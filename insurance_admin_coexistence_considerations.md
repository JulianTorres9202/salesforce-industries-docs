---
title: "Insurance Coexistence Considerations"
source: "https://help.salesforce.com/s/articleView?id=ind.insurance_admin_coexistence_considerations.htm&language=en_US&type=5"
scraped: "2026-04-13"
filter: "ind.insurance_"
---# Insurance Coexistence Considerations

Insurance Coexistence Considerations[](https://help.salesforce.com/s?language=en_US)

You are here:

1.  [Salesforce Help](/s/?language=en_US)
2.  [Docs](/s/products?language=en_US)
3.  [Digital Insurance](https://help.salesforce.com/s/articleView?id=ind.insurance_admin_standard.htm&language=en_US&type=5)

# Insurance Coexistence Considerations

Before you set up Insurance Coexistence, make sure that you review some key factors that affect your implementation.

### Required Editions

<table class="slds-table slds-table_bordered slds-m-bottom_small edition" lwc-3eigj2skqo3=""><colgroup lwc-3eigj2skqo3=""><col lwc-3eigj2skqo3=""></colgroup><tbody lwc-3eigj2skqo3=""><tr class="" lwc-3eigj2skqo3=""><td style="vertical-align:top;" class="slds-cell-wrap" lwc-3eigj2skqo3="">Available in: <strong lwc-3eigj2skqo3="">Performance</strong>, <strong lwc-3eigj2skqo3="">Enterprise</strong>, <strong lwc-3eigj2skqo3="">Unlimited</strong>, and <strong lwc-3eigj2skqo3="">Developer</strong> Editions with Digital Insurance, and Insurance CRM or the Insurance Industries and Insurance Industries Extension managed packages.</td></tr></tbody></table>

-   Configure your existing org with Insurance CRM or the Insurance managed package for coexistence before you set up products using Digital Insurance. If you have set up products using Digital Insurance on the org, don’t configure the org for coexistence.
-   Although Digital Insurance can coexist with Insurance CRM or the Insurance managed package, these solutions don't interoperate. For example, you can’t set up a home insurance product by using Digital Insurance and then create quotes for the product by using Insurance CRM or the Insurance managed package workflows.
-   After you turn on Insurance Coexistence, you can’t turn it off.
-   Insurance Coexistence doesn’t support the implementation of group benefits with Digital Insurance if the org already has a group insurance implementation with the Insurance managed package.
-   Insurance Coexistence is supported with the standard Omnistudio data model, and with the standard and managed package runtime and designers.
-   The Insurance managed package creates record types for the Product and Quote objects. When you set up your org for Insurance Coexistence, you must create unique record types for the Product, Quote, Insurance Policy, Claim objects to use in Digital Insurance workflows. Make sure that you create the record types before you set up any products using Digital Insurance. You can also use these record types to customize record pages for users to see only the relevant components based on whether the record was created using Digital Insurance or the Insurance managed package.
-   After you turn on Insurance Coexistence, the quote, insurance policy, insurance contract, and claim records that you create with the Digital Insurance workflows have a Record Source field with the value Digital Insurance. When you create these records with Insurance managed package or Insurance CRM workflows, the records have an empty Record Source field. Use the value of the Record Source field to filter records in list views and other bulk operations.

Did this article solve your issue?

Let us know so we can improve!

YesNo