---
title: "Add or Update Filter Conditions in Omnistudio Data Mappers for Insurance Coexistence"
source: "https://help.salesforce.com/s/articleView?id=ind.insurance_admin_update_filters_in_data_mappers.htm&language=en_US&type=5"
scraped: "2026-04-13"
filter: "ind.insurance_"
---# Add or Update Filter Conditions in Omnistudio Data Mappers for Insurance Coexistence

Add or Update Filter Conditions in Omnistudio Data Mappers for Insurance Coexistence[](https://help.salesforce.com/s?language=en_US)

You are here:

1.  [Salesforce Help](/s/?language=en_US)
2.  [Docs](/s/products?language=en_US)
3.  [Digital Insurance](https://help.salesforce.com/s/articleView?id=ind.insurance_admin_standard.htm&language=en_US&type=5)

# Add or Update Filter Conditions in Omnistudio Data Mappers for Insurance Coexistence

Update your existing Omnistudio Data Mappers that process Insurance CRM records to exclude Digital Insurance records. In the Data Mappers that you build for Digital Insurance, add filters to exclude Insurance CRM records.

### Required Editions

<table class="slds-table slds-table_bordered slds-m-bottom_small edition" lwc-3eigj2skqo3=""><colgroup lwc-3eigj2skqo3=""><col lwc-3eigj2skqo3=""></colgroup><tbody lwc-3eigj2skqo3=""><tr class="" lwc-3eigj2skqo3=""><td style="vertical-align:top;" class="slds-cell-wrap" lwc-3eigj2skqo3="">Available in: <strong lwc-3eigj2skqo3="">Performance</strong>, <strong lwc-3eigj2skqo3="">Enterprise</strong>, <strong lwc-3eigj2skqo3="">Unlimited</strong>, and <strong lwc-3eigj2skqo3="">Developer</strong> Editions with Digital Insurance and Insurance CRM.</td></tr></tbody></table>

In your Data Mappers that process Product, Quote, Insurance Policy, and Claim records for Insurance managed package or Insurance CRM, add filters to exclude Digital Insurance records. Filter the records by record type. Alternatively, filter quotes, insurance policies, and claims based on the value of the Record Source field. The Record Source field is empty for Insurance CRM records, and has the value Digital Insurance for Digital Insurance records.

Include similar filter conditions in the Data Mappers you create for Digital Insurance workflows to exclude records from insurance CRM workflows.

#### See Also

-   [Omnistudio Data Mappers](https://help.salesforce.com/s/articleView?id=xcloud.os_omnistudio_dataraptors_45587.htm&language=en_US&type=5)

Did this article solve your issue?

Let us know so we can improve!

YesNo