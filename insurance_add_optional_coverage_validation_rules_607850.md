---
title: "Add Optional Coverage Validation Rules"
source: "https://help.salesforce.com/s/articleView?id=ind.insurance_add_optional_coverage_validation_rules_607850.htm&language=en_US&type=5"
scraped: "2026-04-13"
filter: "ind.insurance_"
---# Add Optional Coverage Validation Rules

Add Optional Coverage Validation Rules[](https://help.salesforce.com/s?language=en_US)

You are here:

1.  [Salesforce Help](/s/?language=en_US)
2.  [Docs](/s/products?language=en_US)
3.  [Digital Insurance](https://help.salesforce.com/s/articleView?id=ind.insurance_admin_standard.htm&language=en_US&type=5)

# Add Optional Coverage Validation Rules

To validate whether an optional coverage can be selected in a quote or policy, create optional coverage validation rules. These rules can display custom error messages that tell your users how to fix a problem that keeps them from adding an optional coverage. For example, a rule can ensure that a certain optional coverage isn't selected if a different optional coverage is already selected.

[](https://help.salesforce.com/s?language=en_US)The following services used in OmniScripts and Integration Procedures run optional coverage validation rules.

[](https://help.salesforce.com/s?language=en_US)

-   [InsProductService:getRatedProducts](https://help.salesforce.com/s/articleView?id=ind.insurance_insproductservice__getratedproducts.htm&language=en_US&type=5 "Use this service to get an array of one or more products, priced using rating procedures attached to those products. This service also includes extra features such as tax and fee calculations, filtering, and performance optimization.")
    
    Set `validateCoverageSelection` to `true` to run optional coverage validation rules.
    
-   [InsProductService:repriceProduct](https://help.salesforce.com/s/articleView?id=ind.insurance_insproductservice__repriceproduct.htm&language=en_US&type=5 "Use this service to price one product using the rating procedure attached to that product. This service is usually called when a user selects a product and customizes its coverage.")
    
    [](https://help.salesforce.com/s?language=en_US)Set `validateCoverageSelection` to `true` to run optional coverage validation rules.
    
-   [](https://help.salesforce.com/s?language=en_US)
    
    [InsProductService: runRules](https://help.salesforce.com/s/articleView?id=ind.insurance_insproductservice__runrules.htm&language=en_US&type=5 "Use this service to run rules on a product without repricing that product.")
    
    Set `validateCoverageSelection` = `true` to run optional coverage validation rules.
    

1.  Go to the Coverages tab on the policy Product page.
2.  On the coverage marked Optional, click the Rules icon.
3.  Enter the following:
    
    -   Expression
        
        The conditions under which Vlocity triggers this rule.
        
        You can use root product, coverage, and insured item attribute values in optional coverage validation rules.
        
        Note
        
        If you use `isSelected` in the expressions for validation rules, the rules are evaluated by the following services:
        
        -   [InsProductService:getRatedProducts](https://help.salesforce.com/s/articleView?id=ind.insurance_insproductservice__getratedproducts.htm&language=en_US&type=5 "Use this service to get an array of one or more products, priced using rating procedures attached to those products. This service also includes extra features such as tax and fee calculations, filtering, and performance optimization.")
            
        -   [InsProductService:repriceProduct](https://help.salesforce.com/s/articleView?id=ind.insurance_insproductservice__repriceproduct.htm&language=en_US&type=5 "Use this service to price one product using the rating procedure attached to that product. This service is usually called when a user selects a product and customizes its coverage.")
            
        -   [InsProductService: runRules](https://help.salesforce.com/s/articleView?id=ind.insurance_insproductservice__runrules.htm&language=en_US&type=5 "Use this service to run rules on a product without repricing that product.")
            
        
    -   Severity
        
        How serious this issue is.
        
        Use an Error if you want to stop OmniScript users from proceeding with tasks for optional coverage validation rules. When a user triggers an Error message, they see the message text and are blocked from continuing with the task until they go back and fix the error.
        
        For example, if you set a rule that triggers an Error if a user enters a Policy Deductible > $5000, a user who enters $6000 must go back and enter $5000 or less in the Policy Deductible field before they can move forward.
        
        Note
        
        All Severity settings display messages in the same color and position.
        
    -   Message
        
        A well-formed message that tells your users what the problem is and how to fix it (for an error) or what's going on (for information only).
        
    
    Here's an example of the syntax:
    
4.  Update OmniScripts that use the validation rules and run tests.
    1.  In an OmniScript, for any remote action or selectable item that uses the [InsPolicyService: repriceProduct](https://help.salesforce.com/s/articleView?id=ind.insurance_insproductservice__repriceproduct.htm&language=en_US&type=5 "Use this service to price one product using the rating procedure attached to that product. This service is usually called when a user selects a product and customizes its coverage.") service and needs these rules to trigger, set the remote option `validateCoverageSelection` to `true`.
    2.  Go through the preview of the OmniScript.
    3.  Select optional coverages that have validation rules defined.
    4.  Verify that the message you set appears when you meet conditions of the validation rules.

Did this article solve your issue?

Let us know so we can improve!

YesNo