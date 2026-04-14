---
title: "Data Model Updates for Insurance Spring '23"
source: "https://help.salesforce.com/s/articleView?id=ind.insurance_data_model_updates_for_spring_23.htm&language=en_US&type=5"
scraped: "2026-04-14"
filter: "ind.insurance_"
---# Data Model Updates for Insurance Spring '23

Data Model Updates for Insurance Spring '23[](https://help.salesforce.com/s?language=en_US)

You are here:

1.  [Salesforce Help](/s/?language=en_US)
2.  [Docs](/s/products?language=en_US)
3.  [Digital Insurance](https://help.salesforce.com/s/articleView?id=ind.insurance_admin_standard.htm&language=en_US&type=5)

# Data Model Updates for Insurance Spring '23

Explore new and enhanced data model objects for this release.

[](https://help.salesforce.com/s?language=en_US)

## New Data Model Objects

We added these new objects to the data model for this release:

| 
New Data Model Object

 | 

Description

 |
| --- | --- |
| 

Fulfilment Diagram

 | 

The name of the fulfilment diagram.

 |
| 

Fulfilment Diagram OPD

 | 

Represents a junction between a Fulfilment Diagram and an Orchestration Plan Definition.

This object includes these fields:

-   Fulfilment Diagram: the parent Fulfilment Diagram associated with the detail Fulfilment Diagram OPD.
    
-   Orchestration Plan Definition: The detail Orchestration Plan Definition associated with the parent Fulfilment Diagram OPD.
    
-   Swimlane Order: The swimlane display order for the Orchestration Plan Definition. For example, if 3 is specified, the Orchestration Plan Definition displays in the third swimlane. Minimum of 1 and maximum of 99.
    

 |

[](https://help.salesforce.com/s?language=en_US)

## Enhanced Data Model Objects

We added fields and made other enhancements to these objects for this release:

| 
Enhanced Data Model Objects

 | 

Description

 |
| --- | --- |
| 

Price List Entry

 | 

This object includes this new field:

[](https://help.salesforce.com/s?language=en_US)

-   Price Book Entry: A text field to contain the Price Book Entry ID value.
    

 |
| 

User

 | 

This object includes this new field:

-   DocuSign Named Credential
    

 |

Did this article solve your issue?

Let us know so we can improve!

YesNo