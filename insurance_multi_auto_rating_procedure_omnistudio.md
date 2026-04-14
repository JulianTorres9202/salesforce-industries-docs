---
title: "Multi Auto Rating Procedure"
source: "https://help.salesforce.com/s/articleView?id=ind.insurance_multi_auto_rating_procedure_omnistudio.htm&language=en_US&type=5"
scraped: "2026-04-14"
filter: "ind.insurance_"
---# Multi Auto Rating Procedure

Multi Auto Rating Procedure[](https://help.salesforce.com/s?language=en_US)

You are here:

1.  [Salesforce Help](/s/?language=en_US)
2.  [Docs](/s/products?language=en_US)
3.  [Digital Insurance](https://help.salesforce.com/s/articleView?id=ind.insurance_admin_standard.htm&language=en_US&type=5)

# Multi Auto Rating Procedure

A rating is a risk-based calculation of a premium based on a set of input characteristics. We use rating procedures to price insurance products and health plans. You'll set up, map, and implement rating procedures for all your products and plans.

To learn the basics about Vlocity Insurance rating procedures for pricing insurance products, see [](https://help.salesforce.com/s?language=en_US)[Rating Procedures](https://help.salesforce.com/s/articleView?id=ind.insurance_rating_procedures_super.htm&language=en_US&type=5 "Rating procedures make it possible to price insurance products. Set up, map, and implement rating procedures for all your products and plans.").

Here's how the Multi Auto rating procedure rates these things at the highest level:

-   **[Integration Procedure for Multi Auto](https://help.salesforce.com/s/articleView?id=ind.insurance_integration_procedure_for_multi_auto_omnistudio.htm&language=en_US&type=5)**  
    To rate the Multi Auto insurance product, we use this Integration procedure:
-   **[autoRateDrivers Expression Set](https://help.salesforce.com/s/articleView?id=ind.insurance_autoratedrivers_expression_set_omnistudio.htm&language=en_US&type=5)**  
    This expression set rates all drivers to be insured on a per-vehicle basis. That is, it rates each driver attached to each vehicle.
-   **[autoRateVehicles Expression Set](https://help.salesforce.com/s/articleView?id=ind.insurance_autoratevehicles_expression_set_omnistudio.htm&language=en_US&type=5)**  
    This expression set rates all vehicles to be insured.

Did this article solve your issue?

Let us know so we can improve!

YesNo