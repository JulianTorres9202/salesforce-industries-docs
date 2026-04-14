---
title: "InsPolicyService:createOutOfSequencePolicyVersion"
source: "https://help.salesforce.com/s/articleView?id=ind.insurance_inspolicyservice__createoutofsequencepolicyversion.htm&language=en_US&type=5"
scraped: "2026-04-14"
filter: "ind.insurance_"
---# InsPolicyService:createOutOfSequencePolicyVersion

InsPolicyService:createOutOfSequencePolicyVersion[](https://help.salesforce.com/s?language=en_US)

You are here:

1.  [Salesforce Help](/s/?language=en_US)
2.  [Docs](/s/products?language=en_US)
3.  [Digital Insurance](https://help.salesforce.com/s/articleView?id=ind.insurance_admin_standard.htm&language=en_US&type=5)

# InsPolicyService:createOutOfSequencePolicyVersion

Use this service to initiate an out-of-sequence endorsement for a given policy.

Class: `InsPolicyService`

Method: `createOutOfSequencePolicyVersion`

The service creates these transactions for an out-of-sequence endorsement:

-   Out-of-Sequence Changed/Endorsed: Total change in premium for the policy year as a result of endorsement. In case multi-term policies are impacted, the transaction is created for each term.
    
-   Out-of-Sequence Endorsement: The premium adjustment for the payment schedule when the endorsement is performed. It is only for the current term. The payment schedule entry date is the current date or date of operation when out-of-sequence is effective between a past date and the current date. For a future date, the payment schedule entry date is the effective date of out-of-sequence endorsement.
    
    Important The Reference Policy Number must be populated on all policy versions across terms.
    

## How It Works

1.  The service takes the `policyId` of the current policy, the effective date for the out-of-sequence endorsement, and the JSON specified by the `inputKey`.
    
2.  If `createTransaction` is `true`, the service creates an out-of-sequence transaction of the type `Out-of-Sequence Changed/Endorsed` and the transaction details.
    
3.  If `includePaymentSchedule` is `true`, the service generates or updates payment schedules and payment schedule entry details. The calculation is performed based on values selected for corresponding `paymentCalculationMethod` and `paymentFrequency` options. The payment schedule follows the existing payment schedule rules:
    
    -   Only future-dated unpaid payment schedules are updated.
        
    -   Past payment schedules, paid or unpaid, are never updated.
        
    -   Any adjustments for the past-dated payment and paid payment schedule are included in the Out-of-Sequence Endorsement transaction.
        
4.  The service updates the value of the `IsPolicyEditLocked` field to `true` on the related insurance policy versions. All the policy versions are locked until the out-of-sequence endorsement transaction is complete.
    

Note

The service additionally supports out-of-sequence endorsements where the original policy version has a duration of less than 365 days, or less than 366 days in a leap year. See [Considerations and Limitations for Insurance Policies](https://help.salesforce.com/s/articleView?id=ind.insurance_considerations_and_limitations_for_insurance_policies.htm&language=en_US&type=5).

## Support for Custom Fields

-   Store the custom fields of the Insurance Policy object in the OutOfSequenceEndorsementCustomFields field set.
    
-   Populate the custom fields as key/value pairs in the `additionalFields` section. See [Input JSON](https://help.salesforce.com/s/articleView?id=ind.insurance_inspolicyservice__createoutofsequencepolicyversion.htm&language=en_US&type=5#insurance_inspolicyservice__createoutofsequencepolicyversion__json).
    
-   Use this OutOfSequenceEndorsementCustomFields field set to copy custom data from the canceled to new policy versions during an out-of-sequence endorsement.
    

[](https://help.salesforce.com/s?language=en_US)

## Remote Options

| 
Option

 | 

Description

 |
| --- | --- |
| `policyId` | 

Required.

The ID of an existing policy that the service updates based on new or updated information.

 |
| `createContactForParticipants` | 

Optional.

[](https://help.salesforce.com/s?language=en_US)`true` or `false`

[](https://help.salesforce.com/s?language=en_US)Defaults to `true`.

[](https://help.salesforce.com/s?language=en_US)If `false`, the service doesn't create contact records.

 |
| `createInsuredItemsRelationships` | 

Optional.

`true` or `false`

If this option is `true`, specify a list of `instanceKey` > `parentInstanceKey` relationships between insured items.

This option supports parent > child and parent > child > grandchild insured item relationships.

 |
| `createTransaction` | 

Optional.

`true` or `false`

Defaults to `false`.

If `true`, the service creates a transaction.

 |
| `effectiveDate` | 

Required.

`"YYYY-MM-DD HH:MM:SS"` or `%OmniScriptDataElement%`

The date from when out-of-sequence endorsement changes apply.

 |
| `includePaymentSchedule` | 

Optional.

`true` if the payment schedule is created or updated for the policy.

Default is `false`.

 |
| `inputKey` | 

Required.

`%theJSONyouneed%`

A JSON with necessary inputs to create or update a policy. You can specify either of these values:

-   `postDataCustomClassName`
    
-   `postDataDRBundleName`
    
    If you don't specify one of these options, the value defaults to `postDataCustomClassName`.

 |
| `paymentCalculationMethod` | Required if `includePaymentSchedule` is true. This option overrides the policy's premium calculation method value. |
| `paymentFrequency` | Required if `includePaymentSchedule` is true. This option overrides the policy's premium frequency value. |
| `paymentType` | Required if `includePaymentSchedule` is true. This option overrides the policy's premium payment type value. |
| `postDataCustomClassName` | 

Optional.

The name of the custom class the service uses to save the new policy version.

You must specify either this option or `postDataDRBundleName`.

The default value is **PostInsurancePolicy**.

 |
| `postDataDRBundleName` | 

Optional.

The name of the Omnistudio Data Mapper the service uses to save the new policy version.

You must specify either this option or `postDataCustomClassName`.

-   If you don't specify either, the service uses the default value for `postDataCustomClassName`.
    

 |
| `transactionType` | 

Optional.

If no value is provided for `transactionType`, it defaults to `Out-of-Sequence Changed/Endorsed`.

 |
| `term` | 

The term of the policy that the service creates.

InsPolicyService:createOutOfSequencePolicyVersion supports only annual policy terms.

 |

[](https://help.salesforce.com/s?language=en_US)

## Input JSON

The service looks for the `inputKey` specified within the product JSON. Here's the sample input JSON:

```json
"newPolicyJSON": {
  "accountId": "001f400000RrQSrAAN",
  "term": "Annual",
  "productConfigurationDetail": {
    ...
  },
  "insuredItems": {
    ...
  },
  "additionalFields": {
    "vlocity_ins__Type__c": "AUTO",
  },
}
```

Here's the sample options JSON:

```json
{
   
    "effectiveDate": "2023-03-01",
    "inputKey": "quotepolicyJson",
    "policyId": "0YT3t000000uUz6GAE",
    "includePaymentSchedule": true,
    "createTransaction": true,
    "paymentFrequency": "Monthly",
    "paymentCalculationMethod": "Modal"
  }
```

## Output JSON

Here's the sample output JSON when the service initiates an out-of-sequence endorsement and successfully generates the job ID:

```json
 {
"jobId": "7073t0000BNGivxAQD",
"errorCode": "INVOKE-200",
 "error": "OK"
}
```

Here's the sample output JSON when the service returns an error:

```json
{
"errorCode": "ERROR-CODE",
"error": "error message"
}
```

Did this article solve your issue?

Let us know so we can improve!

YesNo