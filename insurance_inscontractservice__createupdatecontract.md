---
title: "InsContractService:createUpdateContract"
source: "https://help.salesforce.com/s/articleView?id=ind.insurance_inscontractservice__createupdatecontract.htm&language=en_US&type=5"
scraped: "2026-04-14"
filter: "ind.insurance_"
---# InsContractService:createUpdateContract

InsContractService:createUpdateContract[](https://help.salesforce.com/s?language=en_US)

You are here:

1.  [Salesforce Help](/s/?language=en_US)
2.  [Docs](/s/products?language=en_US)
3.  [Digital Insurance](https://help.salesforce.com/s/articleView?id=ind.insurance_admin_standard.htm&language=en_US&type=5)

# InsContractService:createUpdateContract

Use this service to create or update a contract using the output of the `InsQuoteService:getQuoteDetail` service.

Important From Winter '23 onward, we have [InsContractServiceStd:createUpdateContract](https://help.salesforce.com/s/articleView?id=ind.insurance_inscontractservicestd__createupdatecontract.htm&language=en_US&type=5 "Use this service to create or update a contract for the given quote. ​") service enabled to work with Salesforce Standard Data Model for Financial Services Cloud and Health Cloud. Existing customers can continue to use this service, but no further enhancements will be provided in the Insurance Managed Package.

Note

The same quote used to create the contract is also used in the update.

[](https://help.salesforce.com/s?language=en_US)The service is typically used to add replacement products to an existing contract, for small groups.

[](https://help.salesforce.com/s?language=en_US)

[](https://help.salesforce.com/s?language=en_US)Class: `InsContractService`

Method: `createUpdateContract`

[](https://help.salesforce.com/s?language=en_US)

## How It Works

[](https://help.salesforce.com/s?language=en_US)

1.  This service looks for the `inputKey` value in the product JSON of a quote, which also contains the `productConfigurationDetail` map.
    
2.  If a `contractId` is specified, the contract is updated using the output of the `getContractDetails` service as its input.
    
3.  If a `contractId` is not specified, a new `contractId` is created.
    

[](https://help.salesforce.com/s?language=en_US)

## Remote Options

| 
Options

 | 

Description

 |
| --- | --- |
| 

`contractId`

 | 

Id of target contract.

 |
| 

`pricebook`

 | 

Optional.

The name of the pricebook to use on the created or updated contract.

If you don't provide a value, the service defaults to `Standard`.

 |

[](https://help.salesforce.com/s?language=en_US)

## Input JSON

When creating a new contract, the input JSON is similar to the output of the `InsQuoteService:getQuoteDetail` service. When updating an existing contract, the input JSON remains the same.

[](https://help.salesforce.com/s?language=en_US)This sample shows a new contract input JSON, where `contractJson` is the input key and `productConfigurationDetail` contains the product JSON returned via `InsQuoteService:getQuoteDetail`:

[](https://help.salesforce.com/s?language=en_US)`{   "productConfigurationDetail": {     "records": [...]     "totalSize": 1   },   "insuredItems": {     "Driver": [{         "instanceKey": "Joan Smith",         "isPrimary": false,         "isParent": false,         "LN": "Smith",         "AGE": 20,         "FN": "Joan",         "GENDER": "Female",         "FirstName": "Joan",         "LastName": "Smith"       },       {         ...       }     ],     "Auto": [{         "instanceKey": "2015 Lexus LX250",         "autoAntiTheft": true,         "est_annual_mileage": "1-10000",         "autoLicNum": "Lexus",         "autoModel": "LX250",         "autoYear": 2015,         "BodyClass": "Sedan/Saloon",         "VehicleType": "PASSENGER CAR",         "isPrimary": true         "isParent": false,       },       {         ...       }     ]   },   "quoteDetail": {     "attributes": {       "type": "Quote",       "url": "/services/data/v43.0/sobjects/Quote/0Q01I000000qeWLSAY"     },     "ins_daily4__EffectiveDate__c": "2018-07-27",     "ins_daily4__TotalSumInsured__c": 0,     "AccountId": "0011I00000QknfjQAB",     "ins_daily4__RootItemTotal__c": 0,     "Id": "0Q01I000000qeWLSAY"   },   "error": "OK" }`

[](https://help.salesforce.com/s?language=en_US)

## Output JSON

When creating a new contract, the contractId of the new contract is returned in the output JSON ('{"`contractId`": "`idOfNewContract`"}'), as shown below. When updating an existing contract, no output JSON is returned.

[](https://help.salesforce.com/s?language=en_US)`[{ 	'Name': 'Current Product' }, { 	'Name': 'Replacement Product', 	'isReplacementProduct': true }]`

Did this article solve your issue?

Let us know so we can improve!

YesNo