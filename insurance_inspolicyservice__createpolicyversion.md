---
title: "InsPolicyService:createPolicyVersion"
source: "https://help.salesforce.com/s/articleView?id=ind.insurance_inspolicyservice__createpolicyversion.htm&language=en_US&type=5"
scraped: "2026-04-14"
filter: "ind.insurance_"
---# InsPolicyService:createPolicyVersion

InsPolicyService:createPolicyVersion[](https://help.salesforce.com/s?language=en_US)

You are here:

1.  [Salesforce Help](/s/?language=en_US)
2.  [Docs](/s/products?language=en_US)
3.  [Digital Insurance](https://help.salesforce.com/s/articleView?id=ind.insurance_admin_standard.htm&language=en_US&type=5)

# InsPolicyService:createPolicyVersion

Use this service to create a new version of an existing policy, while maintaining the existing policy record as-is.

[](https://help.salesforce.com/s?language=en_US)

This service enables policy versioning. All changes to a policy are tracked in different versions of that policy. You can use it in modify policy and cancel policy OmniScripts and Integration Procedures. You can also use this service to reinstate expired and canceled policies.

[](https://help.salesforce.com/s?language=en_US)

This service works with the Salesforce Financial Services Cloud for optional Payment Schedule creation support.

[](https://help.salesforce.com/s?language=en_US)

[](https://help.salesforce.com/s?language=en_US)Class: `InsPolicyService`

[](https://help.salesforce.com/s?language=en_US)

Method: `createPolicyVersion`

[](https://help.salesforce.com/s?language=en_US)

## How It Works

1.  Takes the `assetId` or `policyId` of the current policy, and the JSON indicated by the `inputKey`.
    
2.  Creates a clone of the original policy.
    
3.  If there's an existing payment schedule, the service updates the payment schedule and creates a payment schedule entry on effective date of endorsement. If `useIsPaidFlag` is true, all the future payment schedule entries (from effective date) without transactions (for which the status field is `Valid` and `isPaid` field is unchecked) are updated based on newer values of premium, tax, and fee. The new payment schedule entry contains the adjusted values of premium, tax, and fee based on new premiums, taxes, and fees and updated payment schedule entries. Also, the contribution records of policy components in each payment schedule entry are updated.
    
4.  The service uses the previous Policy's Premium Calculation Method, Payment Type, and Premium Frequency, and the new Policy's Total Premium For Term, Total Fee For Term, and Total Tax For Term to generate the modified payment schedule. In addition to the creation of the transaction, transaction breakdown data populates into the transaction detail object. This object stores data about how much each asset, participant, or coverage contributes to total transaction amounts in terms of premium, tax, and fees. Only assets, participants, and coverages with at least one value greater than zero for premium, tax, or fees are displayed.
    
    Note Premium Calculation Method, Payment Type, and Premium Frequency aren't copied over from previous policy and must be passed as inputs to the service through the JSON.
    
5.  If `includeRevenueSchedule` is set to true, it calls revenue schedule service to modify the revenue schedule.
    
6.  If it is the first modification of this policy, the service stamps the `originalVersionId__c` and `previousVersionId__c` with the same `assetId`. If this is not the first modification of this policy, the service carries over the `OriginalVersionId__c` to the new version and stamps the previous `assetId` to `PreviousVersionId__c` in the new policy.
    
7.  If the `taxesAndFees`, `taxAmount`, and/or `feeAmount` nodes are included in the input JSON, the corresponding tax/fee fields and/or records are created and prorated on the new version of the policy.
    
8.  If applicable, an InsurancePolicyTransaction will be created for the payment adjustment.
    
9.  If `calculateCommission` is `true`, the service calls `InsurancePolicyService.calculateAndSaveCommission`, which prepares the input for the `InsCommissionService.calculate` and `InsCommissionService.saveCommissions` services. After the calculate service processes the input, the save service stores the calculated value in `TotalCommissionAmount`, and then rolls up the value and adds it to the `TotalCommissionAmount` of the original Policy.
    
10.  If the `disableAttributeCategories` flag in the `getquotedetail` service is set to true, the service omits the attributeCategory node from the response and the `createPolicyVersion` service fails to create policy terms. To make sure that the `createPolicyVersion` service creates policy terms, set the the `disableAttributeCategories` flag in the in the `getQuoteDetail` service to false.

Note The service additionally supports endorsements of policies where the duration of the original policy version is less than 365 days, or less than 366 days in a leap year. See [Considerations and Limitations for Insurance Policies](https://help.salesforce.com/s/articleView?id=ind.insurance_considerations_and_limitations_for_insurance_policies.htm&language=en_US&type=5).

[](https://help.salesforce.com/s?language=en_US)

## Taxes and Fees

Here's how this service works for taxes and fees:

-   If the `taxesAndFees` field is specified on a JSON record, a corresponding `AssetPricingAdjustment__c` record persists for each item in the `taxesAndFees` list.
    
-   If the `taxAmount` field is specified on a JSON record, the `TaxAmount__c` field will be set to the value of the `taxAmount` field on the created `AssetItem` object.
    
-   If the `feeAmount` field is specified on a JSON record, the `FeeAmount__c` field will be set to the value of the `feeAmount` field on the created `AssetItem`.
    

As far as the current (newly created policy) is concerned:

-   If the current policy has a `TotalTaxAmount__c`, that value is prorated over the effective and end dates and set on the `TotalTaxForTerm__c` field.
    
-   If the current policy has a `TotalFeeAmount__c`, that value is prorated over the effective and end dates and set on the `TotalFeeForTerm__c` field.
    
-   If the `AssetItem` on the current policy has a `TaxAmount__c` that value is prorated over the effective and end dates and set on the `ProratedTaxAmount__c` field.
    
-   If the `AssetItem` on the current policy has a `FeeAmount__c` that value is prorated over the effective and end dates and set on the `ProratedFeeAmount__c` field.
    

For policies already created, here's how the taxes and fees are passed around:

-   If the previous policy has a `TotalTaxAmount__c`, that value is prorated over the new effective and end dates, and is set on the `TotalTaxForTerm__c` field.
    
-   If the previous policy has a `TotalFeeAmount__c`, that value is prorated over the new effective and end dates, and is set on the `TotalFeeForTerm__c` field.
    
-   If the AssetItem fields have a `TaxAmount__c`, then that value is prorated over the new effective and end dates, and is set on the `ProratedTaxAmount__c` field.
    
-   If the  `AssetItem` fields on the previous policy have a `FeeAmount__c`, that value is prorated over the new effective and end dates, and is set on the `ProratedFeeAmount__c` field.
    

Finally, if the `createTransaction` option (see below) is set to true, and the new policy version has associated taxes and fees, the `TaxAmount__c` and `FeeAmount__c` fields on the created transaction are set to the difference between the new (current) policy and the previous policy’s `TotalTaxForTerm__c` and `TotalFeeForTerm__c`.

[](https://help.salesforce.com/s?language=en_US)

## Remote Options

| 
Option

 | 

Description

 |
| --- | --- |
| 

`assetId` or `policyId`

 | 

Required.

The Id of the current policy.

 |
| 

[](https://help.salesforce.com/s?language=en_US)`createContactForParticipants`

 | 

Optional.

[](https://help.salesforce.com/s?language=en_US)`true` or `false`

[](https://help.salesforce.com/s?language=en_US)Defaults to `true`.

[](https://help.salesforce.com/s?language=en_US)If `false`, the service doesn't create contact records.

 |
| 

`createInsuredItemsRelationships`

 | 

`true` or `false`

If this option is set to true, you can specify a list of `instanceKey` > `parentInstanceKey` relationships between insured items.

This option supports parent > child and parent > child > grandchild insured item relationships.

 |
| 

`createTransaction`

 | 

Optional.

`true` or `false`

Defaults to `false`.

If `true`, the service creates a transaction that will be used by the revenue schedule services.

 |
| 

`effectiveDate`

 | 

`“YYYY-MM-DD HH:MM:SS”` or `%OmniScriptDataElement%`

The date that the policy goes into effect.

If there's no `effectiveDate` value in the option map, the service looks for it in the `rootAttributes` map. If the service can't find an `effectiveDate` there, it uses today's date.

If you're using the Insurance Industries Extension package, the timestamp value in the `effectiveDate` option is ignored. Instead, the effective date timestamp value is set to 12:00 a.m. of the selected effective date, and the expiration date value is set to 11:59 p.m. for the selected expiration date. The timestamp is set by using the user's specified timezone.

 |
| 

`getDataCustomClassName`

 | 

Optional.

The name of the custom class this service uses to retrieve policy (asset) information.

[](https://help.salesforce.com/s?language=en_US)If you're using Salesforce FSC, you must specify either this option or `postDataDRBundleName`.

Default value is set to **GetInsurancePolicy**.

 |
| 

`getDataDRBundleName`

 | 

Optional,

[](https://help.salesforce.com/s?language=en_US)The name of the Data Mapper this service uses to retrieve policy (asset) information.

[](https://help.salesforce.com/s?language=en_US)If you're using Salesforce FSC, you must specify either this option or `getDataCustomClassName`.

-   If you specify both, the service uses the `getDataDRBundleName` value.
    
-   If you don't specify either, the service uses the default value for `getDataCustomClassName` (**GetInsurancePolicy**).
    

 |
| 

`includePaymentSchedule`

 | 

Optional.

`True` if the payment schedule will be updated for the policy.

Default is `false`.

 |
| 

`includeRevenueSchedule`

 | 

Optional. Used only if `createTransaction` is set to `true`.

`true` or `false`

If `true`, this option calls InsPolicyRevenueScheduleService: modify

 |
| 

`inputKey`

 | 

Required.

`%theJSONyouneed%`

 |
| 

`isCreatingPolicyTerms`

 | 

`true` or `false`

When set to `true`, the service returns a `policyTermIds` node in the output JSON.

 |
| 

`postDataCustomClassName`

 | 

Optional.

The name of the custom class this service uses to save the new policy version.

If you're using Salesforce FSC, you must specify either this option or `postDataDRBundleName`.

Default value is set to **PostInsurancePolicy**.

 |
| 

`postDataDRBundleName`

 | 

Optional.

The name of the Data Mapper this service uses to save the new policy version.

If you're using SalesForce FSC, you must specify either this option or `postDataCustomClassName`.

-   If you specify both, the service uses the `postDataDRBundleName` value.
    
-   If you don't specify either, the service uses the default value for `postDataCustomClassName` (**PostInsurancePolicy**).
    

 |
| 

`transactionType`

 | 

Optional. Used only if `createTransaction` is set to `true`.

If no value is provided for `transactionType`, it defaults to `Changed/Endorsed`.

 |
| 

`updateDataCustomClassName`

 | 

Optional.

Updates the current policy.

If you're using Salesforce FSC, you must specify either this option or `updateDataDRBundleName`.

Default value is set to **PostInsurancePolicy**.

 |
| 

`updateDataDRBundleName`

 | 

Optional.

The name of the Data Mapper this service uses to update the current policy.

If you're using Salesforce FSC, you must specify either this option or `updateDataCustomClassName`.

[](https://help.salesforce.com/s?language=en_US)

-   If you specify both, the service uses the `updateDataDRBundleName` value.
    
-   If you don't specify either, the service uses the default value for `updateDataCustomClassName` (**PostInsurancePolicy**).
    

 |
| 

`useLocalTimezone`

 | 

`true` or `false`

Defaults to `true`.

When set to `true`, this service uses the local timezone in which the policy version is created.

When set to `false`, this services uses GMT as the timezone.

 |
| 

`calculateCommission`

 | 

[](https://help.salesforce.com/s?language=en_US)`true` or `false`

[](https://help.salesforce.com/s?language=en_US)When set to `true`, the service calculates commissions for the root items and saves the total amount to `TotalCommissionAmount`.

[](https://help.salesforce.com/s?language=en_US)When set to `false` (the default), the service doesn't calculate commissions.

[](https://help.salesforce.com/s?language=en_US)Note

If you set this option to true, you also need to input at least one of the producer or production code values: `producerId` , `productionCodeId`, or `productionCodeName`.







 |
| 

`commissionType`

 | 

Optional.

[](https://help.salesforce.com/s?language=en_US)Type of commission (for example, Bonus or Standard).

 |
| 

`commissionStatus`

 | 

Optional.

[](https://help.salesforce.com/s?language=en_US)Status of the commission (for example, Pending, Paid, or Waived).

 |
| 

[](https://help.salesforce.com/s?language=en_US)`producerId`

 | 

Optional.

[](https://help.salesforce.com/s?language=en_US)The processing producer ID, that is, the producer used to retrieve the commissionScheduleId and calculate the commission amount.

[](https://help.salesforce.com/s?language=en_US)Assigned to `InsurancePolicy.ProducerId`.

 |
| 

[](https://help.salesforce.com/s?language=en_US)`productionCodeId`

 | 

Optional.

[](https://help.salesforce.com/s?language=en_US)The production code ID.

[](https://help.salesforce.com/s?language=en_US)Assigned to `InsurancePolicy.ProductionCodeId__c`.

 |
| 

[](https://help.salesforce.com/s?language=en_US)`productionCodeName`

 | 

Optional.

[](https://help.salesforce.com/s?language=en_US)The production code name passed to the InsCommissionService.calculate service.

[](https://help.salesforce.com/s?language=en_US)If you do not input `productionCodeId`, the service uses `productionCodeName` to look up the `productionCodeId`. If you input both values but they don't match, `productionCodeId` takes precedence.

 |
| 

[](https://help.salesforce.com/s?language=en_US)`memberPlanIntegrationProcedure`

 | 

[](https://help.salesforce.com/s?language=en_US)Initiates a custom integration procedure based on the user configuration. When you use this option, it passes all options of the service to the custom integration procedure and all policy Ids as input to integrate with the object, for example the insurance policy object with the member plan.

 |
| 

`ratingDate`

 | 

The rating date that was used to price the input JSON.

Note You can't pass a specific time for ratingField as the field type is Date. So, the rating date timestamp defaults to 12:00 am.





 |
| `term` | 

The term of the policy that the service creates.

InsPolicyService:createPolicyVersion supports only annual policy terms.

 |
| 

`useIsPaidFlag`

 | 

Optional

Specifies if `IsPaid` flag must be enabled or not.

If true, `isPaid` field on payment schedule entry object is considered during premium, tax, and fee calculation.

The default value is false.

 |

[](https://help.salesforce.com/s?language=en_US)

## Input JSON

This service looks for the `inputKey` specified within the product JSON.

```
"policyJson": {
  "productConfigurationDetail": {
    "insuredItems": {
      "Auto": [{
          "instanceKey": "2015 Lexus LX250",
          "autoLicNum": "Lexus",
          "autoModel": "LX150",
          "autoYear": 2015,
          "BodyClass": "Sedan/Saloon",
          "VehicleType": "PASSENGER CAR",
          "isPrimary": true
                                        "isParent": true
        },
        {
          "instanceKey": "2006 Honda Odyssey",
          "autoLicNum": "Honda",
          "autoModel": "Odyssey",
          "autoYear": 2006,
          "BodyClass": "Minivan",
          "VehicleType": "MULTIPURPOSE PASSENGER VEHICLE (MPV)",
          "isPrimary": true
                                        "isParent": true
        },
        {
          "instanceKey": "2018 530 BMW",
          "autoLicNum": "530",
          "autoModel": "BMW",
          "autoYear": 2018,
          "BodyClass": "Sedan/Saloon",
          "VehicleType": "PASSENGER CAR",
          "isPrimary": true
                                        "isParent": true
        },
        {
          "instanceKey": "2016 Camry Toyota",
          "autoLicNum": "Camry",
          "autoModel": "Toyota",
          "autoYear": 2016,
          "BodyClass": "Sedan/Saloon",
          "VehicleType": "PASSENGER CAR",
          "isPrimary": true
                                        "isParent": true
        }
      ],
      "Driver": [{
          "AGE": 20,
          "instanceKey": "Joan Smith",
          "FN": "Joan",
          "GENDER": "Female",
          "LN": "Smith",
          "isPrimary": false
                                        "isParent": false
        },
        {
          "AGE": 30,
          "instanceKey": "John Smith",
          "FN": "John",
          "GENDER": "Male",
          "LN": "Smith",
          "isPrimary": false
                                        "isParent": false
        },
        {
          "AGE": 30,
          "instanceKey": "Robert Henderson",
          "FN": "Robert",
          "GENDER": "Male",
          "LN": "Henderson",
          "isPrimary": false
                                        "isParent": false    
        },
        {
          "AGE": 20,
          "instanceKey": "Kinsey Schell",
          "FN": "Kinsey",
          "GENDER": "Female",
          "LN": "Schell",
          "isPrimary": false
                                        "isParent": false
        }
      ]
    },
    "accountId": "001f400000RrQSrAAN"
  }
```

If the `isCreatingPolicyTerms` remote option is set to `true`, a `policyTermIds` node is included. Here's an example of a `policyTermIds` node:

```
{  
   "policyId": "02i6g000000h110AAA",
   "policyTermIds": [
    "a5X6g000001LeUUEA0",
    "a5X6g000001LeUVEA0",
    "a5X6g000001LeUWEA0",
    "a5X6g000001LeUXEA0",
    "a5X6g000001LeUYEA0",
    "a5X6g000001LeUZEA0",
    "a5X6g000001LeUaEAK",
    "a5X6g000001LeUbEAK",
    "a5X6g000001LeUcEAK",
    "a5X6g000001LeUdEAK",
    "a5X6g000001LeUeEAK",
    "a5X6g000001LeUfEAK"
  ]
}
```

[](https://help.salesforce.com/s?language=en_US)

## Output JSON

The service returns the new policy version number in the output JSON.

[](https://help.salesforce.com/s?language=en_US)`{     "policyId": "02i0b00000uRwhVAAS"     "error": "ok" }`

Did this article solve your issue?

Let us know so we can improve!

YesNo