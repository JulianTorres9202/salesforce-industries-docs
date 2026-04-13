---
title: "InsCensusService:getMemberRatingFacts"
source: "https://help.salesforce.com/s/articleView?id=ind.insurance_inscensusservice__getmemberratingfacts.htm&language=en_US&type=5"
scraped: "2026-04-13"
filter: "ind.insurance_ins"
---# InsCensusService:getMemberRatingFacts

InsCensusService:getMemberRatingFacts[](https://help.salesforce.com/s?language=en_US)

You are here:

1.  [Salesforce Help](/s/?language=en_US)
2.  [Docs](/s/products?language=en_US)
3.  [Digital Insurance](https://help.salesforce.com/s/articleView?id=ind.insurance_admin_standard.htm&language=en_US&type=5)

# InsCensusService:getMemberRatingFacts

Use this service to retrieve rating fact data for census members, for use as user Inputs for the `InsProductService:getRatedProducts` service.

[](https://help.salesforce.com/s?language=en_US)

Class: `InsCensusService`

Method: `getMemberRatingFacts`

[](https://help.salesforce.com/s?language=en_US)

## How It Works

-   JSON formatted userInputs of the census rating fact dataset are used to form `userInputs` for the `getRatedProducts` service.
    
-   The `censusId` and `accountId` are used to retrieve the `GroupCensus__c` object.
    
-   The `censusId` is used to retrieve the `GroupCensusMember__c` object, which generates the user inputs using the `GroupCensus__c` product.
    
-   Details for the rating fact, and it’s attribute selected values, are then iterated to each `GroupCensusMember__c`.
    
-   If `includeContributionInUserInput` is true, all contributions are added to the `userInputs`.
    

[](https://help.salesforce.com/s?language=en_US)

## Inputs/Remote Options

| 
Option

 | 

Description

 |
| --- | --- |
| 

`censusId`

 | 

Required.

Id of the census with members to retrieve.

 |
| 

`accountId`

 | 

Optional.

Id of Account for census.

 |
| 

`productCategory`

 | 

Optional.

String value.

The productCategory, used to group class contributions.

 |
| 

`includeContributionInUserInput drBundleName`

 | 

Boolean.

Used to determine if contributions will be added to the userInputs on the output.

Default = false.

 |

[](https://help.salesforce.com/s?language=en_US)

## Input JSON

This service does not use an input JSON.

[](https://help.salesforce.com/s?language=en_US)

## Output JSON

Below is the sample output of `userInputs` on a census with three members and the attribute selected values of the rating fact attached to the census (`MEMBERAGE` and `MEMBERGENDER`).

```
{
  "ContextId": "",
  "timeStamp": "2019-08-02T14:03:20.161Z",
  "userId": "0056F0000077bTYQAY",
  "userName": "jsmith@company.com",
  "userProfile": "System Administrator",
  "userTimeZone": -420,
  "userCurrencyCode": "EUR",
  "sfdcIFrameOrigin": "https://company.com",
  "sfdcIFrameHost": "web",
  "layout": "lightning",
  "isdtp": "p1",
  "id": "a1e6F000004RDdXQAW",
  "vlcPersistentComponent": {},
  "censusId": "a396F000001KurRQAS",
  "userInputs": [
    {
      "JLRF.MEMBERGENDER": "Female",
      "JLRF.MEMBERAGE": 33
    },
    {
      "JLRF.MEMBERGENDER": "Male",
      "JLRF.MEMBERAGE": 49
    },
    {
      "JLRF.MEMBERGENDER": "Male",
      "JLRF.MEMBERAGE": 35
    }
  ],
  "error": "OK"
}
```

Did this article solve your issue?

Let us know so we can improve!

YesNo