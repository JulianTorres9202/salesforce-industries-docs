---
title: "InsClaimItemService:getInsuranceCodes"
source: "https://help.salesforce.com/s/articleView?id=ind.insurance_insclaimitemservice__getinsurancecodes.htm&language=en_US&type=5"
scraped: "2026-04-14"
filter: "ind.insurance_"
---# InsClaimItemService:getInsuranceCodes

InsClaimItemService:getInsuranceCodes[](https://help.salesforce.com/s?language=en_US)

You are here:

1.  [Salesforce Help](/s/?language=en_US)
2.  [Docs](/s/products?language=en_US)
3.  [Digital Insurance](https://help.salesforce.com/s/articleView?id=ind.insurance_admin_standard.htm&language=en_US&type=5)

# InsClaimItemService:getInsuranceCodes

Use this service to get a list of insurance codes that correspond to the coverages associated with claims.

Note

This service is designed to be used before the [InsClaimItemService:add](https://help.salesforce.com/s/articleView?id=ind.insurance_insclaimitemservice__add.htm&language=en_US&type=5 "Use this service to add a claim line item to a specified claim item object.") or [InsClaimItemService:update](https://help.salesforce.com/s/articleView?id=ind.insurance_insclaimitemservice__update.htm&language=en_US&type=5 "Use this service to update a claim line item to a specified claim item object.") services to get the insurance codes these services need.

[](https://help.salesforce.com/s?language=en_US)

Class: `InsClaimItemService`

Method: `getInsuranceCodes`

[](https://help.salesforce.com/s?language=en_US)

## How It Works

1.  Takes the `codeSystemType` option and any of the other filter options.
    
2.  Returns a filtered list of insurance codes that can be passed to other services.
    

[](https://help.salesforce.com/s?language=en_US)

## Remote Options

| 
Option

 | 

Description

 |
| --- | --- |
| 

`codeSystemType`

 | 

Required.

Filters the list of insurance codes this service returns as results.

 |
| 

`category`

 | 

Filters the list of insurance codes this service returns as results.

 |
| 

`codeSubType`

 | 

Filters the list of insurance codes this service returns as results.

 |
| 

`effectiveDate` 

 | 

Filters the list of insurance codes by effective start date and effective end date, inclusive.

 |

[](https://help.salesforce.com/s?language=en_US)

## Input JSON

This service does not take an input JSON.

[](https://help.salesforce.com/s?language=en_US)

## Output JSON

The service returns a JSON that includes all the claim coverages that fit the options entered and their codes.

```
[
    {
        "CodeSubType__c": "CMS+PCS",
        "Category__c": "Auto",
        "CodeSystemType__c": null,
        "LongDescription__c": "Auto Code Test",
        "ShortDescription__c": "ACode",
        "DisplayName__c": "Auto Code",
        "Name": "AutoCode",
        "Id": "a551U00000021XsQAI"
    },
    {
        "CodeSubType__c": "PCS",
        "Category__c": "Life",
        "CodeSystemType__c": null,
        "LongDescription__c": "Life Code Test",
        "ShortDescription__c": "LCode",
        "DisplayName__c": "Life Code",
        "Name": "LifeCode",
        "Id": "a551U00000021XnQAI"
    },
    { ... }
]
```

Did this article solve your issue?

Let us know so we can improve!

YesNo