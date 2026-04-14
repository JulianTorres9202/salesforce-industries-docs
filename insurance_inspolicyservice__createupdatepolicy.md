---
title: "InsPolicyService:createUpdatePolicy"
source: "https://help.salesforce.com/s/articleView?id=ind.insurance_inspolicyservice__createupdatepolicy.htm&language=en_US&type=5"
scraped: "2026-04-14"
filter: "ind.insurance_"
---# InsPolicyService:createUpdatePolicy

InsPolicyService:createUpdatePolicy[](https://help.salesforce.com/s?language=en_US)

You are here:

1.  [Salesforce Help](/s/?language=en_US)
2.  [Docs](/s/products?language=en_US)
3.  [Digital Insurance](https://help.salesforce.com/s/articleView?id=ind.insurance_admin_standard.htm&language=en_US&type=5)

# InsPolicyService:createUpdatePolicy

Use this service to create a new insurance policy or to update an existing policy with new information.

[](https://help.salesforce.com/s?language=en_US)

This service can be used with Salesforce Financial Services Cloud for optional Payment Schedule creation support.

[](https://help.salesforce.com/s?language=en_US)

[](https://help.salesforce.com/s?language=en_US)Class: `InsPolicyService`

[](https://help.salesforce.com/s?language=en_US)

Method: `createUpdatePolicy`

[](https://help.salesforce.com/s?language=en_US)

## How it works

1.  The service searches the input JSON for the `inputKey`. The `inputKey` node contains the information the service needs to create or update a policy. The information this service requires includes:
    
    -   `accountId`
        
    -   `term`
        
    -   `productConfigurationDetail` records
        
    -   `insuredItems` records (optional)
        
    -   `endDate`
        
    -   `effectiveDate`
        
2.  Creates a Policy (asset) object.
    
3.  If there's an existing payment schedule for the policy, the service returns an error message.
    
4.  If there's an initial payment, an **InsurancePolicyTransaction** will be created. In addition to the creation of the transaction, transaction breakdown data populates into the transaction detail object. This object stores data about how much each asset, participant, or coverage contributes to total transaction amounts in terms of premium, tax, and fees. Only assets, participants, and coverages with at least one value greater than zero for premium, tax, or fees are displayed. You must add the transaction detail object to the Related List for Transaction.
    
5.  If saving the payment schedule, the records will be linked to the Policy's **Original Policy Id**.
    
6.  If `taxesAndfees`, `taxAmount`, and/or `feeAmount` nodes are present in the input JSON, the tax and/or fee records are created.
    
7.  Returns a policy ID in the output JSON if the service is not passed an `assetId`.
    
    If the service is passed an `assetId` in the input JSON, it updates the asset specified by the `assetId`.
    
8.  If `calculateCommission=true`: the service calls `InsurancePolicyService.calculateAndSaveCommission`, which prepares the input for the `InsCommissionService.calculate` and `InsCommissionService.saveCommissions` services. After the calculate service processes the input, the save service stores the calculated value in `TotalCommissionAmount`.
    
    -   The service calls `InsurancePolicyService.calculateAndSaveCommission`, which prepares the input for the `InsCommissionService.calculate` and `InsCommissionService.saveCommissions` services.
        
    -   The commission type (for example, Commission or Bonus) is passed to the `InsCommissionService.saveCommissions` service as `commissionType`.
        
    -   The commission status (for example, Waived or Paid) is passed to the `InsCommissionService.saveCommissions` service as `commissionStatus`.
        
    
    After the calculate service processes the input, the save service stores the calculated value in `TotalCommissionAmount`.
    

Note The `endDate` and `effectiveDate` determine the policy duration. The duration of the first policy version can be less than 365 days, or less than 366 days in a leap year. See [Considerations and Limitations for Insurance Policies](https://help.salesforce.com/s/articleView?id=ind.insurance_considerations_and_limitations_for_insurance_policies.htm&language=en_US&type=5).

[](https://help.salesforce.com/s?language=en_US)

Taxes and Fees

Here's how this service works if taxes and fees are used:

-   If the `taxesAndFees` field is specified on a JSON record, a corresponding `AssetPricingAdjustment__c` record persists for each item in the `taxesAndFees` list.
    
-   If the `taxAmount` field is specified on a JSON record, the `TaxAmount__c` field is set to the value of the taxAmount field on the created `AssetItem`.
    
-   If the `feeAmount` field is specified on a JSON record, the `FeeAmount__c` field is set to the value of the `feeAmount` field on the `AssetItem`.
    

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

Optional.

The Id of an existing policy that this service updates based on new or updated information. Used when the service needs to update an existing policy.

 |
| 

`createContactForParticipants`

 | 

Optional.

`true` or `false`

Defaults to `true`.

If `false`, the service doesn't create contact records.

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

If `true`, the service creates a transaction that is used by the revenue schedule services.

The service also populates transaction breakdown data into the transaction detail object. It displays data about how much each asset, participant, and coverage contributes to the total transaction amount in terms of premium, tax, and fees. Only those assets, participants, and coverages are displayed which have at least one non-zero value for premium, tax, and fee amounts. The transaction detail object must be added to the related list of transactions.

 |
| `coolingOffPeriod` | 

Optional

The number of days you can delay the first payment schedule entry. ​ ​

With cooling off period, the first payment schedule date of the policy is calculated as the effective date + the number of days.

For example, there is a monthly payment frequency where the effective date is Jan 5, and the first payment schedule date is Jan 5. If we apply a cooling off period of 14 days, the first payment schedule entry changes from Jan 5 to Jan 19. The remaining monthly payment schedule dates remain unchanged.

Note Cooling off period must be in range of 1 to 28 days from the start date of the policy.





 |
| 

`effectiveDate`

 | 

%“YYYY-MM-DD HH:MM:SS” or %OmniScriptDataElement%

The date that the policy (or policy update) goes into effect.

If there's no `effectiveDate` value in the option map, the service looks for it in the `rootAttributes` map. If the service can't find an `effectiveDate` there, it uses today's date.

If you're using the Insurance Industries Extension package, the timestamp value in the `effectiveDate` option is ignored. Instead, the effective date timestamp value is set to 12:00 a.m. of the selected effective date, and the expiration date value is set to 11:59 p.m. for the selected expiration date. The timestamp is set by using the user's specified timezone.

 |
| 

`generatePolicyNumber`

 | 

**true** or **false**

If `true`, this option uses the `UniqueIdGenerator` to create a unique policy number. This number is stored as `Asset.SerialNumber`.

 |
| 

`includePaymentSchedule`

 | 

Optional.

`True` if the payment schedule will be created for the policy.

Default is `false`.

 |
| 

`includeRevenueSchedule`

 | 

Optional.

`true` or `false`

If `true`, this option calls the InsPolicyRevenueScheduleService: createRevenueSchedule service to create a revenue schedule or InsPolicyRevenueScheduleService: modifyRevenueSchedule if the policy is being updated.

If `false`, the service doesn't create a revenue schedule for this policy.

 |
| 

`initialPaymentRule`

 | 

Optional.

Either **Percentage**, **Months**, or **Days**.

 |
| 

`initialTransactionName`

 | 

Optional.

The transaction name.

The default is to use the same value as `initialPaymentTransactionType`.

 |
| 

`initialPaymentTransactionType`

 | 

Optional.

The transaction type.

Default value is **Premium Charge**.

 |
| 

`initialPaymentValue`

 | 

Required if the `initialPaymentRule` is provided.

The **Percentage** value, or the number of **Months** or **Days**.

 |
| 

`inputKey`

 | 

Required.

A JSON that this service pulls necessary information from in order to create or update a policy.

 |
| 

`isCreatingPolicyTerms`

 | 

`true` or `false`

When set to `true`, the service returns a `policyTermIds` node in the output JSON.

 |
| 

`isFsc`

 | 

Optional.

`True` if the Policy to be created is an InsurancePolicy object.

Default is `false`.

You can specify either`postDataCustomClassName` or `postDataDRBundleName`.

If you do not specify one of these options, the service defaults to `postDataCustomClassName`.

 |
| 

`paymentCalculationMethod`

 | 

Required if `includePaymentSchedule` is `true`.

Overrides the Policy's **Premium Calculation Method** value.

 |
| 

`paymentFrequency`

 | 

Required if `includePaymentSchedule` is `true`.

Overrides the Policy's **PremiumFrequency** value.

 |
| 

`paymentStartDate`

 | 

Optional.

The date of the first payment schedule entry.

Default is the Policy's effective date.

 |
| 

`paymentType`

 | 

Required if `includePaymentSchedule` is `true`.

Overrides the Policy's **Premium Payment Type** value.

 |
| 

`postDataCustomClassName`

 | 

Optional.

You must specify either this option or `postDataDRBundleName`.

Default value is set to **PostInsurancePolicy**.

 |
| 

`postDataDRBundleName`

 | 

Optional.

You must specify either this option or `postDataCustomClassName`.

If you do not specify this option, the default is `postDataCustomClassName`.

 |
| 

`transactionType`

 | 

%OmniScriptDataElement%

Use if `includeRevenueSchedule` is set to true.

If no value is set, defaults to Sold Policy.

 |
| 

[](https://help.salesforce.com/s?language=en_US)`calculateCommission`

 | 

[](https://help.salesforce.com/s?language=en_US)`true` or `false`

[](https://help.salesforce.com/s?language=en_US)When set to `true`, the service calculates commissions for the root items and saves the total amount to `TotalCommissionAmount`.

[](https://help.salesforce.com/s?language=en_US)When set to `false` (the default), the service doesn't calculate commissions.

[](https://help.salesforce.com/s?language=en_US)Note

If you set this option to true, the service requires at least one of the producer or production code values: `producerId` , `productionCodeId`, or `productionCodeName`.







 |
| 

`commissionType`

 | 

Optional

Type of commission (for example, Bonus or Standard).

 |
| 

`commissionStatus`

 | 

Optional

Status of the commission (for example, Pending, Paid, or Waived).

 |
| 

`[](https://help.salesforce.com/s?language=en_US)producerId`

 | 

Optional

[](https://help.salesforce.com/s?language=en_US)The processing producer ID, that is, the producer used to retrieve the commissionScheduleId and calculate the commission amount.

Assigned to assigned to `InsurancePolicy.ProducerId`.

 |
| 

[](https://help.salesforce.com/s?language=en_US)`productionCodeId`

 | 

Optional

[](https://help.salesforce.com/s?language=en_US)The production code ID.

Assigned to `InsurancePolicy.ProductionCodeId__c`.

 |
| 

`[](https://help.salesforce.com/s?language=en_US)productionCodeName`

 | 

Optional

[](https://help.salesforce.com/s?language=en_US)The production code name passed to the InsCommissionService.calculate service.

[](https://help.salesforce.com/s?language=en_US)If you do not input `productionCodeId`, the service uses `productionCodeName` to look up the `productionCodeId`. If you input both values but they don't match, `productionCodeId` takes precedence.

 |
| 

`memberPlanIntegrationProcedure`

 | 

Initiates a custom integration procedure based on the user configuration. When you use this option, it passes all options of the service to the custom integration procedure and all policy Ids as input to integrate with the object, for example the insurance policy object with the member plan.

 |
| 

`ratingDate`

 | 

The rating date that was used to price the input JSON.

Note You can't pass a specific time for ratingField as the field type is Date. So, the rating date timestamp defaults to 12:00 am.





 |
| 

`term`

 | 

The term of the policy the service will create.

InsPolicyService:createUpdatePolicy supports only annual policy terms.

 |
| `useIsPaidFlag` | 

Optional

If true with `includePaymentSchedule` also set true, the service creates contribution records of policy components for each payment schedule entry.

The default value is false.

 |

[](https://help.salesforce.com/s?language=en_US)

## Input JSON

This service looks for the value of the `inputKey`.

For this example, `inputKey` = `newPolicyJSON`.

```
"newPolicyJSON": {
  "accountId": "001f400000OSHq2AAH",
  "term": "Annual",
  "endDate": "2019-05-14T07:00:00.000Z",
  "effectiveDate": "2018-05-15T07:00:00.000Z",
  "productConfigurationDetail": {
    ...
  },
  "insuredItems": {
    ...
  },
  "additionalFields": {
    "SerialNumber": "AUTO-123",
    "Status": "InForce",
    "vlocityins2__Type__c": "AUTO",
    "vlocityins2__PaymentMethodId__c": "a2Rf40000002NrgEAE"
  },
}
```

The JSON inside the `inputKey` includes several key/value pairs the service needs to create or update a policy. It also includes the product JSON, with pricing for the insured items and the total policy.

| 
Key

 | 

Value

 |
| --- | --- |
| 

`accountId`

 | 

The generated account Id for the asset.

 |
| 

`additionalFields`

 | 

Optional.

Key/value pairs including any policy (asset) fields that are not part of the service.

 |
| 

`endDate`

 | 

Optional.

The date that the policy expires.

 |
| 

`effectiveDate`

 | 

The date that the policy goes into effect.

If there's no `effectiveDate` value in the option map, the service looks for it in the `rootAttributes` map. If the service can't find an `effectiveDate` there, it uses today's date.

 |
| 

`insuredItems`

 | 

The key/value pairs of the insured items the service uses to create the policy.

 |
| 

`modificationDate`

 | 

The date the policy was modified

 |
| 

`productConfigurationDetail`

 | 

An array of records that follow the product JSON structure model.

 |
| 

`term`

 | 

The term of the policy the service will create.

 |

The `insuredItems` records for this example includes the insured items and the values the user selected for each one.

For this example, `inputKey` = `quotepolicyJSON`.

```
"quotepolicyJson": {
  "productConfigurationDetail": {
    ...
  }
  "insuredItems": {
    "DRIVER": [{
        "GENDER": "Female",
        "FN": "Joan",
        "AGE": 20,
        "LN": "Smith",
        "instanceKey": "Joan Smith",
        "isPrimary": false
        "isParent": false
      },
      {
        "GENDER": "Male",
        "FN": "John",
        "AGE": 30,
        "LN": "Smith",
        "instanceKey": "John Smith",
        "isPrimary": false
        "isParent": false
      },
      {
        "GENDER": "Male",
        "FN": "Robert",
        "AGE": 30,
        "LN": "Henderson",
        "instanceKey": "Robert Henderson",
        "isPrimary": false
        "isParent": false
      },
      {
        "GENDER": "Female",
        "FN": "Kinsey",
        "AGE": 20,
        "LN": "Schell",
        "instanceKey": "Kinsey Schell",
        "isPrimary": false
        "isParent": false
      }
    ],
    "AUTO": [{
        "autoLicNum": "Lexus",
        "autoModel": "LX250",
        "autoYear": 2015,
        "instanceKey": "2015 Lexus LX250",
        "BodyClass": "Sedan/Saloon",
        "VehicleType": "PASSENGER CAR",
        "isPrimary": true
        "isParent": true
      },
      {
        "autoLicNum": "Honda",
        "autoModel": "Odyssey",
        "autoYear": 2006,
        "instanceKey": "2006 Honda Odyssey",
        "BodyClass": "Minivan",
        "VehicleType": "MULTIPURPOSE PASSENGER VEHICLE (MPV)",
        "isPrimary": true
        "isParent": true                                
      }
    ]
  },
  "accountId": "0011I00000QknfjQAB",
  "opportunityId": "0061I00000AV8gBQAT"
},
"quoteId": "0Q01I000000206USAQ",
"error": "OK"
```

[](https://help.salesforce.com/s?language=en_US)

## Output JSON

The service returns the policy ID of the newly created policy.

```
{
    "policyId": "02if4000001uCZXAA2",
    "error": "OK"
}
```

[](https://help.salesforce.com/s?language=en_US)If the `isCreatingPolicyTerms` remote option is set to `true`, a `policyTermIds` node is included. Here's an example of a `policyTermIds` node:

[](https://help.salesforce.com/s?language=en_US)`{      "policyId": "02i6g000000h110AAA",    "policyTermIds": [     "a5X6g000001LeUUEA0",     "a5X6g000001LeUVEA0",     "a5X6g000001LeUWEA0",     "a5X6g000001LeUXEA0",     "a5X6g000001LeUYEA0",     "a5X6g000001LeUZEA0",     "a5X6g000001LeUaEAK",     "a5X6g000001LeUbEAK",     "a5X6g000001LeUcEAK",     "a5X6g000001LeUdEAK",     "a5X6g000001LeUeEAK",     "a5X6g000001LeUfEAK"   ] }`

[](https://help.salesforce.com/s?language=en_US)

## Examples

The service is typically used in the OmniScript Quote-to-Policy pattern.

Did this article solve your issue?

Let us know so we can improve!

YesNo