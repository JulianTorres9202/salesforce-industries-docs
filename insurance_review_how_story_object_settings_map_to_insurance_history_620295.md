---
title: "Review How Story Object Settings Map to Insurance History"
source: "https://help.salesforce.com/s/articleView?id=ind.insurance_review_how_story_object_settings_map_to_insurance_history_620295.htm&language=en_US&type=5"
scraped: "2026-04-14"
filter: "ind.insurance_"
---# Review How Story Object Settings Map to Insurance History

Review How Story Object Settings Map to Insurance History[](https://help.salesforce.com/s?language=en_US)

You are here:

1.  [Salesforce Help](/s/?language=en_US)
2.  [Docs](/s/products?language=en_US)
3.  [Digital Insurance](https://help.salesforce.com/s/articleView?id=ind.insurance_admin_standard.htm&language=en_US&type=5)

# Review How Story Object Settings Map to Insurance History

The `DP_CUSTOM_InsStoryObjectConfiguration` DataPack includes story object settings that map to different Claim History types.

| 
Story Object Setting

 | 

Insurance History Type

 |
| --- | --- |
| 

[](https://help.salesforce.com/s?language=en_US)`Claim_EmailMessage`

 | 

Email.

[](https://help.salesforce.com/s?language=en_US)Appears in a two-column format, with a **From** section on the left and a **To** section on the right. The message body appears underneath.

 |
| 

[](https://help.salesforce.com/s?language=en_US)`Claim_Task`

 | 

[](https://help.salesforce.com/s?language=en_US)Task.

[](https://help.salesforce.com/s?language=en_US)Shows the task's subject and its description, which you can expand or collapse.

 |
| 

`Claim_TrackingEntry`

 | 

Event.

Events include steps within a claim’s workflow, such as Claim Opened, Claim Assigned, and Claim Closed. Events are configured in Process Builder as Tracking Entry records.

In Process Builder, you can configure custom labels for the Tracking Entry values that appear as events on a History tab. See [Configure History Timelines with Insurance History LWC](https://help.salesforce.com/s/articleView?id=ind.insurance_configure_history_timelines_with_insurance_history_lwc.htm&language=en_US&type=5 "You can configure the Insurance History Lightning web component (LWC) to display a timeline of quote, claim, or policy activity in a single, chronological feed that's easy to scan and drill into. See essential activity at a glance and expand content like notes and emails to dive into more detail.").

 |
| 

`Claim_ContentDocument`

 | 

Document.

[](https://help.salesforce.com/s?language=en_US)This setting works with the GetContentDocumentAsStory Apex class.

 |
| 

`Claim_ContentNote`

 | 

Note.

[](https://help.salesforce.com/s?language=en_US)This setting works with the GetContentNoteAsStory Apex class. To set up this class, see [Bring Notes into Claim History Timelines](https://help.salesforce.com/s/articleView?id=ind.insurance_notes_claim_history_timelines.htm&language=en_US&type=5 "Add and deploy an Apex class called GetContentNoteAsStory for use with the Claim_ContentNote story object configuration setting."). This setting requires you to enable notes. From Setup, in the Quick Find box, enter Notes Settings, and then select **Notes Settings**. Confirm **Enable Notes** is selected.

 |
| 

`Claim_ProcessInstanceStep`

 | 

Step within a workflow process (for example, approval requests).

[](https://help.salesforce.com/s?language=en_US)This setting works with the GetProcessInstanceStepAsStory Apex class.

 |

You can reconfigure these settings, use them as templates for other story object settings, and add new story object settings to suit your needs. See [Configure History Timelines with Insurance History LWC](https://help.salesforce.com/s/articleView?id=ind.insurance_configure_history_timelines_with_insurance_history_lwc.htm&language=en_US&type=5 "You can configure the Insurance History Lightning web component (LWC) to display a timeline of quote, claim, or policy activity in a single, chronological feed that's easy to scan and drill into. See essential activity at a glance and expand content like notes and emails to dive into more detail.").

Did this article solve your issue?

Let us know so we can improve!

YesNo