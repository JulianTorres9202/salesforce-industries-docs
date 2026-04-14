---
title: "Subscribe to the InsAsyncJobStatusNotification Event"
source: "https://help.salesforce.com/s/articleView?id=ind.insurance_subscribe_to_the_insasyncjobstatusnotification__event.htm&language=en_US&type=5"
scraped: "2026-04-14"
filter: "ind.insurance_"
---# Subscribe to the InsAsyncJobStatusNotification Event

Subscribe to the InsAsyncJobStatusNotification Event[](https://help.salesforce.com/s?language=en_US)

You are here:

1.  [Salesforce Help](/s/?language=en_US)
2.  [Docs](/s/products?language=en_US)
3.  [Digital Insurance](https://help.salesforce.com/s/articleView?id=ind.insurance_admin_standard.htm&language=en_US&type=5)

# Subscribe to the InsAsyncJobStatusNotification Event

Out-of-sequence endorsement works asynchronously after you initiate the policy issuance with the new modifications. After an out-of-sequence endorsement completes, an event is published. Subscribe to these events to support additional custom notification types, such as sending emails to the customers.

By default, you have the **Out-of-Sequence Endorsement** custom notification type enabled in your org. It enables bell notifications to notify you about the status of an async out-of-sequence endorsement job.

Event Name: InsAsyncJobStatusNotification

The InsAsyncJobStatusNotification platform event includes these custom fields:

| API Name | Field Label | Data Type | Description |
| --- | --- | --- | --- |
| Additional Information | AdditionalInformation\_\_c | Long Text Area | The additional information about the event. |
| Insurance Async Bulk Request | AsyncJobRequestId\_\_c | Text | The Insurance Async Bulk Request associated with the event. |
| Insurance Async Bulk Request Status | AsyncJobRequestStatus\_\_c | Text | The status of the Insurance Async Bulk Request. |
| Event Name | EventName\_\_c | Text | The name of the event. |
| Message | 
Message\_\_c

 | Long Text Area | The message that's sent with the notification. |
| Action Name | ActionName\_\_c | Text | The name of the action that's associated with the notification. |
| Notification Name | NotificationName\_\_c | Text | The name of the notification. |
| Subject | 

Subject\_\_c

 | Text | The subject of the asynchronous job status notification event. |
| Target Object | TargetObject\_\_c | Text | The target object for the async job status notification. |
| Recipient | Recipient\_\_c | Long Text Area | The recipients of the notification. |

You can subscribe to platform event messages with flows or use Apex triggers to subscribe to platform event notifications. To learn more, see [Subscribing to Platform Events](https://developer.salesforce.com/docs/atlas.en-us.platform_events.meta/platform_events/platform_events_subscribe.htm).

Did this article solve your issue?

Let us know so we can improve!

YesNo