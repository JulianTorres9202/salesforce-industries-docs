---
title: "Create List Views for Insurance Coexistence"
source: "https://help.salesforce.com/s/articleView?id=ind.insurance_admin_create_list_view_filters.htm&language=en_US&type=5"
scraped: "2026-04-13"
filter: "ind.insurance_"
---# Create List Views for Insurance Coexistence

Create List Views for Insurance Coexistence[](https://help.salesforce.com/s?language=en_US)

You are here:

1.  [Salesforce Help](/s/?language=en_US)
2.  [Docs](/s/products?language=en_US)
3.  [Digital Insurance](https://help.salesforce.com/s/articleView?id=ind.insurance_admin_standard.htm&language=en_US&type=5)

# Create List Views for Insurance Coexistence

Create custom list views for Quote, Insurance Policy, and Claim to segregate records based on whether they were created using Digital Insurance, Insurance managed package, or Insurance CRM workflows. Without the custom list views, users see all the records irrespective of the originating solution and could try to perform an invalid action on a record.

### Required Editions

<table class="slds-table slds-table_bordered slds-m-bottom_small edition" lwc-3eigj2skqo3=""><colgroup lwc-3eigj2skqo3=""><col lwc-3eigj2skqo3=""></colgroup><tbody lwc-3eigj2skqo3=""><tr class="" lwc-3eigj2skqo3=""><td style="vertical-align:top;" class="slds-cell-wrap" lwc-3eigj2skqo3="">Available in: <strong lwc-3eigj2skqo3="">Performance</strong>, <strong lwc-3eigj2skqo3="">Enterprise</strong>, <strong lwc-3eigj2skqo3="">Unlimited</strong>, and <strong lwc-3eigj2skqo3="">Developer</strong> Editions with Digital Insurance, and Insurance CRM or the Insurance Industries and Insurance Industries Extension managed packages.</td></tr></tbody></table>

To segregate records by the originating solution, filter Quote, Insurance Policy, and Claim records by the record type. Alternatively, filter records by the value of the Record Source field. When records are created using Digital Insurance workflows, the field has a value of Digital Insurance. When records are created using Insurance managed package or Insurance CRM workflows, the field has an empty value.

Additionally, segregate records by the associated product to create product-specific list views such as Home Insurance Quotes or Auto Silver Quotes. Filter the records by the value of the Product field.

#### See Also

-   [Create or Clone a List View in Lightning Experience](https://help.salesforce.com/s/articleView?id=xcloud.customviews_lex.htm&language=en_US&type=5)

Did this article solve your issue?

Let us know so we can improve!

YesNo