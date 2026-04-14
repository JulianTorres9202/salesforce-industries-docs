---
title: "Underwriting (Workflow) Rules"
source: "https://help.salesforce.com/s/articleView?id=ind.insurance_underwritingworkflowrules_607457.htm&language=en_US&type=5"
scraped: "2026-04-14"
filter: "ind.insurance_"
---# Underwriting (Workflow) Rules

Underwriting (Workflow) Rules[](https://help.salesforce.com/s?language=en_US)

You are here:

1.  [Salesforce Help](/s/?language=en_US)
2.  [Docs](/s/products?language=en_US)
3.  [Digital Insurance](https://help.salesforce.com/s/articleView?id=ind.insurance_admin_standard.htm&language=en_US&type=5)

# Underwriting (Workflow) Rules

Underwriting (workflow) rules can help automate your business processes as quotes get issued as policies, when policies become eligible for mid-term adjustments (MTAs), when it's time to renew or cancel a policy, and for claims processing.

Although the UI calls them **Underwriting Rules**, in fact, this type of rule can be used in any scenario when a record advances from one state to another, such as from Draft to Underwriting Review, or from Draft to Adjuster Review, or from Review to Issued.

For example, you can create an underwriting rule that automatically declines quotes that meet specified criteria. If any rule evaluates to true, the record's state transitions to declined and the specified action runs.

[](https://help.salesforce.com/s?language=en_US)Here are some examples of underwriting rules:

| 
Scenario

 | 

Applicable Type

 | 

Transition Name

 | 

True Action

 | 

Rule Scope

 | 

Expression

 |
| --- | --- | --- | --- | --- | --- |
| 

Automatically decline a quote if the vessel is over 25 years old.

 | 

Quote

 | 

Submit > Decline

 | 

Decline Quote

 | 

Watercraft

 | 

WC.wcAge > 25

 |
| 

Automatically decline a quote if the vessel is taken more than 100 miles off shore.

 | 

Quote

 | 

Submit > Decline

 | 

Decline Quote

 | 

Watercraft

 | 

WC.wcDistance > 100

 |
| 

Refer to underwriting if an operator's licensing points is greater than or equal to five.

 | 

Quote

 | 

Submit > Underwriting

 | 

Refer to Underwriting.

 | 

Pilot

 | 

wcOperator.opPoints >= 5

 |
| 

Refer to underwriting if the vessel is taken 50 or more miles off shore.

 | 

Quote

 | 

Submit > Underwriting

 | 

Refer to Underwriting

 | 

Watercraft

 | 

WC.wcDistance >= 50

 |

The system logs underwriting (workflow) rules after they're run, and displays them in the Rules Log.

[](https://help.salesforce.com/s?language=en_US)

## Services and UIs that Run Underwriting Rules

Many Insurance and Vlocity Health services run underwriting rules. You can add these services to OmniScripts and Integration Procedures when you want the rules to run.

These are the invoke rules services:

-   [InsClaimService:invokeProductRules](https://help.salesforce.com/s/articleView?id=ind.insurance_insclaimservice__invokeproductrules.htm&language=en_US&type=5 "Use this service in claim flows to invoke underwriting rules you've added to a product.")
    
-   [InsContractService:invokeProductRules](https://help.salesforce.com/s/articleView?id=ind.insurance_inscontractservice__invokeproductrules.htm&language=en_US&type=5 "Use this service in contract flows to invoke underwriting rules you've added to a product.")
    
-   [InsPolicyService:invokeProductRules](https://help.salesforce.com/s/articleView?id=ind.insurance_inspolicyservice__invokeproductrules.htm&language=en_US&type=5 "Use this service with a policy to invoke underwriting rules you've added to a product.")
    
-   [InsQuoteService:invokeProductRules](https://help.salesforce.com/s/articleView?id=ind.insurance_insquoteservice__invokeproductrules.htm&language=en_US&type=5 "Use this service in quote flows to invoke underwriting rules you've added to a product.")
    

These LWC-based UIs also call services that run underwriting (workflow) rules:

-   Quote
    
-   Claim
    

## Limiting the Scope of Rules for Quotes and Insurance Policies

For quotes and insurance policies, use Rule Scope to apply an underwriting rule to a particular type of insured item or insured party. Your processes run more efficiently and accurately because each rule runs for exactly the right line items in a quote or insurance policy.

For example, if a root product includes Auto (1) and Driver (2) as insured items, underwriting rules for that product can have a rule scope of either Auto or Driver (3). If you add a rule that evaluates the monetary value of an automobile, define its Rule Scope as Auto so that it runs just for automobiles, not for drivers.

If Rule Scope is None, the default rule scope is the root product, and the rule behaves the same way as it did in Summer ‘22 and earlier.

If a quote or insurance policy includes multiple root products, rules defined for each root product run separately.

[](https://help.salesforce.com/s?language=en_US)

## Underwriting Rules by Instance

For quotes and insurance policies, set up underwriting rules at the root product level. Specify Rule Scope to apply the rules to particular types of insured items or insured parties. By limiting the scope of the rule, you limit the number of times the rule runs, which improves performance.

For example, an auto insurance policy has two cars, a Toyota and a Honda. Kelly drives one of the cars, and the other car is kept in an insured garage.

With Rule Scope defined as:

-   Driver, the rule runs for Kelly.
    
-   Car, the rule runs for the Toyota and the Honda.
    
-   None, the rule runs for Kelly and the Garage, taking into account additional attribute data from their parent instances.
    

For assets, contracts, insurance claims, and claim coverages, underwriting rules are invoked on a per-instance basis. You still set up underwriting rules at the root product level. For multi-instance scenarios, make sure the instance key is populated on the insured item or insured party.

-   **[Create an Underwriting Rule](https://help.salesforce.com/s/articleView?id=ind.insurance_create_an_underwriting_rule_607603.htm&language=en_US&type=5)**  
    Use underwriting rules to automate quoting, policy, and claims management business processes.For quotes and policies, apply underwriting rules to specific types of insured items or parties, and trigger unique messaging and actions based on whether each rule passes or fails.

Did this article solve your issue?

Let us know so we can improve!

YesNo