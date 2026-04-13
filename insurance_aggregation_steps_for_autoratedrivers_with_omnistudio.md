---
title: "Aggregation Steps for autoRateDrivers"
source: "https://help.salesforce.com/s/articleView?id=ind.insurance_aggregation_steps_for_autoratedrivers_with_omnistudio.htm&language=en_US&type=5"
scraped: "2026-04-13"
filter: "ind.insurance_"
---# Aggregation Steps for autoRateDrivers

Aggregation Steps for autoRateDrivers[](https://help.salesforce.com/s?language=en_US)

You are here:

1.  [Salesforce Help](/s/?language=en_US)
2.  [Docs](/s/products?language=en_US)
3.  [Digital Insurance](https://help.salesforce.com/s/articleView?id=ind.insurance_admin_standard.htm&language=en_US&type=5)

# Aggregation Steps for autoRateDrivers

autoRateDrivers includes aggregation steps that calculate aggregated premiums per driver for specific coverages:

1.  Calculates the rated driver Bodily Injury & Property Damage (BIPD) by averaging the driverBIPD outputs from each run of the calculation steps.
    
    If one driver has been rated twice because they're in two driver+vehicle sets, this step averages their BIPD rating and returns one value.
    
    Note
    
    This works the same way and for the same reason for all the following aggregation steps.
    
2.  Calculates the rated driver Uninsured Motorist (UM) by averaging driverUM outputs from each run of the calculation steps.
    
3.  Calculates the rated driver Medical payments (MED) by averaging driverMED outputs from each run of the calculation steps.
    
4.  Calculates the rated driver comprehensive (CCD) by averaging driverCCD outputs from each run of the calculation steps.
    
5.  Calculates the rated driver Collision (COLL) by averaging driverCOLL outputs from each run of the calculation steps.
    

Did this article solve your issue?

Let us know so we can improve!

YesNo