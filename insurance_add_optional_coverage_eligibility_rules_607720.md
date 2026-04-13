---
title: "Add Optional Coverage Eligibility Rules"
source: "https://help.salesforce.com/s/articleView?id=ind.insurance_add_optional_coverage_eligibility_rules_607720.htm&language=en_US&type=5"
scraped: "2026-04-13"
filter: "ind.insurance_"
---# Add Optional Coverage Eligibility Rules

Add Optional Coverage Eligibility Rules[](https://help.salesforce.com/s?language=en_US)

You are here:

1.  [Salesforce Help](/s/?language=en_US)
2.  [Docs](/s/products?language=en_US)
3.  [Digital Insurance](https://help.salesforce.com/s/articleView?id=ind.insurance_admin_standard.htm&language=en_US&type=5)

# Add Optional Coverage Eligibility Rules

When an optional coverage eligibility rule is invoked, the customer or agent sees only the available insurance products that meet this rule (that is, when the rule returns true).

In this example of an optional coverage eligibility rule, a small business insurance plan includes an optional coverage for business property. To be eligible for this optional coverage, the business property must be worth less than $1,000,000. The eligibility rule for this coverage looks like this:

BP.limitBusProperty < 1000000

The following services used in OmniScripts and Integration Procedures run optional coverage eligibility rules.

-   [InsProductService:getRatedProducts](https://help.salesforce.com/s/articleView?id=ind.insurance_insproductservice__getratedproducts.htm&language=en_US&type=5 "Use this service to get an array of one or more products, priced using rating procedures attached to those products. This service also includes extra features such as tax and fee calculations, filtering, and performance optimization.")
    
    Runs these rules by default. No need to set any remote options.
    
-   [InsProductService: runRules](https://help.salesforce.com/s/articleView?id=ind.insurance_insproductservice__runrules.htm&language=en_US&type=5 "Use this service to run rules on a product without repricing that product.")
    
    Set `runEligibility` = `true` to run optional coverage eligibility rules.
    
-   [InsQuoteService:getQuoteDetail](https://help.salesforce.com/s/articleView?id=ind.insurance_insquoteservice__getquotedetail.htm&language=en_US&type=5 "Use this service to get all of the quote details as JSON.")
    
    Runs these rules by default. No need to set any remote options.
    

Optional coverage eligibility rules are also run on the Quote UI when you:

-   Add an insured item.
    
-   Edit an insured item.
    

Note

When you enter expressions into optional coverage rules, you'll see `isSelected` appear in the type-ahead for all five kinds of rules.

But `isSelected` is only evaluated on validation rules.

1.  On the insurance product page, click **Coverages**.
2.  Find the coverage you need to add an eligibility rule to. Make sure that **Optional** is selected.
3.  Select **Eligibility Rules**.
4.  In the Expression field, enter a formula to create your eligibility rule or rules.
    
    [](https://help.salesforce.com/s?language=en_US)The syntax for eligibility rules is:
    
    [](https://help.salesforce.com/s?language=en_US)<productCode.attributeCode> <operator> < literal and/or function>
    
    To enter more than one eligibility rule, use `AND` or `OR` to separate the rules.
    
5.  (Optional) Enter a note about this rule to tell other Vlocity administrators about this rule. Click the bubble icon and enter text. The note saves automatically.
6.  Click **Save**.

Did this article solve your issue?

Let us know so we can improve!

YesNo