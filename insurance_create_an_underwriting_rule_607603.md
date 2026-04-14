---
title: "Create an Underwriting Rule"
source: "https://help.salesforce.com/s/articleView?id=ind.insurance_create_an_underwriting_rule_607603.htm&language=en_US&type=5"
scraped: "2026-04-14"
filter: "ind.insurance_"
---# Create an Underwriting Rule

Create an Underwriting Rule[](https://help.salesforce.com/s?language=en_US)

You are here:

1.  [Salesforce Help](/s/?language=en_US)
2.  [Docs](/s/products?language=en_US)
3.  [Digital Insurance](https://help.salesforce.com/s/articleView?id=ind.insurance_admin_standard.htm&language=en_US&type=5)

# Create an Underwriting Rule

Use underwriting rules to automate quoting, policy, and claims management business processes.For quotes and policies, apply underwriting rules to specific types of insured items or parties, and trigger unique messaging and actions based on whether each rule passes or fails.

Note For quotes and insurance policies, set up underwriting rules at the root product level and use Rule Scope to apply a rule to a particular type of insured item or insured party. With Rule Scope defined at the root product level, there’s no need to add underwriting rules to child specs.

1.  From the root product spec page, click the **Rules** tab.
2.  In the Underwriting section, click **Add Underwriting Rule**.
3.  Enter a unique **Name** for the underwriting rule.
4.  Enter the **Applicable Type** of object the rule runs for: Asset, Contract, or Quote, or for Insurance Industries Extension, InsuranceClaim\_\_c, ClaimCoverage\_\_c, or InsurancePolicy.
5.  Enter a **Transition Name** that specifies the object’s transition from one state to another if the rule evaluates to true.
    
    For example, a quote can move from Approved > Issued. The transitions available come from the your object's state model.
    
6.  To run the rule for a particular type of insured item or insured party in a quote or insurance policy, enter **Rule Scope**.
    
    The rule scopes available come from the insured items added to the root product.
    
    For example, if a root product includes Auto and Driver as insured items, an underwriting rule for that product can have a rule scope of either Auto or Driver. If you add a rule that evaluates the monetary value of an automobile, define its Rule Scope as Auto so that it runs just for automobiles, not for drivers.
    
    Rule scope is available as of Winter '23. To see Rule Scope on a product spec page, you must install product model cards (**VlocityInsProductModelCards**). These cards are included in the Insurance Cards DataPacks installed by the [Vlocity Installation Assistant](https://help.salesforce.com/s/articleView?id=ind.insurance_complete_vlocity_installation_assistant_steps.htm&language=en_US&type=5 "To complete the installation and the configuration of Insurance do all the tasks marked New Installation Only and all the tasks not specially marked."), or you can install and activate them manually in [Vlocity Cards](https://help.salesforce.com/s/articleView?id=xcloud.os_installing_and_activating_vlocity_templates_and_cards.htm&language=en_US&type=5).
    
7.  To invoke a Vlocity Action based on whether the rule passes or fails, select a **True Action**, a **False Action**, or both. The actions available depend on the selected Transition Name.
8.  To trigger a message based on whether the rule passes or fails, enter a **Success Message**, a **Failure Message**, or both.
9.  Enter an Expression that evaluates characteristics of the applicable type of object.
    
    Whether the expression evaluates to true or false, the appropriate Action is triggered, and the defined Message is displayed.
    
    Important Make sure the expression uses eligible fields within rule scope. No validation is performed on the expression, so if it references fields that are out of scope, it won’t work as expected.
    
10.  To enter a description of the rule, click the bubble icon and enter text in the pop-up. Your notes save automatically.
     
     Your notes save automatically.
     
11.  To start applying the rule to the applicable object, select the Active checkbox.

Did this article solve your issue?

Let us know so we can improve!

YesNo