---
title: "InsCensusService:setMemberRatingFacts"
source: "https://help.salesforce.com/s/articleView?id=ind.insurance_inscensusservice__setmemberratingfacts.htm&language=en_US&type=5"
scraped: "2026-04-13"
filter: "ind.insurance_ins"
---# InsCensusService:setMemberRatingFacts

InsCensusService:setMemberRatingFacts[](https://help.salesforce.com/s?language=en_US)

You are here:

1.  [Salesforce Help](/s/?language=en_US)
2.  [Docs](/s/products?language=en_US)
3.  [Digital Insurance](https://help.salesforce.com/s/articleView?id=ind.insurance_admin_standard.htm&language=en_US&type=5)

# InsCensusService:setMemberRatingFacts

Use this service to associate a Rating Facts Spec to a census member, and automatically extract information from the census member fields to populate the Attribute Selected Values for the member, based on the Rating Fact.

Important From Winter '23 onward, we have [InsCensusServiceStd:setMemberRatingFacts](https://help.salesforce.com/s/articleView?id=ind.insurance_inscensusservicestd__setmemberratingfacts.htm&language=en_US&type=5 "Use this service to set AttributeSelectedValues on the GroupCensusMember records based on the rating fact passed to the service.") service enabled to work with Salesforce Standard Data Model for Financial Services Cloud and Health Cloud. Existing customers can continue to use this service, but no further enhancements will be provided in the Insurance Managed Package.

[](https://help.salesforce.com/s?language=en_US)

Class: `InsCensusService`

Method: `setMemberRatingFacts`

[](https://help.salesforce.com/s?language=en_US)

## How It Works

-   The service takes the `censusId`, `ratingFactSpecId`, and `drBundleName` as either inputs or remote options.
    
-   (optional) The `drBundleName` Omnistudio Data Mapper is used to populate the `AttributeSelectedValues_c` fields of the Census Member object with the Attribute Selected Values, and uses the `SpecProduct2Id__c` as a lookup field to link the census member to a Rating Fact. (See Note, above);
    
-   Both the `SpecProduct2Id_c` and `AttributeSelectedValues_c` are used in the rating.
    

[](https://help.salesforce.com/s?language=en_US)

## Input or Remote Options

Provide the following as either an input or remote option:

| 
Option

 | 

Description

 |
| --- | --- |
| 

`censusId`

 | 

Census Id to be associated with the Rating Fact spec.

 |
| 

`ratingFactSpecId`

 | 

Rating Fact spec Id to be associated with the census.

 |
| 

`drBundleName`

 | 

Name of transform Data Mapper to map Rating Fact attributes and census member.

 |

[](https://help.salesforce.com/s?language=en_US)

## Input JSON

This service does not use an input JSON.

[](https://help.salesforce.com/s?language=en_US)

## Output JSON

There is no output JSON associated with this service.

Did this article solve your issue?

Let us know so we can improve!

YesNo