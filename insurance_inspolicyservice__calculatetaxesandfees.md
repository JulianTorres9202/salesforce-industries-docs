---
title: "InsPolicyService:calculateTaxesAndFees"
source: "https://help.salesforce.com/s/articleView?id=ind.insurance_inspolicyservice__calculatetaxesandfees.htm&language=en_US&type=5"
scraped: "2026-04-14"
filter: "ind.insurance_"
---# InsPolicyService:calculateTaxesAndFees

InsPolicyService:calculateTaxesAndFees[](https://help.salesforce.com/s?language=en_US)

You are here:

1.  [Salesforce Help](/s/?language=en_US)
2.  [Docs](/s/products?language=en_US)
3.  [Digital Insurance](https://help.salesforce.com/s/articleView?id=ind.insurance_admin_standard.htm&language=en_US&type=5)

# InsPolicyService:calculateTaxesAndFees

Use this service to calculate and save taxes and fees on a target asset (policy).

[](https://help.salesforce.com/s?language=en_US)

[](https://help.salesforce.com/s?language=en_US)Class: `InsPolicyService`

[](https://help.salesforce.com/s?language=en_US)

Method: `calculateTaxesAndFees`

Tax and fee information is saved on the asset (policy) object, and on the `AssetCoverage__c`, `AssetInsuredItem__c`, and `AssetPartyRelationship__c` fields.

This service also saves itemized taxes as described in step 3 below.

Note

This service supports the Salesforce Financial Services Cloud.

[](https://help.salesforce.com/s?language=en_US)

## How It Works

1.  The service takes the `assetId`, the `effectiveDate` (or `EffectiveDate_c` on the target policy, or today's date if the value is null).
    
2.  Based on the taxes and fees items associated with the policy, the coverages, and/or the insured items, either does the simple calculation specified or calls the calculation procedure or Integration Procedure required to calculate the taxes and fees.
    
    [](https://help.salesforce.com/s?language=en_US)Note
    
    This service can also call external systems to calculate taxes and fees. Specify these systems when you [set up taxes and fees](https://help.salesforce.com/s/articleView?id=ind.insurance_taxes_and_fees_608285.htm&language=en_US&type=5 "Calculate applicable taxes on Vlocity Insurance quotes and policies, and applicable fees on Vlocity Health and Vlocity Insurance quotes and policies.").
    
3.  If saveChanges is set (or defaulted) to `true`, saves the calculated taxes and fees in one of three ways.
    
    -   If an `AssetItem` has calculated taxes and fees, the service saves an `AssetPricingAdjustment__c` record representing that tax/fee.
        
        [](https://help.salesforce.com/s?language=en_US)The `AssetPricingAdjustment__c` record holds the calculated amount (`Amount__c`), the associated `AssetItem` (`AssetCoverageId__c`/`AssetInsuredItemId__c`/`AssetPartyRelationshipId__c`) and `Asset` (`AssetId__c`) , the type (tax or fee; `AdjustmentType__c`), and the associated tax/fee (`PriceListEntryId__c`).
        
        [](https://help.salesforce.com/s?language=en_US)`AssetPricingAdjustment__c` has an associated `AssetItem`, so the `ApplicableItemType__c` field will also be set. This setting indicates which item type is applicable: Coverage, Insured Item, or Party Relationship.
        
        [](https://help.salesforce.com/s?language=en_US)If the `transactionId` option is specified, the `AssetTransactionId__c` field is set to the `transactionId` value.
        
    -   If an `AssetItem` or its children have calculated taxes, the sum of the calculated taxes on itself and its children will be stored on the `TaxAmount__c` field.
        
    -   If an `AssetItem` or its children have calculated fees, the sum of the calculated fees on itself and its children will be stored on the `FeeAmount__c` field.
        
    
    [](https://help.salesforce.com/s?language=en_US)Note
    
    If `saveItemizedTaxesAndFees` is set to `false`, the `AssetPricingAdjustment__c` records are not saved. The `TotalTaxAmount__c` and `TotalFeeAmount__c` amounts on the asset (policy) is set to 0. All other values are still saved.
    
4.  At the Asset level, the sum of all of the tax amounts and fee amounts are stored on the `TotalTaxAmount__c` and `TotalFeeAmount__c` fields respectively.
    
5.  If the target asset (policy) is not the original version of the policy, the tax and fee amounts will be prorated based on the asset’s `EffectiveDate__c` and `ExpirationDate__c`. The prorated tax and fee amounts for an `AssetItem` is stored on the `ProratedTaxAmount__c` and `ProratedFeeAmount__c` fields. The prorated tax and fee amounts for the asset are stored on the `TotalTaxForTerm__c` and `TotalFeeForTerm__c` fields.
    
6.  If a `transactionId` option is provided, the change in total prorated tax and fee amounts (the sum of the prorated tax and fee amounts across the target asset version and all previous versions of the asset) between the current asset version and the previous asset versions are stored on the target transaction’s `TaxAmount__c` and `FeeAmount__c` fields respectively.
    

[](https://help.salesforce.com/s?language=en_US)

## Remote Options

| 
Option

 | 

Description

 |
| --- | --- |
| 

`assetId`

 | 

Required

Id of the asset (policy) this service will calculate taxes and fees for.

 |
| 

`transactionId`

 | 

Optional

The specified transaction will be updated with calculated tax and fee amounts.

 |
| 

`jurisdictionIds`

 | 

Optional

Calculates taxes and fees associated with the provided jurisdictions only.

 |
| 

`effectiveDate`

 | 

Optional

Calculate taxes and fees that are effective on the specified date only.

If not provided, the value defaults to the target policy’s `EffectiveDate__c`. If `EffectiveDate__c` is null, value defaults to today’s date.

 |
| 

`saveChanges`

 | 

Optional

`true` or `false`

Defaults to `true`.

If `true`, persist calculated taxes and fees on the policy (asset).

If `false`, do not persist the calculated taxes and fees on the policy (asset).

 |

[](https://help.salesforce.com/s?language=en_US)

## Input JSON

This service doesn't take an input JSON.

[](https://help.salesforce.com/s?language=en_US)

## Output JSON

The service returns the itemized taxes and fees in the product/child product hierarchy. Here's an example:

```
{
  "productId": 1,
  "productName": "Product",
  "ProductCode": "P",
  "taxesAndFees": [{
    "Id": 1,
    "Amount__c": 10,
    "PriceListEntryId__c": 11,
    "AdjustmentType__c": "Tax"
  }, {
    "Id": 2,
    "Amount__c": 15,
    "PriceListEntryId__c": 12,
    "AdjustmentType__c": "Fee"
  }],
  "taxAmount": 25
  "feeAmount": 30
  "childProducts": [{
    "productId": 2,
    "productName": "Insured Item",
    "ProductCode": "II",
    "instanceKey": "My Insured Item",
    "taxesAndFees": [{
      "Id": 3,
      "Amount__c": 15,
      "PriceListEntryId__c": 16,
      "AdjustmentType__c": "Tax"
    }],
    "taxAmount": 15
  }, {
    "productId": 3,
    "productName": "Coverage",
    "ProductCode": "C",
    "taxesAndFees": [{
      "Id": 4,
      "Amount__c": 15,
      "PriceListEntryId__c": 21
      "AdjustmentType__c": "Fee"
    }],
    "feeAmount": 15
  }]
}
```

Did this article solve your issue?

Let us know so we can improve!

YesNo