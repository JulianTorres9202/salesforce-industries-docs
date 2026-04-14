---
title: "InsPolicyService:createTransaction"
source: "https://help.salesforce.com/s/articleView?id=ind.insurance_inspolicyservice__createtransaction.htm&language=en_US&type=5"
scraped: "2026-04-14"
filter: "ind.insurance_"
---# InsPolicyService:createTransaction

InsPolicyService:createTransaction[](https://help.salesforce.com/s?language=en_US)

You are here:

1.  [Salesforce Help](/s/?language=en_US)
2.  [Docs](/s/products?language=en_US)
3.  [Digital Insurance](https://help.salesforce.com/s/articleView?id=ind.insurance_admin_standard.htm&language=en_US&type=5)

# InsPolicyService:createTransaction

Use this service to create a transaction on a target policy.

[](https://help.salesforce.com/s?language=en_US)

[](https://help.salesforce.com/s?language=en_US)Class: `InsPolicyService`

Method: `createTransaction`

[](https://help.salesforce.com/s?language=en_US)This service lets you maintain policy values and track policy activity.

[](https://help.salesforce.com/s?language=en_US)Note

This service works with the Salesforce Financial Services Cloud.

[](https://help.salesforce.com/s?language=en_US)

## How It Works

1.  The service takes the `assetId` or `policyId` from the input JSON and sets it as the `AssetId__c` field on the transaction.
    
2.  Takes the `transactionType` from the input JSON and sets it as the `Type__c` field on the transaction.
    
3.  Takes the `effectiveDate` from the input JSON and sets it as the `PostDate__c` and `TransactionDate__c` fields on the transaction.
    
4.  (Optional) Takes the amount from the input JSON and sets it as the `Amount__c` field on the transaction.
    
5.  (FSC only) Takes a `postDataDRBundleName` or a `postDataCustomClassName` Omnistudio Data Mapper as an input.
    
6.  (Optional) Takes the `transactionName` from the input JSON and sets it as the Name field on the transaction.
    
7.  (Optional) Takes the `additionalFields` map from the input JSON and sets any transaction fields that are specified in the map.
    
8.  (Non-FSC) Creates a new `AssetTransaction_c` record and returns the record Id in the `transactionId` field.
    
    [](https://help.salesforce.com/s?language=en_US)Or
    
    [](https://help.salesforce.com/s?language=en_US)(FSC) Creates a new `InsurancePolicyTransaction` or `InsurancePolicyTransaction_c` record and returns the record Id in the `transactionId` field.
    
9.  (FSC only) Outputs data in the `postDataDRBundleName` you specify.
    
10.  If `calculateCommission` is `true`, the service calls `InsurancePolicyService.calculateAndSaveCommission`, which prepares the input for the `InsCommissionService.calculate` and `InsCommissionService.saveCommissions` services. After the calculate service processes the input, the save service stores the calculated value in `TotalCommissionAmount`.
     

[](https://help.salesforce.com/s?language=en_US)

## Remote Options

| 
Remote Option

 | 

Description

 |
| --- | --- |
| 

`calculateCommission`

 | 

`true` or `false`

When set to `true`, the service calculates commissions for the root items and saves the total amount to `TotalCommissionAmount`.

[](https://help.salesforce.com/s?language=en_US)When set to `false` (the default), the service doesn't calculate commissions.

[](https://help.salesforce.com/s?language=en_US)Note

If you set this option to true, you also need to input at least one of the producer or production code values: `producerId` , `productionCodeId`, or `productionCodeName`.







 |
| 

[](https://help.salesforce.com/s?language=en_US)`commissionType`

 | 

Optional.

[](https://help.salesforce.com/s?language=en_US)Type of commission (for example, Bonus or Standard).

 |
| 

[](https://help.salesforce.com/s?language=en_US)`commissionStatus`

 | 

Optional.

[](https://help.salesforce.com/s?language=en_US)Status of the commission (for example, Pending, Paid, or Waived).

 |
| 

`producerId`

 | 

Optional.

[](https://help.salesforce.com/s?language=en_US)The processing producer ID, that is, the producer used to retrieve the commissionScheduleId and calculate the commission amount.

[](https://help.salesforce.com/s?language=en_US)Assigned to `InsurancePolicy.ProducerId`.

 |
| 

`productionCodeId`

 | 

Optional.

[](https://help.salesforce.com/s?language=en_US)The production code ID.

[](https://help.salesforce.com/s?language=en_US)Assigned to `InsurancePolicy.ProductionCodeId__c`.

 |
| 

`productionCodeName`

 | 

Optional.

[](https://help.salesforce.com/s?language=en_US)The production code name passed to the InsCommissionService.calculate service.

[](https://help.salesforce.com/s?language=en_US)If you do not input `productionCodeId`, the service uses `productionCodeName` to look up the `productionCodeId`. If you input both values but they don't match, `productionCodeId` takes precedence.

 |

[](https://help.salesforce.com/s?language=en_US)

## Input JSON

This service looks for the following key/value pairs:

[](https://help.salesforce.com/s?language=en_US)

-   `assetId` or `policyId`
    
    Id of policy on which the transaction will be created
    
-   `transactionType`
    
    Type of transaction
    
-   `effectiveDate`
    
    Post date and transaction date of transaction
    
-   `amount`
    
    (Optional) Transaction amount
    
-   `transactionName`
    
    (Optional) Name of transaction. If not provided, the name is defaulted to the transaction type.
    
-   `additionalFields`
    
    (Optional) Map of additional transaction fields to be set
    

[](https://help.salesforce.com/s?language=en_US)For example:

[](https://help.salesforce.com/s?language=en_US)`{ 	"assetId": "02i5A000005iF1MQAU", 	"transactionType": "Premium Paid", 	"effectiveDate": "2018-10-04", 	"amount": "100", 	"transactionName": "My Transaction", 	"additionalFields": { 		"StatementId__c": "a4f5A000001QFE0QAO" 	} }`

[](https://help.salesforce.com/s?language=en_US)

## Output JSON

The service returns the following keys and their values:

[](https://help.salesforce.com/s?language=en_US)

-   `transactionId`
    
    Id of transaction record created
    

[](https://help.salesforce.com/s?language=en_US)For example:

[](https://help.salesforce.com/s?language=en_US)`{     "transactionId": "a3g5A000000YRPpQAO" }`

[](https://help.salesforce.com/s?language=en_US)

## Additional Information

Use the `additionalFields` map to set any extra fields on the transaction that are not specified in the input parameters. For example, to set the `StatementId__c` field, the `additionalFields` map looks like this:

[](https://help.salesforce.com/s?language=en_US)`{     “additionalFields”: {     “StatementId__c” : “02i1I000001jaEhQAI”     } }`

Did this article solve your issue?

Let us know so we can improve!

YesNo