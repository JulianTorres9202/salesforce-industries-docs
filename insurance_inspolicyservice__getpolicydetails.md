---
title: "InsPolicyService:getPolicyDetails"
source: "https://help.salesforce.com/s/articleView?id=ind.insurance_inspolicyservice__getpolicydetails.htm&language=en_US&type=5"
scraped: "2026-04-14"
filter: "ind.insurance_"
---# InsPolicyService:getPolicyDetails

InsPolicyService:getPolicyDetails[](https://help.salesforce.com/s?language=en_US)

You are here:

1.  [Salesforce Help](/s/?language=en_US)
2.  [Docs](/s/products?language=en_US)
3.  [Digital Insurance](https://help.salesforce.com/s/articleView?id=ind.insurance_admin_standard.htm&language=en_US&type=5)

# InsPolicyService:getPolicyDetails

Use this service to get the coverages, insured items, pricing, and other information for an existing insurance policy, including optional coverages that weren't selected.

Note

To get the policy details, you must have read access to the Insurance Policy records. Configure your sharing settings and sharing rules to provide access to the requested policy record. See [Share Objects and Fields](https://developer.salesforce.com/docs/atlas.en-us.securityimplguide.meta/securityimplguide/security_data_sharing.htm).

[](https://help.salesforce.com/s?language=en_US)

For example, you can use this service to get and display existing policy details in a policy modification OmniScript or Integration Procedure.

[](https://help.salesforce.com/s?language=en_US)

[](https://help.salesforce.com/s?language=en_US)Class: `InsPolicyService`

[](https://help.salesforce.com/s?language=en_US)

Method: `getPolicyDetails`

[](https://help.salesforce.com/s?language=en_US)

## How It Works

1.  Uses the `policyId` or `assetId` to get the policy record and its associated coverages and insured items.
    
2.  Goes to the product spec associated with the policy to get unselected optional coverage specs.
    
3.  Returns a JSON structure that includes insured items, policy coverages, and optional coverages.
    

[](https://help.salesforce.com/s?language=en_US)

## Surcharges

If the `calculateTaxesAndFees` service is used, the following fields are returned for the following records and for the policy:

For each `AssetCoverage__c`, `AssetInsuredItem__c`, and `AssetPartyRelationship__c` record, the following fields are returned, as long as the fields are not null:

-   `taxAmount` and `TaxAmount__c` (values are equivalent)
    
-   `feeAmount` and `FeeAmount__c` (values are equivalent)
    
-   `totalTaxFeeAmount__c` and `totalTaxFeeAmount` (equivalent to `TaxAmount__c` + `FeeAmount__c`)
    
-   `ProratedTaxAmount__c`
    
-   `ProratedFeeAmount__c`
    
-   `TotalAmount__c`
    
-   `TotalProratedAmount__c`
    

The following fields are returned for the policy if the fields are not null:

-   `TotalTaxAmount__c`
    
-   `TotalFeeAmount__c`
    
-   `totalTaxFeeAmount__c` and `TotalTaxFeeAmount` (equivalent to `TotalTaxAmount__c` + `TotalFeeAmount__c`)
    
-   `TotalTaxForTerm__c`
    
-   `TotalFeeForTerm__c`
    
-   `TotalAmount__c`
    
-   `TotalAmountForTerm__c`
    

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

or

`policyId`

 | 

Required.

The Id of the policy (asset) to get details for.

The sObject type for this Id determines which data model the service uses, Asset-based or Salesforce FSC.

If you provide an `assetId` without specifying `getDataDRBundleName` or `getDataCustomClassNameDR`, the service uses the Asset-based data model automatically.

If you provide a `policyId` without specifying `getDataDRBundleName` or `getDataCustomClassNameDR`, the service uses the Salesforce FSC data model automatically.

 |
| 

`getCoverages`

 | 

`%instanceKey%`

Returns coverage details for the specified instance only.

 |
| 

`getDataDRBundleName`

 | 

Optional.

Enter a DataRaptor to use to retrieve policy (asset) information.

If you specify both `getDataDRBundleName` and `getDataCustomClassName`, the service uses the specified DataRaptor, not the custom class. If you specify `getDataDRBundleName` but not `getDataCustomClassName`, the service uses the specified DataRaptor, not the default class.

 |
| 

`getDataCustomClassName`

 | 

Optional.

Enter a custom class to use to retrieve policy (asset) information. This value overrides the default class used to retrieve information.

 |
| 

`includeTaxesAndFees`

 | 

`true` or `false`

Defaults to `true`.

When set to `true`, returns tax and fee fields in the policy JSON.

If provided and set to `true`, returns `AssetPricingAdjustment__c` records associated with each `AssetCoverage__c`, `AssetInsuredItem__c`, `AssetPartyRelationship__c`, or Policy via the `taxesAndFees` field.

 |
| 

`omitAttributeCategory`

 | 

`true` or `false`

When set to `true`, the service does not return attributes for the products (insured items, insured parties, coverages) in the policy.

 |
| 

`omitCoverages`

 | 

`true` or `false`

When set to `true`, the service returns insured items, insured parties child insured items but not coverages.

 |

[](https://help.salesforce.com/s?language=en_US)

## Input JSON

This service doesn't use the input JSON.

[](https://help.salesforce.com/s?language=en_US)

## Output JSON

The service returns an array of records from the policy (asset) object. These records are structured similarly to product records, but include additional fields.

The service also returns records it pulls from the product, including optional coverages that aren't part of the policy object (they weren't selected as coverages for this policy).

```
"totalSize": 1,
"records": [{
    "displaySequence": -1,
    "Id": "02if4000001vM1LAAU",
    "productId": "01tf4000001lKNQAA2",
    "productName": "Watercraft",
    "EffectiveStart": "2018-05-21",
    "EffectiveEnd": "2019-05-20",
    "Price": 20,
    "PricingFormula__c": "wcPropertyNet + wcLiabilityNet + wcUninsuredNet + wcMedPaymentsNet + wcPersonalEffectsNet + wcTrailerNet + wcTowingNet + wcFishingEquipNet + wcBoatLiftNet",
    "ProductCode": "Watercraft",
    "CalculatedPriceData": {
      "ID": "0",
      "wcBoatLiftNet": 20
    },
    "childProducts": {
      "totalSize": 1,
      "records": [...]
    ]
```

In addition to fields described in the Product JSON Structure Model, the output JSON for this service includes the following fields from the policy (asset) object (using the `GetPolicyDetailsFields` field set):

-   `productId`
    
-   `productName`
    
-   `EffectiveStart`
    
-   `EffectiveEnd`
    
-   `StandardPremium__c`
    
-   `PricingSource__c`
    
-   `PricingFormula__c`
    
-   `productCode`
    
-   `term`
    
-   `AssetCoverage__c`
    
    All accessible fields
    
-   `AssetInsuredItem__c`
    
    All accessible fields
    

## Examples

The service is typically used in OmniScripts that modify or cancel policies.

Did this article solve your issue?

Let us know so we can improve!

YesNo