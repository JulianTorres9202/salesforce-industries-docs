---
title: "Rules for Auto Products"
source: "https://help.salesforce.com/s/articleView?id=ind.insurance_rules_for_auto_products_omnistudio.htm&language=en_US&type=5"
scraped: "2026-04-14"
filter: "ind.insurance_"
---# Rules for Auto Products

Rules for Auto Products[](https://help.salesforce.com/s?language=en_US)

You are here:

1.  [Salesforce Help](/s/?language=en_US)
2.  [Docs](/s/products?language=en_US)
3.  [Digital Insurance](https://help.salesforce.com/s/articleView?id=ind.insurance_admin_standard.htm&language=en_US&type=5)

# Rules for Auto Products

The Multi Auto product includes a number of rules.

-   **[Eligibility Rules](https://help.salesforce.com/s/articleView?id=ind.insurance_eligibility_rules_omnistudio.htm&language=en_US&type=5)**  
    The Multi Auto product model does not include any Eligibility Rules. If you want to create eligibility rules for your auto product models, see [Create Product Eligibility Rules](https://help.salesforce.com/s/articleView?id=ind.insurance_create_product_eligibility_rules_607661.htm&language=en_US&type=5 "Insurance uses eligibility rules to help determine what insurance products and optional coverages a customer is eligible for. You can use eligibility rules in the quote process to screen out insurance products and optional coverages that a potential customer doesn't qualify for. For example, you can create an eligibility rule for a Medicare supplement insurance product that screens out anyone under the age of 65.")
-   **[Workflow (Underwriting) Rules for the Multi Auto Product Model](https://help.salesforce.com/s/articleView?id=ind.insurance_workflow_underwriting_rules_omnistudio.htm&language=en_US&type=5)**  
    Multi Auto includes several workflow (underwriting) rules. These get run towards the end of the quoting process by the InsQuoteService:invokeProductRules service. This service is called by an integration procedure in the Auto quote OmniScript and by the Lightning Web Component in the Quote UI.
-   **[Optional Coverage Rules for Auto Products](https://help.salesforce.com/s/articleView?id=ind.insurance_optional_coverage_rules_for_auto_products_omnistudio.htm&language=en_US&type=5)**  
    The Multi Auto product does not include any optional coverage rules.
-   **[Attribute Rules for Auto Products](https://help.salesforce.com/s/articleView?id=ind.insurance_attribute_rules_for_auto_products_with_omnistudio.htm&language=en_US&type=5)**  
    The Multi Auto product includes the following attribute rules:

Did this article solve your issue?

Let us know so we can improve!

YesNo