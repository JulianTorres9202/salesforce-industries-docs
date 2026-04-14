---
title: "Configure History Timelines with Insurance History LWC"
source: "https://help.salesforce.com/s/articleView?id=ind.insurance_configure_history_timelines_with_insurance_history_lwc.htm&language=en_US&type=5"
scraped: "2026-04-14"
filter: "ind.insurance_"
---# Configure History Timelines with Insurance History LWC

Configure History Timelines with Insurance History LWC[](https://help.salesforce.com/s?language=en_US)

You are here:

1.  [Salesforce Help](/s/?language=en_US)
2.  [Docs](/s/products?language=en_US)
3.  [Digital Insurance](https://help.salesforce.com/s/articleView?id=ind.insurance_admin_standard.htm&language=en_US&type=5)

# Configure History Timelines with Insurance History LWC

You can configure the Insurance History Lightning web component (LWC) to display a timeline of quote, claim, or policy activity in a single, chronological feed that's easy to scan and drill into. See essential activity at a glance and expand content like notes and emails to dive into more detail.

With a compact History timeline, you can:

[](https://help.salesforce.com/s?language=en_US)

-   Simplify daily CSR tasks or support detailed file reviews and audits.
    
-   Easily access quote, claim, or policy content including emails and approvals, with deeper details and related work tasks just a click away.
    
-   Gain an understanding of the quote, claim, or policy lifecycle with readily available information on key events such as assignments, payments, status changes, and more.
    

[](https://help.salesforce.com/s?language=en_US)![Claim History timeline example](https://sf-zdocs-cdn-prod.zoominsoftware.com/tdta-insurance-260-0-0-production-enus/e4c2671d-0822-4c56-95dd-073f2b1f9ddc/insurance/images/c/claims_history.png)

1.  Click buttons to expand or collapse details [](https://help.salesforce.com/s?language=en_US), refresh data [](https://help.salesforce.com/s?language=en_US), and filter for activity that interests you most [](https://help.salesforce.com/s?language=en_US).
    
2.  Click related records to drill into them.
    
3.  See who did what, when. The most recent activity appears first.
    

Note

Your org includes a [DataPack for building a History tab for claims](https://help.salesforce.com/s/articleView?id=ind.insurance_configure_insurance_history_with_claim_history_lwc_datapack_620180.htm&language=en_US&type=5 "You can configure the Insurance History Lightning web component to create a cohesive view of all things happening with a claim. A DataPack included with your org gets you started. It has story object configuration that brings essential content into a Claim History tab out of the box."). But you can use the Insurance History LWC for other objects in a Salesforce managed package extension, and then incorporate a History tab into records such as policies and quotes.

[](https://help.salesforce.com/s?language=en_US)

## How to Configure a History Timeline

Your History timeline configuration can reference objects such as tasks, emails, and events directly through the Insurance History story object. You can also reference an Apex class for more complex objects like notes, documents (different versions of content), and approvals (process instance steps).

[](https://help.salesforce.com/s?language=en_US)Here's an example of a story object setting that references an email object directly.

Here's an example that references an Apex class.

Story object settings define these fields on the Insurance History LWC.

| 
Field

 | 

Description

 |
| --- | --- |
| 

Title

 | 

Required

The first line in the History item. If Title returns a record ID, it appears as a link so that you can drill into record details.

If Title isn't defined or if it returns a null value, History shows the object name as the Title (for example, simply **Task**).

 |
| 

Title\_Highlight

 | 

A short text field that appears right after Title. You can use it to provide context or guidance (for example, "For your approval"). It remains visible even in collapsed view.

 |
| 

Subtitle

 | 

A long, untrimmed, richly formatted text field. It's used for comments and descriptions.

Use Subtitle or Detail in a story object setting, not both.

 |
| 

Detail

 | 

A long, trimmed, richly formatted text field. It's for data that can be truncated within a History line item.

[](https://help.salesforce.com/s?language=en_US)Use Detail or Subtitle in a story object setting, not both.

 |

Here's how Title (1), Subtitle or Detail (2), and Title\_Highlight (3) appear on a History tab. Use Subtitle to show complete content (recommended), or Detail to truncate content.

After you decide what to include in your history timeline:

[](https://help.salesforce.com/s?language=en_US)

1.  [Configure the Story Object for a History Timeline](https://help.salesforce.com/s/articleView?id=ind.insurance_configure_the_story_object_for_a_history_timeline.htm&language=en_US&type=5 "You configure your History timeline by configuring settings on the story object. You can add a new set of data to the story object configuration, or edit an existing one.")
    
2.  [Configure History Tracking Entries](https://help.salesforce.com/s/articleView?id=ind.insurance_configure_history_tracking_entries.htm&language=en_US&type=5 "You can track granular details as the quote, claim, or policy evolves through its lifecycle by writing records to the Vlocity Tracking Entry object. Then you can configure this Tracking Entry object in the story object to return results to the History timeline.")
    
3.  [Add the History Tab to Records](https://help.salesforce.com/s/articleView?id=ind.insurance_add_the_history_tab_to_records.htm&language=en_US&type=5 "Add the History tab to records to make it available to users.")
    

-   **[Configure the Story Object for a History Timeline](https://help.salesforce.com/s/articleView?id=ind.insurance_configure_the_story_object_for_a_history_timeline.htm&language=en_US&type=5)**  
    You configure your History timeline by configuring settings on the story object. You can add a new set of data to the story object configuration, or edit an existing one.
-   **[Configure History Tracking Entries](https://help.salesforce.com/s/articleView?id=ind.insurance_configure_history_tracking_entries.htm&language=en_US&type=5)**  
    You can track granular details as the quote, claim, or policy evolves through its lifecycle by writing records to the Vlocity Tracking Entry object. Then you can configure this Tracking Entry object in the story object to return results to the History timeline.
-   **[Add the History Tab to Records](https://help.salesforce.com/s/articleView?id=ind.insurance_add_the_history_tab_to_records.htm&language=en_US&type=5)**  
    Add the History tab to records to make it available to users.

Did this article solve your issue?

Let us know so we can improve!

YesNo