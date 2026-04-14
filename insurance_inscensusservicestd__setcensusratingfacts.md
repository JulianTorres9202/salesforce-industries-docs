---
title: "InsCensusServiceStd:setCensusRatingFacts"
source: "https://help.salesforce.com/s/articleView?id=ind.insurance_inscensusservicestd__setcensusratingfacts.htm&language=en_US&type=5"
scraped: "2026-04-14"
filter: "ind.insurance_"
---# InsCensusServiceStd:setCensusRatingFacts

InsCensusServiceStd:setCensusRatingFacts[](https://help.salesforce.com/s?language=en_US)

You are here:

1.  [Salesforce Help](/s/?language=en_US)
2.  [Docs](/s/products?language=en_US)
3.  [Digital Insurance](https://help.salesforce.com/s/articleView?id=ind.insurance_admin_standard.htm&language=en_US&type=5)

# InsCensusServiceStd:setCensusRatingFacts

Use this service to set `AttributeSelectedValues` on the `GroupCensus` record based on the rating fact passed to the service.

Class: ​`InsCensusServiceStd`​​

Method: `setCensusRatingFacts`

[](https://help.salesforce.com/s?language=en_US)

## How It Works

1.  The service takes the `censusId`, `ratingFactSpecId`, and `drBundleName` as either inputs or remote options.
    
2.  The service uses `drBundleName` Omnistudio Data Mapper to populate the `AttributeSelectedValues_c` fields of the GroupCensus object. It uses the `SpecProduct2Id__c` as a lookup field to link the GroupCensus to a Rating Fact.
    
3.  Both the `SpecProduct2Id_c` and `AttributeSelectedValues_c` are used in the rating.
    

## Service Behavior

Understand how different inputs affect the service outputs.

| Input | Service Output |
| --- | --- |
| No `censusId` or invalid `censusId` | `AttributeSelectedValues` are not populated. |
| No `ratingFactSpecId` and invalid `ratingFactSpecId` | `AttributeSelectedValues` are not populated. |
| Invalid `drBundleName` | Empty `AttributeSelectedValues` are populated. |
| Valid `censusId` and `ratingFactSpecId` | `AttributeSelectedValues` are populated for the passed census. |

[](https://help.salesforce.com/s?language=en_US)

## Remote Options

| ​Option​ | ​Description​ |
| --- | --- |
| ​​​`censusId​​​` | 
​Required​.

ID of the group census to be associated with the Rating Fact spec.

 |
| ​​​`ratingFactSpecId​​​` | 

​Required​

Rating Fact spec Id to be associated with the census.​

 |
| `​​​drBundleName​​​` | ​Name of transform Data Mapper to map Rating Fact attributes and census. |

## Input JSON

Here's the sample input JSON format:

```json
{ 
   "censusId":"ID",
   "ratingFactSpecId":"ID",
   "drBundleName":"Name"
}
```

Here's the sample input JSON:

```json
{ 
   "censusId":"a4D4P000000hbjSUAQ",
   "ratingFactSpecId":"01tRO000000VpnYYAS"
   "drBundleName":"TransformGroupCensus"
}
```

## Output JSON

The service populates attribute selected values on group census.

Did this article solve your issue?

Let us know so we can improve!

YesNo