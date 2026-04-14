---
title: "Data Model Updates for Insurance Summer '21"
source: "https://help.salesforce.com/s/articleView?id=ind.insurance_data_model_updates_for_insurance_summer__21.htm&language=en_US&type=5"
scraped: "2026-04-14"
filter: "ind.insurance_"
---# Data Model Updates for Insurance Summer '21

Data Model Updates for Insurance Summer '21[](https://help.salesforce.com/s?language=en_US)

You are here:

1.  [Salesforce Help](/s/?language=en_US)
2.  [Docs](/s/products?language=en_US)
3.  [Digital Insurance](https://help.salesforce.com/s/articleView?id=ind.insurance_admin_standard.htm&language=en_US&type=5)

# Data Model Updates for Insurance Summer '21

The data model updates for this release:

[](https://help.salesforce.com/s?language=en_US)

## New Data Model Objects

We added this object to the data model for this release:

| 
New Object

 | 

Description

 |
| --- | --- |
| 

Orchestration Item Relationship

 | 

Generic orchestration item relationship. Use this object during a supplemental order to maintain the continuity chain of dependencies.

This object includes the following fields:

-   Item
    
-   Related Item
    
-   Relationship Type: The type of relationship between the pair of orchestration items.
    

 |

[](https://help.salesforce.com/s?language=en_US)

## Enhanced Data Model Objects

We added fields and made other enhancements to the following objects for this release:

| 
Enhanced Object

 | 

What's Changed

 |
| --- | --- |
| 

Product

 | 

We added the following field:

-   Fulfillment Behavior
    

 |
| --- | --- |
| 

Orchestration Item Definition

 | 

We added the following field:

-   Callout Parameters: The parameters for request payload generation in the system interface.
    

 |
| --- | --- |
| 

Orchestration Item

 | 

We added the following fields:

-   Callout Parameters: The parameters for request payload generation in the system interface.
    
-   [](https://help.salesforce.com/s?language=en_US)
    
    Process After
    
-   [](https://help.salesforce.com/s?language=en_US)
    
    Process After Expression
    

 |
| --- | --- |
| 

Quote

 | 

We added the following field:

-   Commission Amount: The commission amount calculated for the specified quote.
    

 |
| --- | --- |
| 

Fulfilment Request Line

 | 

[](https://help.salesforce.com/s?language=en_US)We added the following field:

-   Main Fulfilment Request Line Id: This field looks up to the main fulfilment request line item.
    

 |
| --- | --- |
| 

Order Product

 | 

[](https://help.salesforce.com/s?language=en_US)We added the following field:

-   Main Order Item Id: This field looks up to the main order line item.
    

 |
| --- | --- |
| 

Vlocity DataRaptor Bundle

 | 

We added the following field:

-   OM Plus Enabled: Enables OM plus sync for this object.
    

 |
| --- | --- |
| 

Vlocity DataRaptor Map Item

 | 

We added the following field:

-   OM Plus Enabled: Enables OM plus sync for this object.
    

 |
| --- | --- |
| 

Integration Retry Policy

 | 

We added the following field:

-   Retry Intervals
    

 |

Did this article solve your issue?

Let us know so we can improve!

YesNo