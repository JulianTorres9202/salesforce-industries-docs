---
title: "Product Modeling"
source: "https://help.salesforce.com/s/articleView?id=ind.insurance_brokerage_product_model_intro.htm&language=en_US&type=5"
scraped: "2026-04-13"
filter: "ind.insurance_"
---# Product Modeling

Product Modeling[](https://help.salesforce.com/s?language=en_US)

You are here:

1.  [Salesforce Help](/s/?language=en_US)
2.  [Docs](/s/products?language=en_US)
3.  [Digital Insurance](https://help.salesforce.com/s/articleView?id=ind.insurance_admin_standard.htm&language=en_US&type=5)

# Product Modeling

Policies, coverages, and benefits are modeled as products by using specific record types, such as root product, coverage specification, and benefit specification. During product modeling, you create a hierarchical model where coverages are nested under policies and benefits are nested under coverages. During modeling, all of these entities are modeled as products.

### Required Editions

<table class="slds-table slds-table_bordered slds-m-bottom_small edition" lwc-3eigj2skqo3=""><colgroup lwc-3eigj2skqo3=""><col lwc-3eigj2skqo3=""></colgroup><tbody lwc-3eigj2skqo3=""><tr class="" lwc-3eigj2skqo3=""><td style="vertical-align:top;" class="slds-cell-wrap" lwc-3eigj2skqo3="">Available in: Lightning Expereince</td></tr><tr class="" lwc-3eigj2skqo3=""><td style="vertical-align:top;" class="slds-cell-wrap" lwc-3eigj2skqo3="">Available in: <strong class="uicontrol" lwc-3eigj2skqo3="">Professional</strong>, <strong class="uicontrol" lwc-3eigj2skqo3="">Enterprise</strong>, and<strong class="uicontrol" lwc-3eigj2skqo3=""> Unlimited</strong> Editions where Financial Service Cloud and Insurance Brokerage are enabled.</td></tr></tbody></table>

## Key Objects

[](https://help.salesforce.com/s?language=en_US)

-   Product: Represents items or services sold to customers, either simple (no hierarchy) or bundled. Product Catalog Management is used by insurance carriers to create sellable units with features such as qualification rules, validations, pricing. Brokerages use a limited version.
-   Record Types: A record type is used to set up different types of product and helps you have different versions of product record for different processes and purposes. The root product, coverage specification, and benefit specification record types are shipped out of the box and are used to model policies, coverages, and benefits.
-   Product Component Group: Represents logical grouping of associated products in a bundle. Child components are added under this group.
-   Product Classification: Represents a template to create similar products with inheritable attributes.
-   Attribute: Describes product properties. For example, Deductible, Copay, and Coinsurance.
-   Hierarchy: Represents the hierarchical structure that’s used to model bundled products like Employee Benefits. For example, a product component group such as Coverages is used to add coverage specifications such as Medical, Dental, and Vision under the Employee Benefits root product.

-   **[Product Model for Plan Benefits](https://help.salesforce.com/s/articleView?id=ind.insurance_brokerage_product_model_plan_benefits.htm&language=en_US&type=5)**  
    In Product Catalog Manager, build a product model to manage data entry for plan benefits across health-related coverages

Did this article solve your issue?

Let us know so we can improve!

YesNo