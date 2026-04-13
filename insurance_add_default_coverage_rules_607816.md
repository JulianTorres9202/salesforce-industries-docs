---
title: "Add Default Coverage Rules"
source: "https://help.salesforce.com/s/articleView?id=ind.insurance_add_default_coverage_rules_607816.htm&language=en_US&type=5"
scraped: "2026-04-13"
filter: "ind.insurance_"
---# Add Default Coverage Rules

Add Default Coverage Rules[](https://help.salesforce.com/s?language=en_US)

You are here:

1.  [Salesforce Help](/s/?language=en_US)
2.  [Docs](/s/products?language=en_US)
3.  [Digital Insurance](https://help.salesforce.com/s/articleView?id=ind.insurance_admin_standard.htm&language=en_US&type=5)

# Add Default Coverage Rules

To specify when an optional coverage is selected by default, use default coverage rules. For example, for Roadside Assistance optional coverage in an Auto policy, you can create a rule that makes Roadside Assistance selected by default when Comprehensive coverage is selected.

Note

Users can manually deselect coverages selected by these rules.

The syntax for Default coverage rules is:

<productCode.attributeCode> <operator> < literal and/or function>

Here's what the example rule looks like:

AUTO.COMPREHENSIVE = TRUE

[](https://help.salesforce.com/s?language=en_US)These services used in OmniScripts and Integration Procedures run Default Selected coverage rules:

[](https://help.salesforce.com/s?language=en_US)

-   [InsProductService:getRatedProducts](https://help.salesforce.com/s/articleView?id=ind.insurance_insproductservice__getratedproducts.htm&language=en_US&type=5 "Use this service to get an array of one or more products, priced using rating procedures attached to those products. This service also includes extra features such as tax and fee calculations, filtering, and performance optimization.")
    
    Runs these rules by default. No need to set any remote options.
    
-   [InsProductService: runRules](https://help.salesforce.com/s/articleView?id=ind.insurance_insproductservice__runrules.htm&language=en_US&type=5 "Use this service to run rules on a product without repricing that product.")
    
    Set `runDefaultSelected` = `true`.
    

[](https://help.salesforce.com/s?language=en_US)Default coverage rules run on the Quote UI when you:

-   Add a root product.
    
-   Add an insured item.
    

Did this article solve your issue?

Let us know so we can improve!

YesNo