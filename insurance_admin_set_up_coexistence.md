---
title: "Set Up Insurance Coexistence with Salesforce Go"
source: "https://help.salesforce.com/s/articleView?id=ind.insurance_admin_set_up_coexistence.htm&language=en_US&type=5"
scraped: "2026-04-13"
filter: "ind.insurance_"
---# Set Up Insurance Coexistence with Salesforce Go

Set Up Insurance Coexistence with Salesforce Go[](https://help.salesforce.com/s?language=en_US)

You are here:

1.  [Salesforce Help](/s/?language=en_US)
2.  [Docs](/s/products?language=en_US)
3.  [Digital Insurance](https://help.salesforce.com/s/articleView?id=ind.insurance_admin_standard.htm&language=en_US&type=5)

# Set Up Insurance Coexistence with Salesforce Go

Configure your org for the coexistence of Digital Insurance with the Insurance manage package or Insurance CRM.

### Required Editions

<table class="slds-table slds-table_bordered slds-m-bottom_small edition" lwc-3eigj2skqo3=""><colgroup lwc-3eigj2skqo3=""><col lwc-3eigj2skqo3=""></colgroup><tbody lwc-3eigj2skqo3=""><tr class="" lwc-3eigj2skqo3=""><td style="vertical-align:top;" class="slds-cell-wrap" lwc-3eigj2skqo3="">Available in: <strong lwc-3eigj2skqo3="">Performance</strong>, <strong lwc-3eigj2skqo3="">Enterprise</strong>, <strong lwc-3eigj2skqo3="">Unlimited</strong>, and <strong lwc-3eigj2skqo3="">Developer</strong> Editions with Digital Insurance, and Insurance CRM or the Insurance Industries and Insurance Industries Extension managed packages.</td></tr></tbody></table>

| User Permissions Needed |
| --- |
| To turn on features in Salesforce Go: | Customize Application |
| To view Salesforce Go: | View Setup and Configuration |

1.  Select **Salesforce Go** from the gear menu or from the main Setup menu.
2.  To configure your org for the coexistence of Digital Insurance with the Insurance package, search for and select the **Coexistence for Insurance Managed Package** feature.
    1.  On the feature page, click **Get Started**.
    2.  Turn on coexistence for the Insurance managed package.
    3.  Complete the configuration steps.
3.  To configure your org for the coexistence of Digital Insurance with Insurance CRM, search for and select the **Coexistence for Insurance CRM** feature.
    1.  On the feature page, click **Get Started**.
    2.  Turn on coexistence for the Insurance CRM.
    3.  Complete the configuration steps.

-   **[Create Product Record Types for Insurance Coexistence](https://help.salesforce.com/s/articleView?id=ind.insurance_admin_create_product_record_types.htm&language=en_US&type=5)**  
    Create unique record types for the Product object to use in Digital Insurance workflows. The unique record types ensure Digital Insurance products are excluded from Insurance managed package UI components and workflows that filter by record type. You can also use the record types to customize the record pages for users.
-   **[Create Record Types for Insurance Coexistence](https://help.salesforce.com/s/articleView?id=ind.insurance_admin_create_record_types.htm&language=en_US&type=5)**  
    Create unique record types for the Quote, Insurance Policy, and Claim objects to use in Digital Insurance workflows. Use the record types to customize record pages and build custom automations for Digital Insurance.
-   **[Set Up Page Layouts and Record Pages for Insurance Coexistence](https://help.salesforce.com/s/articleView?id=ind.insurance_admin_set_up_page_layouts.htm&language=en_US&type=5)**  
    Customize the page layouts and record pages for Quote, Insurance Policy, and Claim so that users see only the fields, actions, and components that they need for Digital Insurance. Assign the page layouts and record pages to the Digital Insurance record types.
-   **[Create List Views for Insurance Coexistence](https://help.salesforce.com/s/articleView?id=ind.insurance_admin_create_list_view_filters.htm&language=en_US&type=5)**  
    Create custom list views for Quote, Insurance Policy, and Claim to segregate records based on whether they were created using Digital Insurance, Insurance managed package, or Insurance CRM workflows. Without the custom list views, users see all the records irrespective of the originating solution and could try to perform an invalid action on a record.
-   **[Create and Update Sharing Rules for Insurance Coexistence](https://help.salesforce.com/s/articleView?id=ind.insurance_admin_update_sharing_settings.htm&language=en_US&type=5)**  
    Create and edit sharing rules for Product, Quote, Insurance Policy, and Claim to add the record type or the value of the Record Source field to the sharing criteria. The updated criteria ensures users have access to only the records they need.
-   **[Update Custom Triggers for Insurance Coexistence](https://help.salesforce.com/s/articleView?id=ind.insurance_admin_update_custom_triggers.htm&language=en_US&type=5)**  
    Update the triggers that you use with the Insurance managed package or Insurance CRM workflows to exclude Digital Insurance records.
-   **[Add a Filter Condition in the Bulk Policy Renewal Batch Job for Insurance Coexistence](https://help.salesforce.com/s/articleView?id=ind.insurance_admin_update_bulk_renewal_batch_job_definition.htm&language=en_US&type=5)**  
    In the batch job for bulk renewal of policies, add a filter to process only the insurance policies issued for Digital Insurance products.
-   **[Add or Update Filter Conditions in Flows for Insurance Coexistence](https://help.salesforce.com/s/articleView?id=ind.insurance_admin_update_filters_in_flows.htm&language=en_US&type=5)**  
    Update your existing flows that automate actions in Insurance CRM workflows to exclude Digital Insurance records. In the flows you create for Digital Insurance records, add filter conditions to exclude Insurance CRM records.
-   **[Add or Update Filter Conditions in Omnistudio Data Mappers for Insurance Coexistence](https://help.salesforce.com/s/articleView?id=ind.insurance_admin_update_filters_in_data_mappers.htm&language=en_US&type=5)**  
    Update your existing Omnistudio Data Mappers that process Insurance CRM records to exclude Digital Insurance records. In the Data Mappers that you build for Digital Insurance, add filters to exclude Insurance CRM records.

#### See Also

-   [Discover and Set Up Features with Salesforce Go](https://help.salesforce.com/s/articleView?id=xcloud.setup_salesforce_go.htm&language=en_US&type=5)

Did this article solve your issue?

Let us know so we can improve!

YesNo