---
title: "Medical Coverage Product Structure"
source: "https://help.salesforce.com/s/articleView?id=ind.insurance_brokerage_product_model_medical_coverage_structure.htm&language=en_US&type=5"
scraped: "2026-04-13"
filter: "ind.insurance_"
---# Medical Coverage Product Structure

Medical Coverage Product Structure[](https://help.salesforce.com/s?language=en_US)

You are here:

1.  [Salesforce Help](/s/?language=en_US)
2.  [Docs](/s/products?language=en_US)
3.  [Digital Insurance](https://help.salesforce.com/s/articleView?id=ind.insurance_admin_standard.htm&language=en_US&type=5)

# Medical Coverage Product Structure

Model the medical coverage product structure under the Employee Benefits root product.

### Required Editions

<table class="slds-table slds-table_bordered slds-m-bottom_small edition" lwc-3eigj2skqo3=""><colgroup lwc-3eigj2skqo3=""><col lwc-3eigj2skqo3=""></colgroup><tbody lwc-3eigj2skqo3=""><tr class="" lwc-3eigj2skqo3=""><td style="vertical-align:top;" class="slds-cell-wrap" lwc-3eigj2skqo3="">Available in: Lightning Expereince</td></tr><tr class="" lwc-3eigj2skqo3=""><td style="vertical-align:top;" class="slds-cell-wrap" lwc-3eigj2skqo3="">Available in: <strong class="uicontrol" lwc-3eigj2skqo3="">Professional</strong>, <strong class="uicontrol" lwc-3eigj2skqo3="">Enterprise</strong>, and<strong class="uicontrol" lwc-3eigj2skqo3=""> Unlimited</strong> Editions where Financial Service Cloud and Insurance Brokerage are enabled.</td></tr></tbody></table>

Modeling the structure involves creating product component groups for each benefit, and creating product classifications for each component group. After the classifications are ready, add attributes definitions and assign them to the classifications. The last step is to create benefit products and add them to the product component group. For the detailed coverage product structure that you need to create, see [Plan Benefits Sample Information](https://help.salesforce.com/s/articleView?id=ind.insurance_brokerage_product_model_sample_benefits_information.htm&language=en_US&type=5 "Use the plan benefits information to model the medical, dental, and vision coverage products under the Employee Benefits root product.").

-   **[Create Product Component Groups for Medical Product](https://help.salesforce.com/s/articleView?id=ind.insurance_brokerage_product_model_pcg_medical.htm&language=en_US&type=5)**  
    Create functional structures to organize benefits for Medical products under specific groups using the product component groups.
-   **[Create a Product Classification](https://help.salesforce.com/s/articleView?id=ind.insurance_brokerage_product_model_product_classification_create.htm&language=en_US&type=5)**  
    Create a product classification across benefit specifications. This way, you can create a single product classification that includes all the attributes you need, and then use that product classification to create multiple benefit specifications.
-   **[Create an Attribute Definition with Currency and Percent Data Type](https://help.salesforce.com/s/articleView?id=ind.insurance_brokerage_product_model_attribute_definition_currency_percent.htm&language=en_US&type=5)**  
    Create an attribute to describe the product properties. Create all attribute definitions that have the data type as currency or percent. For example, Deductible, Copay, and OOP Max have currency as data type and Coinsurance has percent as data type.
-   **[Create Attribute Definition with Picklist Data Type](https://help.salesforce.com/s/articleView?id=ind.insurance_brokerage_product_model_attribute_definition_picklist.htm&language=en_US&type=5)**  
    Create a Deductible Waiver attribute definition that’s a picklist with Deductible Waived and Deductible not waived picklist values. Create all attribute definitions with picklist data type. For example, Emergency Room Copay Waived and Retail Copay Multiplier.
-   **[Assign the Attribute to the Product Classification](https://help.salesforce.com/s/articleView?id=ind.insurance_brokerage_product_model_assign_attribute_pcg.htm&language=en_US&type=5)**  
    After creating a product classification and attribute, assign the attribute to the product classification. For example, assign the Deductibles attribute to the Annual Deductibles product classification.
-   **[Create and Add Benefit Product to the Product Component Group](https://help.salesforce.com/s/articleView?id=ind.insurance_brokerage_product_model_benefit_product_create_add_pcg.htm&language=en_US&type=5)**  
    Create the benefit products for each product classification and then add them to the product component group. For example, create Annual Deductible/ Individual and Annual Deductible/ Family benefit products under Annual Deductible product classification and then add them to the General Plan Information Product Component Group.

Did this article solve your issue?

Let us know so we can improve!

YesNo