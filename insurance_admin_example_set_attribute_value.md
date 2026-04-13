---
title: "Example: Set an Attribute Value"
source: "https://help.salesforce.com/s/articleView?id=ind.insurance_admin_example_set_attribute_value.htm&language=en_US&type=5"
scraped: "2026-04-13"
filter: "ind.insurance_"
---# Example: Set an Attribute Value

Example: Set an Attribute Value[](https://help.salesforce.com/s?language=en_US)

You are here:

1.  [Salesforce Help](/s/?language=en_US)
2.  [Docs](/s/products?language=en_US)
3.  [Digital Insurance](https://help.salesforce.com/s/articleView?id=ind.insurance_admin_standard.htm&language=en_US&type=5)

# Example: Set an Attribute Value

The admin creates a SetAttribute rule to set the Collision Coverage Deductible to $500 when the Collision Coverage BI Person Limit exceeds $10,000.

[](https://help.salesforce.com/s?language=en_US)

1.  In the New Configuration Rule page, specify these details:
    
    |  |  |
    | --- | --- |
    | Name | SetAttribute |
    | Start Date and Time | Current date |
    | Status | Active |
    
2.  Click **Next**.
3.  In the Rule Criteria page, specify these details:
    
    |  |  |
    | --- | --- |
    | Scope Details | [](https://help.salesforce.com/s?language=en_US)
    -   Rule Scope: Bundle
    -   Product Bundle: Motor Vehicle Bundle
    
     |
    | Conditions | [](https://help.salesforce.com/s?language=en_US)
    
    -   Resource: Product
    -   Operator: Equals
    -   Value: Collision
    -   Attribute: BI Person Limit
    -   Operator: Greater Than
    -   Value: $10000
    
     |
    | Actions | [](https://help.salesforce.com/s?language=en_US)
    
    -   Action: Set Attribute
    -   Product: Collision
    -   Attribute: Collision Deductable
    -   Operator: Equals
    -   Value: $500
    -   Message Type: Informational
    -   Message: Collision Coverage Deductible is set to $500 because the Collision Coverage BI Person Limit exceeds $10,000.
    
     |
    
4.  Save your changes.

Did this article solve your issue?

Let us know so we can improve!

YesNo