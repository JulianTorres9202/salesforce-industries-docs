---
title: "Data Model Updates for Insurance Winter '23"
source: "https://help.salesforce.com/s/articleView?id=ind.insurance_data_model_updates_for_winter_23.htm&language=en_US&type=5"
scraped: "2026-04-14"
filter: "ind.insurance_"
---# Data Model Updates for Insurance Winter '23

Data Model Updates for Insurance Winter '23[](https://help.salesforce.com/s?language=en_US)

You are here:

1.  [Salesforce Help](/s/?language=en_US)
2.  [Docs](/s/products?language=en_US)
3.  [Digital Insurance](https://help.salesforce.com/s/articleView?id=ind.insurance_admin_standard.htm&language=en_US&type=5)

# Data Model Updates for Insurance Winter '23

Explore new and enhanced data model objects for this release.

[](https://help.salesforce.com/s?language=en_US)

## New Data Model Object

We added this new object to the data model for this release:

| 
New Data Model Object

 | 

Description

 |
| --- | --- |
| 

Configuration Snapshot

 | 

Allows you to track or manage multiple versions of cacheable datasets linking to snapshot ID with varying effectivity. Supports zero downtime during cache generation for the APIs using cached datasets.

This object includes these new fields:

-   Configuration Snapshot Id: Auto generated number to represent the cached dataset.
    
-   Effective End Date: End date of the linked cached dataset through snapshot ID.
    
-   Effective Start Date: Start date of the linked cached dataset through snapshot ID.
    
-   Status: Status of the configuration snapshot, which helps to track the status of cached/caching dataset with following states. Possible values: Processing, Ready, Active, Expired, Aborted
    

 |

[](https://help.salesforce.com/s?language=en_US)

## Enhanced Data Model Objects

We added fields and made other enhancements to the following objects for this release:

| 
Enhanced Data Model Objects

 | 

Description

 |
| --- | --- |
| 

CachedAPIResponse\_\_c

 | 

This object includes the following new field:

[](https://help.salesforce.com/s?language=en_US)

-   ConfigurationSnapshotId: Auto generated number to represent the cached dataset.
    

 |
| 

FulfilmentRequestLine\_\_c

 | 

This object includes the following new fields:

-   Attribute Selected Values: Use this field when JSONAttribute V2 feature is turned on. It contains the attribute values of the line item encoded in a JSON format.
    
-   Is Migrated: Indicates whether a migration process is applied or not for a specific fulfillment request line.
    

 |
| FulfilmentRequestLineDecompRelationship\_\_c | 

This object includes the following new field:

-   Decomposition Relationship Metadata: Decomposition relationship metadata for this fulfillment request line.
    

 |
| 

InventoryItem\_\_c

 | 

This object includes the following new fields:

[](https://help.salesforce.com/s?language=en_US)

-   Attribute Selected Values: Use this field when JSONAttribute V2 feature is turned on. It contains the attribute values of the line item encoded in a JSON format.
    
-   Is Migrated: Indicates whether a migration process is applied or not for a specific fulfillment request line.
    

 |
| Order | 

This object includes the following new field:

-   Orchestration Method: The method used for order management decomposition and orchestration.
    

 |
| ProductRequirement\_\_c | 

This object includes the following new fields:

-   False Action: The Vlocity Action associated with the Product Requirement. This action executes when the underwriting rule is false.
    
-   False Message: The message presented when the underwriting rule is false.
    
-   Rule Scope: The insured item types on which the rule executes.
    

 |

Did this article solve your issue?

Let us know so we can improve!

YesNo