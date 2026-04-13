---
title: "Set Up Product Qualification"
source: "https://help.salesforce.com/s/articleView?id=ind.insurance_admin_set_up_qualification_rules.htm&language=en_US&type=5"
scraped: "2026-04-13"
filter: "ind.insurance_"
---# Set Up Product Qualification

Set Up Product Qualification[](https://help.salesforce.com/s?language=en_US)

You are here:

1.  [Salesforce Help](/s/?language=en_US)
2.  [Docs](/s/products?language=en_US)
3.  [Digital Insurance](https://help.salesforce.com/s/articleView?id=ind.insurance_admin_standard.htm&language=en_US&type=5)

# Set Up Product Qualification

To make sure your users browse only qualified products in product catalog, you must create context definitions and decision tables for Product Catalog Management, create qualification rules and qualification rule procedure, and then configure product discovery settings.

### Required Editions

<table class="slds-table slds-table_bordered slds-m-bottom_small edition" lwc-3eigj2skqo3=""><colgroup lwc-3eigj2skqo3=""><col style="width:100%" lwc-3eigj2skqo3=""></colgroup><tbody lwc-3eigj2skqo3=""><tr class="" lwc-3eigj2skqo3=""><td style="vertical-align:top;" class="slds-cell-wrap" lwc-3eigj2skqo3="">Available in: Lightning Experience</td></tr><tr class="" lwc-3eigj2skqo3=""><td style="vertical-align:top;" class="slds-cell-wrap" lwc-3eigj2skqo3="">Available in: <strong lwc-3eigj2skqo3="">Enterprise</strong>, <strong lwc-3eigj2skqo3="">Unlimited</strong>, and <strong lwc-3eigj2skqo3="">Developer</strong> Editions of Digital Insurance Platform where Product Configuration is enabled with the Revenue Lifecycle Management add-on</td></tr></tbody></table>

1.  [Create context definitions for Product Catalog Management](https://help.salesforce.com/s/articleView?id=ind.product_catalog_context_definitions_for_product_catalog_management.htm&language=en_US&type=5).
    
    To ensure efficient data access to qualification procedures and the pricing procedure used in Product Discovery and Product Discovery APIs, create context definitions. To create a context definition, [extend the predefined ProductDiscoveryContext context definition](https://help.salesforce.com/s/articleView?id=ind.product_catalog_extend_productdiscoverycontext_context_definition.htm&language=en_US&type=5).
    
2.  [Create decision tables for Product Catalog Management](https://help.salesforce.com/s/articleView?id=ind.product_catalog_decision_tables_for_product_catalog_management.htm&language=en_US&type=5).
    
    A decision table contains the criteria used for qualification and disqualification of products and product categories. Create a decision table for every type of qualification and disqualification that you want to configure. For example, to specify criteria that determines product qualification and disqualification, create two decision tables: one for product qualification and another for product disqualification.
    
3.  [Create qualification rules](https://help.salesforce.com/s/articleView?id=ind.product_catalog_create_a_qual_rule_for_product.htm&language=en_US&type=5).
    
    Create rules that capture the values for the input criteria that a product or category must meet to be either qualified or disqualified. Even though users see only the qualified products, they can filter both qualified and disqualified products.
    
4.  [Create qualification rule procedure](https://help.salesforce.com/s/articleView?id=ind.product_catalog_create_qual_rule_procedure_for_product.htm&language=en_US&type=5).
    
    A qualification rule procedure has a series of qualification procedure elements that evaluate the rules in a decision table. The procedure accepts a list of categories and products as input and returns the list of products and categories along with their qualification or disqualification information.
    
5.  Configure product discovery settings to populate the information that users see when they use Product Discovery.[](https://help.salesforce.com/s?language=en_US)
    1.  From Setup, in the Quick Find box, find and select **Product Discovery Settings**.
    2.  In Select Context Definition, select ProductDiscoveryContext or the extended context definition.
    3.  Turn on **Qualification Procedure**, and then select the qualification procedure.

-   **[Verification of Qualified Products](https://help.salesforce.com/s/articleView?id=ind.insurance_admin_verify_qualified_products.htm&language=en_US&type=5)**  
    Browse and add qualified products to quotes.

#### See Also

-   [Simulate and Activate a Qualification Rule Procedure](https://help.salesforce.com/s/articleView?id=ind.product_catalog_simulate_and_activate_a_qualification_rule_procedure.htm&language=en_US&type=5)

Did this article solve your issue?

Let us know so we can improve!

YesNo