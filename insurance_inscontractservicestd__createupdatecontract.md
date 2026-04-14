---
title: "InsContractServiceStd:createUpdateContract"
source: "https://help.salesforce.com/s/articleView?id=ind.insurance_inscontractservicestd__createupdatecontract.htm&language=en_US&type=5"
scraped: "2026-04-14"
filter: "ind.insurance_"
---# InsContractServiceStd:createUpdateContract

InsContractServiceStd:createUpdateContract[](https://help.salesforce.com/s?language=en_US)

You are here:

1.  [Salesforce Help](/s/?language=en_US)
2.  [Docs](/s/products?language=en_US)
3.  [Digital Insurance](https://help.salesforce.com/s/articleView?id=ind.insurance_admin_standard.htm&language=en_US&type=5)

# InsContractServiceStd:createUpdateContract

Use this service to create or update a contract for the given quote. ​

Note Field Level Security must be enabled for the `Name`, `SourceQuote`, `SourceOpportunity` and `Pricebook` fields of Contract entity.

Class: ​`InsContractServiceStd`​​

Method: `createUpdateContract`

[](https://help.salesforce.com/s?language=en_US)

## How It Works

[](https://help.salesforce.com/s?language=en_US)

1.  This service looks for the `inputKey` value in the product JSON of a quote, which contains the `productConfigurationDetail` map, `additionalFields`​​, `​QuoteId`​​, and ​`AccountId​​`.
    
2.  The `​productConfigurationDetail`​​ contains the data of quote line items of given Quote, which the service uses to create contract group plans.
    
3.  `​​quoteId`​ is ID of the Quote for which the service creates the contract. ​`AccountId​​` is the ID of Account which is linked to the contract. ​
    
4.  Based on `QuoteId`, `AccountId` and additionalFields, the service creates the Contract and populate its fields. Corresponding to this Contract, the service creates an Insurance Contract and populates its fields using `additionalFields` data.
    
5.  If a `contractId` is specified, the service updates the contract.
    
6.  If a `contractId` is not specified, the service creates a new `contractId`.
    

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

Optional

Id of the contract.

 |
| 

`pricebook`

 | 

Optional

Name of the pricebook.

 |
| 

`inputJson`

 | 

Required.

Input JSON of the contract and contract group plans to be created. It has `productConfigurationDetail`, `additionalFields`, `AccountId` and `QuoteId`.

 |

## Service Behavior

Understand how different inputs affect the service outputs.

| 
Input

 | 

Output

 |
| --- | --- |
| No `contractId` and no `inputJson` | The service creates no contract. |
| No `contractId` and `inputJson` | The service creates a new Contract, Insurance Contract, and Contract Group Plans. |
| `contractId` and no `inputJson` | The service updates no contract. |
| `contractId` and `inputJson` | The service updates existing Contract, Insurance Contract, and Contract Group Plans. |

[](https://help.salesforce.com/s?language=en_US)

## Input JSON

[](https://help.salesforce.com/s?language=en_US)This sample shows a new contract input JSON, where `contractJson` is the input key and `productConfigurationDetail` contains the product JSON:

[](https://help.salesforce.com/s?language=en_US)`{     "productConfigurationDetail": {         "records": [      {           "displaySequence": 0,           "currencySymbol": "$",           "currencyCode": "USD",           "Id": "0QLRO0000009kbn4AA",           "productId": "01tRO000000QnqrYAC",           "Product2Id": "01tRO000000QnqrYAC",           "LineNumber": "00000019",           "CreatedDate": "2022-04-14T08:32:35.000+0000",           "QuoteId": "0Q0RO0000000vtw0AA",           "Price": 1,           "UnitPrice": 1,           "vlocityins6__RecordTypeName__c": "Product",           "vlocityins6__Type__c": "Dental",           "TotalPrice": 1,           "LastModifiedDate": "2022-04-14T08:32:35.000+0000",           "vlocityins6__PricingSource__c": "TotalPremium",           "vlocityins6__ProductName__c": "Dental Standard",           "vlocityins6__TotalAmount__c": 1,           "vlocityins6__ProductChildItemSequence__c": 0,           "needReprice": false,           "vlocityins6__NeedReprice__c": false,           "vlocityins6__RelationshipType__c": "Child",           "quoteLineItemId": "0QLRO0000009kbn4AA",           "productName": "Dental Standard",           "ProductCode": "dentalStandard",           "recordType": "Product",           "lineRecordType": "Product",           "Name": "Dental Standard",           "hasAttributes": true,           "coverageCount": 0,           "hasCoverages": false         },         {           "displaySequence": 0,           "currencySymbol": "$",           "currencyCode": "USD",           "Id": "0QLRO0000009kbs4AA",           "productId": "01tRO000000QnWnYAK",           "Product2Id": "01tRO000000QnWnYAK",           "LineNumber": "00000018",           "CreatedDate": "2022-04-14T08:30:59.000+0000",           "QuoteId": "0Q0RO0000000vtw0AA",           "Price": 7425,           "UnitPrice": 7425,           "vlocityins6__RecordTypeName__c": "Product",           "vlocityins6__Type__c": "Dental",           "TotalPrice": 7425,           "LastModifiedDate": "2022-05-31T02:35:56.000+0000",           "vlocityins6__PricingSource__c": "TotalPremium",           "vlocityins6__ProductName__c": "Dental Premium",           "vlocityins6__TotalAmount__c": 7425,           "vlocityins6__ProductChildItemSequence__c": 0,           "needReprice": false,           "vlocityins6__NeedReprice__c": false,           "vlocityins6__RelationshipType__c": "Child",           "quoteLineItemId": "0QLRO0000009kbs4AA",           "productName": "Dental Premium",           "ProductCode": "dentalPremium",           "recordType": "Product",           "lineRecordType": "Product",           "Name": "Dental Premium",           "hasAttributes": true,           "coverageCount": 0,           "hasCoverages": false         }],         "totalSize": 1              },     "additionalFields" : {       "EnrollmentWaitingPeriod": "30",       "Name": "contractAcc-Group Contract",       "ContractTerm": 12,       "EnrollmentCensusId": "0rfRO00000000WRYAY"     },     "AccountId" : "001RO000003fLhQYAU",     "QuoteId" : "0Q0RO0000001DlH0AU" }`

[](https://help.salesforce.com/s?language=en_US)

## Output JSON (when service creates a contract)

When creating a new contract, the `contractId` of the new contract is returned in the output JSON. When updating an existing contract, no output JSON is returned.

[](https://help.salesforce.com/s?language=en_US)`{   "contractId: "0rfRN0000000014YAA",   "errorCode": "INVOKE-200",   "error": "OK" }`

## Output JSON (when service returns an error)

The service returns an empty string if it encounters any exceptions. Also, it returns a list of members with errors. Each list item consists of input member data and errors.

```json
{
  "contractId: "",
  "errors" : "List of errors, if any",
  "errorCode": "INVOKE-200",
  "error": "OK"
}
```

Did this article solve your issue?

Let us know so we can improve!

YesNo