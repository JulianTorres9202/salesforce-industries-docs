---
title: "Add Optional Coverage Relationship Rules"
source: "https://help.salesforce.com/s/articleView?id=ind.insurance_add_optional_coverage_relationship_rules_607925.htm&language=en_US&type=5"
scraped: "2026-04-13"
filter: "ind.insurance_"
---# Add Optional Coverage Relationship Rules

Add Optional Coverage Relationship Rules[](https://help.salesforce.com/s?language=en_US)

You are here:

1.  [Salesforce Help](/s/?language=en_US)
2.  [Docs](/s/products?language=en_US)
3.  [Digital Insurance](https://help.salesforce.com/s/articleView?id=ind.insurance_admin_standard.htm&language=en_US&type=5)

# Add Optional Coverage Relationship Rules

Use optional coverage relationship rules for optional coverages that are either dependent on other optional coverages, or mutually exclusive of other optional coverages.

For example, if your optional CyberSecurity coverage requires that optional Electronics coverage also be selected, the relationship looks like this:

[](https://help.salesforce.com/s?language=en_US)The following services used in OmniScripts and Integration Procedures run optional coverage relationship rules.

[](https://help.salesforce.com/s?language=en_US)

-   [InsProductService:getRatedProducts](https://help.salesforce.com/s/articleView?id=ind.insurance_insproductservice__getratedproducts.htm&language=en_US&type=5 "Use this service to get an array of one or more products, priced using rating procedures attached to those products. This service also includes extra features such as tax and fee calculations, filtering, and performance optimization.")
    
    Set `evalOptionalCoverageRelationship` to `true`.
    
-   [InsProductService:repriceProduct](https://help.salesforce.com/s/articleView?id=ind.insurance_insproductservice__repriceproduct.htm&language=en_US&type=5 "Use this service to price one product using the rating procedure attached to that product. This service is usually called when a user selects a product and customizes its coverage.")
    
    [](https://help.salesforce.com/s?language=en_US)Set `evalOptionalCoverageRelationship` to `true`.
    
-   [](https://help.salesforce.com/s?language=en_US)
    
    [InsProductService: runRules](https://help.salesforce.com/s/articleView?id=ind.insurance_insproductservice__runrules.htm&language=en_US&type=5 "Use this service to run rules on a product without repricing that product.")
    
    Set `evalOptionalCoverageRelationship` = `true`.
    

1.  At the top of the Coverages tab, click **Relationships**.
2.  Click **Add Relationship**.
3.  In the left field, choose the coverage that has a dependent relationship.
4.  In the middle field, choose the relationship.
5.  In the right field, choose the related coverage.

Did this article solve your issue?

Let us know so we can improve!

YesNo