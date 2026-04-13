---
title: "Add Required Coverage Rules"
source: "https://help.salesforce.com/s/articleView?id=ind.insurance_add_required_coverage_rules_607787.htm&language=en_US&type=5"
scraped: "2026-04-13"
filter: "ind.insurance_"
---# Add Required Coverage Rules

Add Required Coverage Rules[](https://help.salesforce.com/s?language=en_US)

You are here:

1.  [Salesforce Help](/s/?language=en_US)
2.  [Docs](/s/products?language=en_US)
3.  [Digital Insurance](https://help.salesforce.com/s/articleView?id=ind.insurance_admin_standard.htm&language=en_US&type=5)

# Add Required Coverage Rules

You can create rules that describe the situations where some insurance policies require a specific optional coverage. For example, an Auto policy requires Collision Deductible Waiver coverage when Comprehensive coverage is selected.

The syntax for required coverage rules is:

<productCode.attributeCode> <operator> < literal and/or function>

Here's what the example rule looks like:

The following services used in OmniScripts and Integration Procedures run required coverage rules.

[](https://help.salesforce.com/s?language=en_US)

-   [InsProductService:getRatedProducts](https://help.salesforce.com/s/articleView?id=ind.insurance_insproductservice__getratedproducts.htm&language=en_US&type=5 "Use this service to get an array of one or more products, priced using rating procedures attached to those products. This service also includes extra features such as tax and fee calculations, filtering, and performance optimization.")
    
    Runs these rules by default. No need to set any remote options.
    
-   [InsProductService: runRules](https://help.salesforce.com/s/articleView?id=ind.insurance_insproductservice__runrules.htm&language=en_US&type=5 "Use this service to run rules on a product without repricing that product.")
    
    Set `runRequiredCoverage` = `true`.
    

[](https://help.salesforce.com/s?language=en_US)Required coverage rules are also run on the Quote UI when you add a root product.

[](https://help.salesforce.com/s?language=en_US)To learn more, see [Single Root Quoting](https://help.salesforce.com/s/articleView?id=ind.insurance_single_root_quoting_612298.htm&language=en_US&type=5 "You can configure quotes directly in the Quote object, without any need to go through an OmniScript flow.").

Did this article solve your issue?

Let us know so we can improve!

YesNo