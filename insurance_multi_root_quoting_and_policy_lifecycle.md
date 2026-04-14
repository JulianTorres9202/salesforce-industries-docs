---
title: "Manage Multi-Root Quoting and Policy Lifecycle"
source: "https://help.salesforce.com/s/articleView?id=ind.insurance_multi_root_quoting_and_policy_lifecycle.htm&language=en_US&type=5"
scraped: "2026-04-14"
filter: "ind.insurance_"
---# Manage Multi-Root Quoting and Policy Lifecycle

Manage Multi-Root Quoting and Policy Lifecycle[](https://help.salesforce.com/s?language=en_US)

You are here:

1.  [Salesforce Help](/s/?language=en_US)
2.  [Docs](/s/products?language=en_US)
3.  [Digital Insurance](https://help.salesforce.com/s/articleView?id=ind.insurance_admin_standard.htm&language=en_US&type=5)

# Manage Multi-Root Quoting and Policy Lifecycle

Streamline insurance sales by grouping multiple root products such as Auto, Home, and Medical into a single quote and policy structure. Insurance carriers can add multiple root products to a quote and offer them together as a single unit. This topic explains what a multi-root policy is, how it differs from a single-root policy, and the key considerations across quoting and policy lifecycle management.

### Required Editions

<table class="slds-table slds-table_bordered slds-m-bottom_small edition" lwc-3eigj2skqo3=""><colgroup lwc-3eigj2skqo3=""><col style="width:100%" lwc-3eigj2skqo3=""></colgroup><tbody lwc-3eigj2skqo3=""><tr class="" lwc-3eigj2skqo3=""><td style="vertical-align:top;" class="slds-cell-wrap" lwc-3eigj2skqo3="">Available in: Lightning Experience</td></tr><tr class="" lwc-3eigj2skqo3=""><td style="vertical-align:top;" class="slds-cell-wrap" lwc-3eigj2skqo3="">Available in: <strong lwc-3eigj2skqo3="">Enterprise</strong>, <strong lwc-3eigj2skqo3="">Unlimited</strong>, and <strong lwc-3eigj2skqo3="">Developer</strong> Editions of Digital Insurance Platform</td></tr></tbody></table>

This model supports scenarios where carriers sell and service multiple products for the same customer. Managing these products as independent quotes and policies increases complexity across pricing, lifecycle operations, and financial tracking. Multi-root policies reduce this fragmentation by enabling multi-product quoting and centralized lifecycle management while preserving product-level separation.

Let's consider an example. Sara, a captive agent, creates a quote for a customer who requires Auto Gold auto insurance coverage, Dental Gold medical coverage, and Term Life Standard life insurance. She creates a single multi-root quote that includes all three products. When the policyholder accepts the quote, each product is issued as a separate child policy and linked under one parent policy.

Product setup for multi-root policies is identical to single-root policies. You can add single-root bundles to a quote, and you can add the same bundle multiple times if required. No additional product modeling changes are required to support multi-root policies.

Note The current scope of the multi-root policy lifecycle includes policy issuance, endorsement, and renewal.

-   **[Determine the Policy Lifecycle at Issuance](https://help.salesforce.com/s/articleView?id=ind.insurance_multi_root_determine_policy_lifecycle.htm&language=en_US&type=5)**  
    At the time of policy issuance, you must decide whether the policy should follow a single-root or multi-root lifecycle. This decision applies even when the quote contains only one product.
-   **[Differences Between Single and Multi Root Policies](https://help.salesforce.com/s/articleView?id=ind.insurance_multi_root_difference_single_and_multi_root.htm&language=en_US&type=5)**  
    Compare single-root and multi-root policies to understand the differences in structure, lifecycle, and product management.
-   **[Quoting and Rating Key Considerations](https://help.salesforce.com/s/articleView?id=ind.insurance_multi_root_quoting_and_rating_considerations.htm&language=en_US&type=5)**  
    Understand how quoting, pricing, and underwriting work in multi-root quotes, including product configuration, pricing aggregation, instance key rules, and rule evaluation behavior.
-   **[Policy Management Key Considerations](https://help.salesforce.com/s/articleView?id=ind.insurance_multi_root_policy_management_considerations.htm&language=en_US&type=5)**  
    Understand how multi-root policies handle lifecycle operations, financial rollups, asynchronous processing, structure rules, and configuration behavior across parent and child policies.
-   **[Understand Reprice All in Insurance Quotes](https://help.salesforce.com/s/articleView?id=ind.insurance_multi_root_reprice_all_quotes.htm&language=en_US&type=5)**  
    Recalculate pricing across all products in an insurance quote to produce accurate quote-level aggregates and pricing results.

#### See Also

-   [Multi-Root Policy Issuance API](https://developer.salesforce.com/docs/atlas.en-us.insurance_developer_guide.meta/insurance_developer_guide/connect_resources_multi_root_issue_policy.htm)
-   [Multi-Root Policy Endorsement API](https://developer.salesforce.com/docs/atlas.en-us.insurance_developer_guide.meta/insurance_developer_guide/connect_resources_insurance_multi_root_endorsement_policy.htm)
-   [Multi-Root Policy Renewal API](https://developer.salesforce.com/docs/atlas.en-us.insurance_developer_guide.meta/insurance_developer_guide/connect_resources_insurance_policy_multi_root_renew.htm)
-   [Issue Multi-Root Insurance Policy Action](https://developer.salesforce.com/docs/atlas.en-us.insurance_developer_guide.meta/insurance_developer_guide/actions_obj_issue_multi_root_insurance_policy.htm)
-   [Endorse Multi-Root Insurance Policy Action](https://developer.salesforce.com/docs/atlas.en-us.insurance_developer_guide.meta/insurance_developer_guide/actions_obj_endorse_multi_root_insurance_policy.htm)
-   [Renew Multi-Root Insurance Policy Action](https://developer.salesforce.com/docs/atlas.en-us.insurance_developer_guide.meta/insurance_developer_guide/actions_obj_renew_multi_root_insurance_policy.htm)

Did this article solve your issue?

Let us know so we can improve!

YesNo