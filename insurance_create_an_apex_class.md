---
title: "Create an Apex Class"
source: "https://help.salesforce.com/s/articleView?id=ind.insurance_create_an_apex_class.htm&language=en_US&type=5"
scraped: "2026-04-14"
filter: "ind.insurance_"
---# Create an Apex Class

Create an Apex Class[](https://help.salesforce.com/s?language=en_US)

You are here:

1.  [Salesforce Help](/s/?language=en_US)
2.  [Docs](/s/products?language=en_US)
3.  [Digital Insurance](https://help.salesforce.com/s/articleView?id=ind.insurance_admin_standard.htm&language=en_US&type=5)

# Create an Apex Class

Create an Apex class to send an email with attachment to the user who requests insurance proof.

<table class="slds-table slds-table_bordered slds-m-bottom_small" lwc-3eigj2skqo3=""><colgroup lwc-3eigj2skqo3=""><col style="width:100%" lwc-3eigj2skqo3=""></colgroup><tbody lwc-3eigj2skqo3=""><tr class="" lwc-3eigj2skqo3=""><td style="vertical-align:top;" class="slds-cell-wrap" lwc-3eigj2skqo3=""><strong lwc-3eigj2skqo3="">REQUIRED EDITIONS</strong></td></tr><tr class="" lwc-3eigj2skqo3=""><td style="vertical-align:top;" class="slds-cell-wrap" lwc-3eigj2skqo3="">Available in: Lightning Experience in <strong class="uicontrol" lwc-3eigj2skqo3="">Professional</strong>, <strong class="uicontrol" lwc-3eigj2skqo3="">Enterprise</strong>, and <strong class="uicontrol" lwc-3eigj2skqo3="">Unlimited</strong> editions where Financial Services Cloud license is enabled with FSC Insurance add-on.</td></tr></tbody></table>

<table class="slds-table slds-table_bordered slds-m-bottom_small" lwc-3eigj2skqo3=""><colgroup lwc-3eigj2skqo3=""><col style="width:50%" lwc-3eigj2skqo3=""><col style="width:50%" lwc-3eigj2skqo3=""></colgroup><tbody lwc-3eigj2skqo3=""><tr class="" lwc-3eigj2skqo3=""><td style="vertical-align:top;" colspan="2" class="slds-cell-wrap" lwc-3eigj2skqo3=""><strong lwc-3eigj2skqo3="">USER PERMISSIONS NEEDED</strong></td></tr><tr class="" lwc-3eigj2skqo3=""><td style="vertical-align:top;" class="slds-cell-wrap" lwc-3eigj2skqo3="">To set up the Request Insurance Proof service process:</td><td style="vertical-align:top;" class="slds-cell-wrap" lwc-3eigj2skqo3=""><p lwc-3eigj2skqo3="">Industries Service Process, Industry Service Excellence, Omnistudio, Case, Service Catalog Request objects Read, Create, Edit, Delete, View All Records</p><p lwc-3eigj2skqo3="">AND</p><p lwc-3eigj2skqo3="">FSC Insurance</p><p lwc-3eigj2skqo3="">AND</p><p lwc-3eigj2skqo3="">Financial Services Cloud Extension OR FSC Sales</p><p lwc-3eigj2skqo3="">OR</p><p lwc-3eigj2skqo3="">Financial Services Cloud Basic</p><p lwc-3eigj2skqo3="">OR</p><p style="margin-bottom:0;" lwc-3eigj2skqo3="">Financial Services Cloud Standard</p></td></tr><tr class="" lwc-3eigj2skqo3=""><td style="vertical-align:top;" class="slds-cell-wrap" lwc-3eigj2skqo3="">To use Request Insurance Proof service process:</td><td style="vertical-align:top;" class="slds-cell-wrap" lwc-3eigj2skqo3=""><p lwc-3eigj2skqo3="">Industries Service Process, Industry Service Excellence, Omnistudio, Case, Service Catalog Request objects Read, Create, Edit, Delete, View All Records</p><p lwc-3eigj2skqo3="">AND</p><p lwc-3eigj2skqo3="">FSC Insurance</p><p lwc-3eigj2skqo3="">AND</p><p lwc-3eigj2skqo3="">Financial Services Cloud Extension OR FSC Sales</p><p lwc-3eigj2skqo3="">OR</p><p lwc-3eigj2skqo3="">Financial Services Cloud Basic</p><p lwc-3eigj2skqo3="">OR</p><p style="margin-bottom:0;" lwc-3eigj2skqo3="">Financial Services Cloud Standard</p></td></tr></tbody></table>

1.  Click Setup, and then click **Developer Console**.
2.  [Create an Apex class](https://help.salesforce.com/s/articleView?id=platform.ls_create_apex_class_for_apex_action.htm&language=en_US&type=5).
    
    Example: To send an email with attachment to the user who requests insurance proof, use a script like this:
    
    ```
    /*************************
    * @Class Name:- FSCInsServiceProcessSendEmail
    * @Description:- This apex class contains an invocable method used to send email along with attachment
    **************************/
    global with sharing class FSCInsServiceProcessSendEmail {
    // Method to send email along with attachment and reurns either Success or Failure back to flow output variable
    @InvocableMethod(label='Send Email to user with attachment' description='Sends email to user from apex ')
    public static List<String> sendEmail(List<Requests> request) {
    List<Messaging.SingleEmailMessage> mails = new List<Messaging.SingleEmailMessage>();
    Messaging.SingleEmailMessage mail = new Messaging.SingleEmailMessage();
    List<String> response = new List<String>();
    List<String> sendTo = new List<String> {request[0].sendToEmailId};
    mail.setToAddresses(sendTo);
    mail.setSubject(request[0].emailSubject);
    mail.setHtmlBody(request[0].textTemplate);
    //Fetch attachment id associated to the caseId and append it to email as attachments
    List<Attachment> attList = new List<Attachment> ([SELECT Id, Name FROM Attachment WHERE parentId =: request[0].caseId WITH SECURITY_ENFORCED]);
    if (attList.size() > 0) {
    List<String> attachmentIds = new List<String> {attList[0].Id};
    mail.setEntityAttachments(attachmentIds);
    }
    // Add email to the master list
    mails.add(mail);
    //Send all emails in the master list
    Messaging.SendEmailResult[] results = Messaging.sendEmail(mails);
    if (results[0].success) {
    response.add('Success');
    } else {
    response.add('Failed to send email');
    }
    return response;
    }
    
    //set of invocable variables which is used to set values from flow
    global class Requests {
    @InvocableVariable(label='Email Body' description='Text template of email body')
    global String textTemplate;
    @InvocableVariable(label='Send To Email Id' description='Email id of recipient')
    global String sendToEmailId;
    @InvocableVariable(label='CaseId' description='Case Id associated with attachment')
    global String caseId;
    @InvocableVariable(label='Email Subject' description='Email subject')
    global String emailSubject;
    }
    }
    ```

Did this article solve your issue?

Let us know so we can improve!

YesNo