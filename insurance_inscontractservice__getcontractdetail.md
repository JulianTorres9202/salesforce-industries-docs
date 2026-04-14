---
title: "InsContractService:getContractDetail"
source: "https://help.salesforce.com/s/articleView?id=ind.insurance_inscontractservice__getcontractdetail.htm&language=en_US&type=5"
scraped: "2026-04-14"
filter: "ind.insurance_"
---# InsContractService:getContractDetail

InsContractService:getContractDetail[](https://help.salesforce.com/s?language=en_US)

You are here:

1.  [Salesforce Help](/s/?language=en_US)
2.  [Docs](/s/products?language=en_US)
3.  [Digital Insurance](https://help.salesforce.com/s/articleView?id=ind.insurance_admin_standard.htm&language=en_US&type=5)

# InsContractService:getContractDetail

Use this service to return a ProductJSON that you can use with the `InsQuoteService:createUpdateQuote` service to update the Contract JSON with, or to create a renewal quote with replacement products.

[](https://help.salesforce.com/s?language=en_US)

[](https://help.salesforce.com/s?language=en_US)Class: `InsContractService`

Method: `getContractDetail`

[](https://help.salesforce.com/s?language=en_US)

## How It Works

For example, if the Silver My Choice HDHP 300 product has a replacement product of Silver My Choice HDHP 400, the Contract JSON will replace the Silver My Choice HDHP 300 product with Silver My Choice HDHP 400.

[](https://help.salesforce.com/s?language=en_US)

1.  Uses the `contractId` to retrieve contract information.
    
2.  Using the contract information, retrieves all of the `ContractLineItems` associated with the contract.
    
    If `rootItemIds` is specified, the service retrieves only the `ContractLineItems` with ids in the `rootItemIds` list and their child `ContractLineItems`.
    
3.  If the `getReplacementProducts` option is set to `true`, the service iterates through all the root-level `ContractLineItems`. If the product associated with a given `ContractLineItem` has a replacement product, the service replaces the child product with the replacement product in the contract JSON.
    

[](https://help.salesforce.com/s?language=en_US)An `effectiveDate` option is also available if you want to use a replacement product that will be effective until some future date. To do this, select the replacement product whose effective date is less than the `effectiveDate` and whose end date is null or is greater than the `effectiveDate`.

[](https://help.salesforce.com/s?language=en_US)By default, the service will use the active census type System that is attached to the contracted Group. If this is not available, it uses the enrollment census from the contract.

[](https://help.salesforce.com/s?language=en_US)

## Remote Options

| 
Option

 | 

Description

 |
| --- | --- |
| 

`contractId`

 | 

Required.

Id of target contract.

 |
| 

`getReplacementProducts`

 | 

Optional.

Default = `false`.

If set to `true`, replaces the existing products with applicable replacements.

 |
| 

`effectiveDate`

 | 

Optional.

Used if `getReplacementProducts` is set to `true`.

If this option is not provided, default = today.

 |
| 

`rateType`

 | 

Optional. Use only when you set `getReplacementProducts` to `true`.

Value must be `age` or `composite.`

No default value is entered if no value is set.

Use this option when you need to price replacement products. It corresponds to the `rateType` option for [InsProductService:getRatedProducts](https://help.salesforce.com/s/articleView?id=ind.insurance_insproductservice__getratedproducts.htm&language=en_US&type=5 "Use this service to get an array of one or more products, priced using rating procedures attached to those products. This service also includes extra features such as tax and fee calculations, filtering, and performance optimization.").

 |
| 

`isBatchMode`

 | 

`true` or `false`

When set to `true`, the service returns a simplified product JSON that does not include attribute categories, but does include attribute selected values and rules.

When set to `false`, the service returns the full product JSON.

This option is useful if you're running an Integration Procedure in batch mode and it contains this service.

 |

[](https://help.salesforce.com/s?language=en_US)

## Input JSON

This service does not use an input JSON.

[](https://help.salesforce.com/s?language=en_US)

## Output JSON

Contract JSON of target contract. (Sample below.)

Note

The fields returned in the Contract JSON can be modified by updating the `GetContractDetailFields` fieldSets on the Contract and ContractLineItem objects.

[](https://help.salesforce.com/s?language=en_US)`{   "totalSize": 1,   "records": [     {       "displaySequence": -1,       "Id": "800f4000000Bi7mAAC",       "AccountId": "001f400000emqVVAAY",       "ContractNumber": "00024803",       "effectiveDate": "2018-12-28",       "endDate": "2019-01-27",       "ContractTerm": 1,       "EnrollmentCensusId__c": "a3wf4000000LspPAAS",       "Pricebook2Id": "01sf4000007PvM2AAK",       "childProducts": {         "totalSize": 2,         "records": [           {             "displaySequence": -1,             "Id": "a2If4000001HvLtEAK",             "renewalSourceId": "a2If4000001HvLtEAK",             "AttributeSelectedValues__c": "{\"SLEEPSTUDIESOON\":\"Not covered.\",\"SLEEPSTUDIESIN\":80,\"HITECHIMAGINGOON\":\"Not covered.\",\"HITECHIMAGINGIN\":90,\"XRAYLABOON\":\"Not covered.\",\"XRAYLABIN\":90,\"InpatHabOutofnetwork\":50,\"InpatHabInnetwork\":80,\"InpatRehabOutOfnetwork\":50,\"InpatRehabInnetwork\":80,\"SNFOut-of-network\":50,\"SNFIn-network\":80,\"Inpatoutofnetwork\":50,\"Inpatinnetwork\":80,\"ATTRIBUTE-079\":80,\"ATTRIBUTE-078\":100,\"ATTRIBUTE-081\":70,\"ATTRIBUTE-080\":80,\"ATTRIBUTE-083\":80,\"ATTRIBUTE-082\":10,\"WELLBABYOON\":50,\"WELLBABYINN\":\"No charge.\",\"Tobacco OON\":\"No charge.\",\"Tobacco INN\":\"No charge.\",\"MAMMOOON\":80,\"MAMMOIN\":90,\"IMMUNOON\":80,\"IMMUNIN\":\"No charge.\",\"GYNOON\":80,\"GYNINN\":\"No charge.\",\"EXAMOON\":70,\"EXAMIN\":10,\"OUTPAT Treatment OON\":60,\"OUTPAT Treatment IN\":50,\"OUTPAT SVC OON\":50,\"OUTPAT SVC IN\":20,\"PROSORTHOON\":50,\"PROSORTHIN\":75,\"DIABETESOON\":50,\"DIABETESIN\":75,\"EQOON\":50,\"EQINN\":75,\"RESPITE OON\":30,\"RESPITE IN\":80,\"HOSPICE OON\":30,\"HOSPICE IN\":80,\"HOMEOON\":30,\"HOMEIN\":80,\"ATTRIBUTE-073\":12000,\"ATTRIBUTE-071\":5000,\"ATTRIBUTE-072\":6000,\"ATTRIBUTE-070\":3000,\"ATTRIBUTE-076\":60,\"ATTRIBUTE-075\":80,\"ATTRIBUTE-069\":50,\"INCP\":25,\"ATTRIBUTE-066\":50000,\"ATTRIBUTE-064\":3000,\"EMPLOYEEFAMILY\":5775,\"SGCOINSURANCE\":\"$70\",\"SGDEDUCTIBLE\":\"$6000\"}",             "productId": "01tf4000003GgJUAA0",             "Price": 4504.5,             "productName": "Silver My Choice HDHP 3000",             "ProductCode": "MCHDHPCA3000",             "RecordTypeName__c": "Product",             "childProducts": {               "totalSize": 0,               "records": [                 {                   "displaySequence": -1,                   "Id": "a2If4000001HvLvEAK",                   "renewalSourceId": "a2If4000001HvLvEAK",                   "AttributeSelectedValues__c": "{\"WELLNESS-EXAM\":20,\"ILLNESS\":4}",                   "ParentItemId__c": "a2If4000001HvLtEAK",                   "productId": "01tf4000003GgJjAAK",                   "pciId": "a2vf4000000RLG2AAO",                   "Price": 0,                   "productName": "Acupuncture Office Professional",                   "ProductCode": "AOP",                   "RecordTypeName__c": "CoverageSpec",                   "isSelected": true                 },                 {                   "displaySequence": -1,                   "Id": "a2If4000001HvLwEAK",                   "renewalSourceId": "a2If4000001HvLwEAK",                   "AttributeSelectedValues__c": "{\"WELLNESS-EXAM\":20,\"ILLNESS\":4}",                   "ParentItemId__c": "a2If4000001HvLtEAK",                   "productId": "01tf4000003GgJeAAK",                   "pciId": "a2vf4000000RLG3AAO",                   "Price": 0,                   "productName": "Acupuncture Outpatient Professional",                   "ProductCode": "AOUP",                   "RecordTypeName__c": "CoverageSpec",                   "isSelected": true                 }               ]             }           },           {             "displaySequence": -1,             "Id": "a2If4000001HvLuEAK",             "renewalSourceId": "a2If4000001HvLuEAK",             "AttributeSelectedValues__c": "{\"SQUAREFEET\":\"2018-04-02T07:00:00.000Z\"}",             "productId": "01tf4000003GgIvAAK",             "Price": 3575,             "productName": "Bronze My Choice HDHP 2500 CA",             "ProductCode": "MCHDHPCA2500",             "RecordTypeName__c": "Product",             "childProducts": {               "totalSize": 0,               "records": [                 {                   "displaySequence": -1,                   "Id": "a2If4000001HvLxEAK",                   "renewalSourceId": "a2If4000001HvLxEAK",                   "AttributeSelectedValues__c": "{\"WELLNESS-EXAM\":20,\"ILLNESS\":4}",                   "ParentItemId__c": "a2If4000001HvLuEAK",                   "productId": "01tf4000003GgJeAAK",                   "pciId": "a2vf4000000RLFtAAO",                   "Price": 2788.5,                   "productName": "Acupuncture Outpatient Professional",                   "ProductCode": "AOUP",                   "RecordTypeName__c": "CoverageSpec",                   "isSelected": true                 },                 {                   "displaySequence": -1,                   "Id": "a2If4000001HvLyEAK",                   "renewalSourceId": "a2If4000001HvLyEAK",                   "AttributeSelectedValues__c": "{\"WELLNESS-EXAM\":20,\"ILLNESS\":4}",                   "ParentItemId__c": "a2If4000001HvLuEAK",                   "productId": "01tf4000003GgJjAAK",                   "pciId": "a2vf4000000RLFsAAO",                   "Price": 2788.5,                   "productName": "Acupuncture Office Professional",                   "ProductCode": "AOP",                   "RecordTypeName__c": "CoverageSpec",                   "isSelected": true                 }               ]             }           }         ]       }     }   ]`

Did this article solve your issue?

Let us know so we can improve!

YesNo