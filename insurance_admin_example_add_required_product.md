---
title: "Example: Automatically add a Required Product"
source: "https://help.salesforce.com/s/articleView?id=ind.insurance_admin_example_add_required_product.htm&language=en_US&type=5"
scraped: "2026-04-13"
filter: "ind.insurance_"
---# Example: Automatically add a Required Product

Example: Automatically add a Required Product[](https://help.salesforce.com/s?language=en_US)

You are here:

1.  [Salesforce Help](/s/?language=en_US)
2.  [Docs](/s/products?language=en_US)
3.  [Digital Insurance](https://help.salesforce.com/s/articleView?id=ind.insurance_admin_standard.htm&language=en_US&type=5)

# Example: Automatically add a Required Product

The admin wants to automatically add comprehensive coverage to the quote if the driver belongs to the state of Texas and prevent users from removing it.

To meet this requirement, the admin creates a RequiredCoverage rule that uses the Auto-Add action and enables the Lock option in the Rule Criteria instead of using the Require action.

1.  In the New Configuration Rule page, specify these details:
    
    |  |  |
    | --- | --- |
    | Name | RequiredCoverage |
    | Start Date and Time | Current date |
    | Status | Active |
    
2.  Click **Next**.
3.  In the Rule Criteria page, specify these details:
    
    |  |  |
    | --- | --- |
    | Scope Details | [](https://help.salesforce.com/s?language=en_US)
    -   Rule Scope: Bundle
    -   Product Bundle: Auto
    
     |
    | Conditions | [](https://help.salesforce.com/s?language=en_US)
    
    -   Resource: Product
    -   Operator: Equals
    -   Value: Driver
    -   Attribute: AccountState
    -   Operator: Equals
    -   Value: Texas
    
     |
    | Actions | [](https://help.salesforce.com/s?language=en_US)
    
    -   Action: Auto-Add
    -   Product: Comprehensive
    -   Lock: Selected
    -   Message Type: Informational
    -   Message: Auto-Added the Comprehensive coverage.
    
     |
    
4.  Save your changes.

Did this article solve your issue?

Let us know so we can improve!

YesNo