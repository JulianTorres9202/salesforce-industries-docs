---
title: "InsCensusServiceStd:setMemberRatingFacts"
source: "https://help.salesforce.com/s/articleView?id=ind.insurance_inscensusservicestd__setmemberratingfacts.htm&language=en_US&type=5"
scraped: "2026-04-14"
filter: "ind.insurance_"
---# InsCensusServiceStd:setMemberRatingFacts

InsCensusServiceStd:setMemberRatingFacts[](https://help.salesforce.com/s?language=en_US)

You are here:

1.  [Salesforce Help](/s/?language=en_US)
2.  [Docs](/s/products?language=en_US)
3.  [Digital Insurance](https://help.salesforce.com/s/articleView?id=ind.insurance_admin_standard.htm&language=en_US&type=5)

# InsCensusServiceStd:setMemberRatingFacts

Use this service to set `AttributeSelectedValues` on the `GroupCensusMember` records based on the rating fact passed to the service.

Class: ​`InsCensusServiceSt`d

Method: `setMemberRatingFacts`

[](https://help.salesforce.com/s?language=en_US)

## How It Works

1.  The service takes the `censusId`, `ratingFactSpecId`, and `drBundleName` as either inputs or remote options.
    
2.  Fetches the GroupCensus, GroupCensusMember, and related GroupClass records from the passed census Id. ​
    
3.  The service uses the fieldset RatingFactSourceFields for fetching GroupCensusMember record data.
    
4.  (optional) The service uses `drBundleName` Omnistudio Data Mapper to populate the `AttributeSelectedValues_c` fields of the GroupCensusMember object. It passes the `SpecProduct2Id__c` as a lookup field to link the GroupCensusMember to a Rating Fact.
    
5.  Both the `SpecProduct2Id_c` and `AttributeSelectedValues_c` are used in the rating.
    

## Service Behavior

Understand how different inputs affect the service outputs.

| Input | Service Output |
| --- | --- |
| No `censusId` or invalid `censusId` | `AttributeSelectedValues` aren't populated. |
| No `ratingFactSpecId` and invalid `ratingFactSpecId` | `AttributeSelectedValues` aren't populated. |
| Invalid `drBundleName` | Empty `AttributeSelectedValues` are populated. |
| Valid `censusId` and `ratingFactSpecId` | `AttributeSelectedValues` are populated for each member. |

[](https://help.salesforce.com/s?language=en_US)

## Input or Remote Options

Provide the following as either an input or remote option:​

| ​Option​ | ​Description​ |
| --- | --- |
| 
`censusId​​​`

 | 

​Group Census Id to be associated with the Rating Fact spec.​

 |
| 

​​​

`ratingFactSpecId​​​`

 | 

Rating Fact spec Id to be associated with the census.​

 |
| 

​​​

`drBundleName`

​​​

 | 

​Name of transform Data Mapper to map Rating Fact attributes and group census member.​

 |

## Input JSON

Here's the sample input JSON format: ​

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
   "drBundleName":"TransformGroupCensusMember"
}
```

## Output JSON

There is no output JSON associated with this service.

Did this article solve your issue?

Let us know so we can improve!

YesNo