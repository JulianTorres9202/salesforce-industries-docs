---
title: "Product Qualification Rules for Insurance"
source: "https://help.salesforce.com/s/articleView?id=ind.insurance_admin_product_qualification_rules.htm&language=en_US&type=5"
scraped: "2026-04-13"
filter: "ind.insurance_"
---# Product Qualification Rules for Insurance

Product Qualification Rules for Insurance[](https://help.salesforce.com/s?language=en_US)

You are here:

1.  [Salesforce Help](/s/?language=en_US)
2.  [Docs](/s/products?language=en_US)
3.  [Digital Insurance](https://help.salesforce.com/s/articleView?id=ind.insurance_admin_standard.htm&language=en_US&type=5)

# Product Qualification Rules for Insurance

Define customer eligibility for products to ensure that users see only specific products in the product catalog. You can qualify or disqualify products on the basis of criteria such as location, account attributes, or age.

### Required Editions

<table class="slds-table slds-table_bordered slds-m-bottom_small edition" lwc-3eigj2skqo3=""><colgroup lwc-3eigj2skqo3=""><col style="width:100%" lwc-3eigj2skqo3=""></colgroup><tbody lwc-3eigj2skqo3=""><tr class="" lwc-3eigj2skqo3=""><td style="vertical-align:top;" class="slds-cell-wrap" lwc-3eigj2skqo3="">Available in: Lightning Experience</td></tr><tr class="" lwc-3eigj2skqo3=""><td style="vertical-align:top;" class="slds-cell-wrap" lwc-3eigj2skqo3="">Available in: <strong lwc-3eigj2skqo3="">Enterprise</strong>, <strong lwc-3eigj2skqo3="">Unlimited</strong>, and <strong lwc-3eigj2skqo3="">Developer</strong> Editions of Digital Insurance Platform where Product Configuration is enabled with the Revenue Lifecycle Management add-on</td></tr></tbody></table>

By default, all products in the product catalog are qualified. Use qualification rules to specify the conditions based on which products and categories remain qualified or get disqualified. In Insurance, the eligibility rules determine the customer eligibility for insurance products and optional coverages.

The product is qualified when the product matches the specified qualification criteria. Use eligibility rules in the quote process to exclude insurance products and optional coverages that a potential customer doesn't qualify for. For example, for the US market, you can create an eligibility rule for a Medicare supplement insurance product that screens out anyone under the age of 65 years, so that the product is not offered to them.

-   **[Set Up Product Qualification](https://help.salesforce.com/s/articleView?id=ind.insurance_admin_set_up_qualification_rules.htm&language=en_US&type=5)**  
    To make sure your users browse only qualified products in product catalog, you must create context definitions and decision tables for Product Catalog Management, create qualification rules and qualification rule procedure, and then configure product discovery settings.

#### See Also

-   [Considerations for Using Qualification Rules](https://help.salesforce.com/s/articleView?id=ind.product_catalog_qualification_rules.htm&language=en_US&type=5)

Did this article solve your issue?

Let us know so we can improve!

YesNo