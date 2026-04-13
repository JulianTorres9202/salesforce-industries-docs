---
title: "Example: Create a User Profile-Based Rule"
source: "https://help.salesforce.com/s/articleView?id=ind.insurance_admin_example_create_user_profile_rule.htm&language=en_US&type=5"
scraped: "2026-04-13"
filter: "ind.insurance_"
---# Example: Create a User Profile-Based Rule

Example: Create a User Profile-Based Rule[](https://help.salesforce.com/s?language=en_US)

You are here:

1.  [Salesforce Help](/s/?language=en_US)
2.  [Docs](/s/products?language=en_US)
3.  [Digital Insurance](https://help.salesforce.com/s/articleView?id=ind.insurance_admin_standard.htm&language=en_US&type=5)

# Example: Create a User Profile-Based Rule

The admin creates a UserProfileRule to automatically set the Comprehensive Coverage Deductible to $250 when a user with the Broker profile selects Comprehensive Coverage.

[](https://help.salesforce.com/s?language=en_US)

1.  In the New Configuration Rule page, specify these details:
    
    |  |  |
    | --- | --- |
    | Name | UserProfileRule |
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
    -   Value: Comprehensive
    -   Field: UserProfile
    -   Operator: Equals
    -   Value: Broker
    
     |
    | Actions | [](https://help.salesforce.com/s?language=en_US)
    
    -   Action: Set Attribute
    -   Product: Comprehensive
    -   Attribute: Comprehensive Deductible
    -   Operator: Equals
    -   Value: $250
    -   Message Type: Informational
    -   Message: The Comprehensive Deductible is set to $250 for the Broker profile.
    
     |
    
4.  Save your changes.

Did this article solve your issue?

Let us know so we can improve!

YesNo