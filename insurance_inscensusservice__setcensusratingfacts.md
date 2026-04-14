---
title: "InsCensusService:setCensusRatingFacts"
source: "https://help.salesforce.com/s/articleView?id=ind.insurance_inscensusservice__setcensusratingfacts.htm&language=en_US&type=5"
scraped: "2026-04-14"
filter: "ind.insurance_"
---# InsCensusService:setCensusRatingFacts

InsCensusService:setCensusRatingFacts[](https://help.salesforce.com/s?language=en_US)

You are here:

1.  [Salesforce Help](/s/?language=en_US)
2.  [Docs](/s/products?language=en_US)
3.  [Digital Insurance](https://help.salesforce.com/s/articleView?id=ind.insurance_admin_standard.htm&language=en_US&type=5)

# InsCensusService:setCensusRatingFacts

Use this service to associate a Rating Fact spec to a census, and automatically extract information from the census fields to populate the Attribute Selected Values for the census, based on the Rating Fact.

Important From Winter '23 onward, we have [InsCensusServiceStd:setCensusRatingFacts](https://help.salesforce.com/s/articleView?id=ind.insurance_inscensusservicestd__setcensusratingfacts.htm&language=en_US&type=5 "Use this service to set AttributeSelectedValues on the GroupCensus record based on the rating fact passed to the service.") service enabled to work with Salesforce Standard Data Model for Financial Services Cloud and Health Cloud. Existing customers can continue to use this service, but no further enhancements will be provided in the Insurance Managed Package.

The service passes the census header fields (including custom fields) to an Omnistudio Data Mapper in the same way that the InsCensusService:setMemberRatingFacts service does to map Rating Fact attributes and census members.

This census level service allows you to reference a different Rating Fact, with different attributes, than the one associated at the census member level.

[](https://help.salesforce.com/s?language=en_US)

Class: `InsCensusService`

Method: `setCensusRatingFacts`

[](https://help.salesforce.com/s?language=en_US)

## How It Works

[](https://help.salesforce.com/s?language=en_US)

-   The service takes the `censusId`, `ratingFactSpecId`, and `drBundleName` as either inputs or remote options.
    
-   The `drBundleName` Data Mapper is used to populate the `AttributeSelectedValues_c` fields of the Census object with the Attribute Selected Values, and uses the `SpecProduct2Id__c` as a lookup field to link the census to a Rating Fact.
    
-   Both the `SpecProduct2Id_c` and `AttributeSelectedValues_c` are used in the rating.
    

[](https://help.salesforce.com/s?language=en_US)

## Remote Options

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

Name of transform Data Mapper to map Rating Fact attributes and census.

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