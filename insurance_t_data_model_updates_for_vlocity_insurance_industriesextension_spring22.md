---
title: "Data Model Updates for Vlocity Insurance Industries Extension Spring '22"
source: "https://help.salesforce.com/s/articleView?id=ind.insurance_t_data_model_updates_for_vlocity_insurance_industriesextension_spring22.htm&language=en_US&type=5"
scraped: "2026-04-14"
filter: "ind.insurance_"
---# Data Model Updates for Vlocity Insurance Industries Extension Spring '22

Data Model Updates for Vlocity Insurance Industries Extension Spring '22[](https://help.salesforce.com/s?language=en_US)

You are here:

1.  [Salesforce Help](/s/?language=en_US)
2.  [Docs](/s/products?language=en_US)
3.  [Digital Insurance](https://help.salesforce.com/s/articleView?id=ind.insurance_admin_standard.htm&language=en_US&type=5)

# Data Model Updates for Vlocity Insurance Industries Extension Spring '22

This section provides a list of new data model objects and enhanced data model objects for this release.

[](https://help.salesforce.com/s?language=en_US)

## Enhanced Data Model Objects

We added fields and made other enhancements to these objects for this release:

| 
Enhanced Object

 | 

Description

 |
| --- | --- |
| 

Insurance Policy Term

 | 

[](https://help.salesforce.com/s?language=en_US)This object includes the following new fields:

-   Term Duration Type: The type of time period measured for the duration. Possible values include: Lifetime, Duration, Rolling, Policy Term.
    
-   Term Duration Unit of Measure: The type of time measurement used for the duration. Possible values include: Day, Month.
    
-   Term Duration Value: The amount of time measured for the duration.
    

 |
| 

Insurance Policy Term Tracking Entry

 | 

This object includes the following new fields:

[](https://help.salesforce.com/s?language=en_US)

-   [](https://help.salesforce.com/s?language=en_US)
    
    Total Used Amount: The total monetary amount accumulated for a benefit with a lifetime term duration type.
    
-   [](https://help.salesforce.com/s?language=en_US)
    
    Total Used Value: The total number of units accumulated for a benefit with a lifetime term duration type.
    
-   Usage Date: The claim loss date used to evaluate whether a loss is within the duration period.
    

 |

Did this article solve your issue?

Let us know so we can improve!

YesNo