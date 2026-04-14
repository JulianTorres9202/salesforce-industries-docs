---
title: "Configure Insurance History with Claim History LWC DataPack"
source: "https://help.salesforce.com/s/articleView?id=ind.insurance_configure_insurance_history_with_claim_history_lwc_datapack_620180.htm&language=en_US&type=5"
scraped: "2026-04-14"
filter: "ind.insurance_"
---# Configure Insurance History with Claim History LWC DataPack

Configure Insurance History with Claim History LWC DataPack[](https://help.salesforce.com/s?language=en_US)

You are here:

1.  [Salesforce Help](/s/?language=en_US)
2.  [Docs](/s/products?language=en_US)
3.  [Digital Insurance](https://help.salesforce.com/s/articleView?id=ind.insurance_admin_standard.htm&language=en_US&type=5)

# Configure Insurance History with Claim History LWC DataPack

You can configure the Insurance History Lightning web component to create a cohesive view of all things happening with a claim. A DataPack included with your org gets you started. It has story object configuration that brings essential content into a Claim History tab out of the box.

[](https://help.salesforce.com/s?language=en_US)Note

You can use the Insurance History LWC for other objects in a Salesforce managed package extension, including policies and quotes. For details, see [Configure History Timelines with Insurance History LWC](https://help.salesforce.com/s/articleView?id=ind.insurance_configure_history_timelines_with_insurance_history_lwc.htm&language=en_US&type=5 "You can configure the Insurance History Lightning web component (LWC) to display a timeline of quote, claim, or policy activity in a single, chronological feed that's easy to scan and drill into. See essential activity at a glance and expand content like notes and emails to dive into more detail.").

-   **[Download and Import DataPack for Claim History](https://help.salesforce.com/s/articleView?id=ind.insurance_download_and_import_datapack_for_claim_history_620207.htm&language=en_US&type=5)**  
    Install a DataPack that brings essential content into a Claim History tab out of the box.
-   **[Configure Story Object Settings for Claim History](https://help.salesforce.com/s/articleView?id=ind.insurance_configure_story_object_settings_for_claim_history_620255.htm&language=en_US&type=5)**  
    Before you use Claim History, configure story object settings. Make sure each setting uses the correct **Parent Object Name** (Claim) and **Story Object Lookup Field** (vlocity\_ins\_fsc\_\_ClaimId\_\_c).
-   **[Review How Story Object Settings Map to Insurance History](https://help.salesforce.com/s/articleView?id=ind.insurance_review_how_story_object_settings_map_to_insurance_history_620295.htm&language=en_US&type=5)**  
    The `DP_CUSTOM_InsStoryObjectConfiguration` DataPack includes story object settings that map to different Claim History types.
-   **[Bring Notes into Claim History Timelines](https://help.salesforce.com/s/articleView?id=ind.insurance_notes_claim_history_timelines.htm&language=en_US&type=5)**  
    Add and deploy an Apex class called GetContentNoteAsStory for use with the Claim\_ContentNote story object configuration setting.
-   **[Add the History Tab to Claim Records](https://help.salesforce.com/s/articleView?id=ind.insurance_add_the_history_tab_to_claim_records_620367.htm&language=en_US&type=5)**  
    Add the History tab to records to make it available to users.

Did this article solve your issue?

Let us know so we can improve!

YesNo