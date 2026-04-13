---
title: "Add a Filter Condition in the Bulk Policy Renewal Batch Job for Insurance Coexistence"
source: "https://help.salesforce.com/s/articleView?id=ind.insurance_admin_update_bulk_renewal_batch_job_definition.htm&language=en_US&type=5"
scraped: "2026-04-13"
filter: "ind.insurance_"
---# Add a Filter Condition in the Bulk Policy Renewal Batch Job for Insurance Coexistence

Add a Filter Condition in the Bulk Policy Renewal Batch Job for Insurance Coexistence[](https://help.salesforce.com/s?language=en_US)

You are here:

1.  [Salesforce Help](/s/?language=en_US)
2.  [Docs](/s/products?language=en_US)
3.  [Digital Insurance](https://help.salesforce.com/s/articleView?id=ind.insurance_admin_standard.htm&language=en_US&type=5)

# Add a Filter Condition in the Bulk Policy Renewal Batch Job for Insurance Coexistence

In the batch job for bulk renewal of policies, add a filter to process only the insurance policies issued for Digital Insurance products.

### Required Editions

<table class="slds-table slds-table_bordered slds-m-bottom_small edition" lwc-3eigj2skqo3=""><colgroup lwc-3eigj2skqo3=""><col lwc-3eigj2skqo3=""></colgroup><tbody lwc-3eigj2skqo3=""><tr class="" lwc-3eigj2skqo3=""><td style="vertical-align:top;" class="slds-cell-wrap" lwc-3eigj2skqo3="">Available in: <strong lwc-3eigj2skqo3="">Performance</strong>, <strong lwc-3eigj2skqo3="">Enterprise</strong>, <strong lwc-3eigj2skqo3="">Unlimited</strong>, and <strong lwc-3eigj2skqo3="">Developer</strong> Editions with Digital Insurance, and Insurance CRM or the Insurance Industries and Insurance Industries Extension managed packages.</td></tr></tbody></table>

With Insurance Coexistence, your org has insurance policies issued for older products through Insurance managed package workflows as well as the insurance policies issued for the products launched with Digital Insurance. The batch job for bulk policy renewal should process only the insurance policies for Digital Insurance products. When you create the batch job, add a filter condition to select only the insurance policies that have a Record Source field with the value Digital Insurance. See [Create a Batch Job Definition](https://help.salesforce.com/s/articleView?id=ind.insurance_set_up_bulk_renewal_batch_job_definition.htm&language=en_US&type=5).

Did this article solve your issue?

Let us know so we can improve!

YesNo