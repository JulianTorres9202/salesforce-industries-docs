---
title: "History Timelines with Insurance History LWC"
source: "https://help.salesforce.com/s/articleView?id=ind.insurance_history_timelines_with_insurance_history_lwc.htm&language=en_US&type=5"
scraped: "2026-04-14"
filter: "ind.insurance_"
---# History Timelines with Insurance History LWC

History Timelines with Insurance History LWC[](https://help.salesforce.com/s?language=en_US)

You are here:

1.  [Salesforce Help](/s/?language=en_US)
2.  [Docs](/s/products?language=en_US)
3.  [Digital Insurance](https://help.salesforce.com/s/articleView?id=ind.insurance_admin_standard.htm&language=en_US&type=5)

# History Timelines with Insurance History LWC

You can configure the Insurance History Lightning web component to get a cohesive view of all things happening with a quote, claim, or policy. When did a claim open or get reassigned, when was an approval request submitted, what time did an agent first contact the claimant? A History tab displays a timeline of all this activity in a single, chronological feed that's easy to scan and drill into. See essential activity at a glance and expand content like notes and emails to dive into more detail.

Your org includes a new [DataPack for building a History tab for claims](https://help.salesforce.com/s/articleView?id=ind.insurance_configure_insurance_history_with_claim_history_lwc_datapack_620180.htm&language=en_US&type=5 "You can configure the Insurance History Lightning web component to create a cohesive view of all things happening with a claim. A DataPack included with your org gets you started. It has story object configuration that brings essential content into a Claim History tab out of the box."). But you can use the Insurance History LWC for other objects in a Salesforce managed package extension, and then incorporate a History tab into records such as policies and quotes.

[](https://help.salesforce.com/s?language=en_US)**Why:** A History tab gives you a concise snapshot so you can:

-   Simplify daily CSR tasks or support detailed file reviews and audits.
    
-   Easily access quote, claim, or policy content including emails and approvals, with deeper details and related work tasks just a click away.
    
-   Gain an understanding of the quote, claim, or policy lifecycle with readily available information on key events such as assignments, payments, status changes, and more.
    

[](https://help.salesforce.com/s?language=en_US)**How:** To get started, install a DataPack that brings essential content into a Claim History tab out of the box. Your configuration can reference objects such as tasks, emails, and events directly through the Insurance History story object. You can also reference an Apex class for more complex objects like notes, documents (different versions of content), and approvals (process instance steps).

Here's an overview of configuration tasks.

1.  Download the `DP_CUSTOM_InsStoryObjectConfiguration` static resource file as a .json file and import it through Vlocity Cards. Then configure story object settings used for Claim History.
    
2.  Reconfigure or add story object settings to suit your needs.
    
3.  In Process Builder, configure Tracking Entry values that mark milestone events throughout a claim's lifecycle.
    
4.  Add the History tab to claim records.
    

## See Also

-   [Configure History Timelines with Insurance History LWC](https://help.salesforce.com/s/articleView?id=ind.insurance_configure_history_timelines_with_insurance_history_lwc.htm&language=en_US&type=5 "You can configure the Insurance History Lightning web component (LWC) to display a timeline of quote, claim, or policy activity in a single, chronological feed that's easy to scan and drill into. See essential activity at a glance and expand content like notes and emails to dive into more detail.")
    
-   [Configure Insurance History with Claim History LWC DataPack](https://help.salesforce.com/s/articleView?id=ind.insurance_configure_insurance_history_with_claim_history_lwc_datapack_620180.htm&language=en_US&type=5 "You can configure the Insurance History Lightning web component to create a cohesive view of all things happening with a claim. A DataPack included with your org gets you started. It has story object configuration that brings essential content into a Claim History tab out of the box.")
    

Did this article solve your issue?

Let us know so we can improve!

YesNo