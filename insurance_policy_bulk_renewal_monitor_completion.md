---
title: "Set Up Process End Notification for Bulk Renewals"
source: "https://help.salesforce.com/s/articleView?id=ind.insurance_policy_bulk_renewal_monitor_completion.htm&language=en_US&type=5"
scraped: "2026-04-14"
filter: "ind.insurance_"
---# Set Up Process End Notification for Bulk Renewals

Set Up Process End Notification for Bulk Renewals[](https://help.salesforce.com/s?language=en_US)

You are here:

1.  [Salesforce Help](/s/?language=en_US)
2.  [Docs](/s/products?language=en_US)
3.  [Digital Insurance](https://help.salesforce.com/s/articleView?id=ind.insurance_admin_standard.htm&language=en_US&type=5)

# Set Up Process End Notification for Bulk Renewals

Learn how to use the platform event from the batch framework to detect when a bulk policy renewal job completes and trigger a notification or follow-up action. Use the platform event triggered by the batch framework at the end of a batch job. A Platform Event–Triggered flow subscribes to all Batch Job Status Change Events from the batch framework.

Process flow:

-   The user triggers the batch job with a jobIdentifier to uniquely identify the bulk renewal request.
-   The batch job retrieves policy records based on filter criteria on the Insurance Policy entity and triggers the batch flow for each policy record.
-   The flow calls the out-of-the-box Renew Insurance Policies invocable action, which creates entries in the InsuranceAsyncBulkRecordDetail entity with the status Scheduled and publishes a policy event. All these entries are grouped under the same jobIdentifier.
-   By the time the batch completes, all policies to be renewed are recorded in the async entity. You can determine if the process has ended by checking the number of records with a status not in (Success, Fail) for that jobIdentifier in InsuranceAsyncBulkRecordDetail.
-   When the job completes, the batch framework triggers the BatchJobStatusChangeEvent platform event. The platform event flow subscribed to this event is triggered. It checks for bulk renewal batch jobs and calls the invocable action that enqueues a Queueable Apex job with a delay.
-   This Queueable Apex job checks for the number of records with a status not in (Success, Fail) for the same jobIdentifier. If the count is greater than 0, it enqueues itself again. If the count is 0, it raises a notification or fires another event.

1.  Create a Platform Event–Triggered flow.
2.  Select the Batch Job Status Changed Event platform event.
3.  Filter events based on batch job definition and status.
4.  Add an Apex action to the Flow. The action enqueues a queueable apex job that checks the bulk renew request status based on data in monitoring entities.
    
    Sample Apex Class: CallRenewStatusQueueable
    
    ```
    public with sharing class CallRenewStatusQueueable {
      @InvocableMethod
      public static void execute(List<Requests> requestList) {
        for (Requests request : requestList) {
          String jobId = request.batchJobId;
          BatchJob job = [SELECT RuntimeParameter FROM BatchJob WHERE Id = :jobId];
          Map<String, Object> paramsMap = 
            (Map<String, Object>) JSON.deserializeUntyped(job.RuntimeParameter);
    
          List<Object> inputParams = 
            (List<Object>) paramsMap.get('batchJobFlowRunTimeParameters');
    
          String jobIdentifier = '';
          for (Object param : inputParams) {
            Map<String, Object> temp = (Map<String, Object>) param;
            if (temp.get('name') == 'requestId [Flow]') {
              jobIdentifier = (String) temp.get('value');
            }
          }
    
          System.enqueueJob(new CheckBulkRenewStatus(jobIdentifier), 10);
        }
      }
    
      public class Requests {
        @InvocableVariable(required=true)
        public String batchJobId;
      }
    }
    ```
    
5.  Define the Queueable Apex Job.
    
    Sample Class: CheckBulkRenewStatus
    
    ```
    public class CheckBulkRenewStatus implements Queueable {
      private String jobIdentifier;
    
      public CheckBulkRenewStatus(String jobIdentifier) {
        this.jobIdentifier = jobIdentifier;
      }
    
      public void execute(QueueableContext context) {
        InsuranceAsyncBulkRequest asyncRequest = [
          SELECT Id FROM InsuranceAsyncBulkRequest 
          WHERE JobIdentifier = :jobIdentifier LIMIT 1
        ];
    
        InsuranceAsyncBulkRequestItem item = [
          SELECT Id FROM InsuranceAsyncBulkRequestItem 
          WHERE InsuranceAsyncBulkRequestId = :asyncRequest.Id
        ];
    
        List<InsuranceAsyncBulkRecordDetail> pendingItems = [
          SELECT Id FROM InsuranceAsyncBulkRecordDetail 
          WHERE InsuranceAsyncBulkRequestItemId = :item.Id 
          AND Status IN ('In Progress', 'Scheduled')
        ];
    
        if (pendingItems.size() > 0) {
          System.enqueueJob(new CheckBulkRenewStatus(jobIdentifier), 10); // Retry
        } else {
          // All renewals completed — raise an event or notify user
          System.debug('Bulk renewal complete. Sending final notification.');
        }
      }
    }
    ```
    
6.  Save your changes, and activate the flow.

Did this article solve your issue?

Let us know so we can improve!

YesNo