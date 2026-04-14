---
title: "InsPolicyService:cancelPolicy"
source: "https://help.salesforce.com/s/articleView?id=ind.insurance_inspolicyservice__cancelpolicy.htm&language=en_US&type=5"
scraped: "2026-04-14"
filter: "ind.insurance_"
---# InsPolicyService:cancelPolicy

InsPolicyService:cancelPolicy[](https://help.salesforce.com/s?language=en_US)

You are here:

1.  [Salesforce Help](/s/?language=en_US)
2.  [Docs](/s/products?language=en_US)
3.  [Digital Insurance](https://help.salesforce.com/s/articleView?id=ind.insurance_admin_standard.htm&language=en_US&type=5)

# InsPolicyService:cancelPolicy

Use this service to cancel an existing insurance policy.

[](https://help.salesforce.com/s?language=en_US)This service works with the `InsPolicyService:prepareToCancelPolicy` service and with the `InsPolicyRevenueScheduleService:cancelRevenueSchedule` service to complete all the changes necessary to cancel a policy, provide a refund amount, and end the revenue schedule (if needed).

[](https://help.salesforce.com/s?language=en_US)

[](https://help.salesforce.com/s?language=en_US)Class: `InsPolicyService`

Method: `cancelPolicy`

[](https://help.salesforce.com/s?language=en_US)

This service works with the Salesforce Financial Services Cloud.

[](https://help.salesforce.com/s?language=en_US)

## How It Works

1.  Takes the `assetId` or `policyId` of the policy to be canceled and the `effectiveDate` on which the cancellation goes into effect.
    
    Note The effective cancellation date can't be greater than today.
    
2.  Updates the policy status to `Canceled`, the original Expiration Date to the current value of the Expiration Date, and Expiration Date to a day before the Cancellation Date (with Timestamp of 11:59 PM).
    
3.  Changes the expiration date to the `effectiveDate` passed to the service with a Timestamp of 11:59 PM.
    
4.  Uses the appropriate calculation process based on the `useIsPaidFlag` value.
    
    With `useIsPaidFlag` set to false (deselected), the service prorates the policy's Total Premium For Term, Total Fee For Term, and Total Tax For Term, and calculates refunded amounts based on the Cancellation Date and Policy Paid To Date. If Policy Paid To Date is Null, the service considers the policy paid in full and uses Expiration Date.
    
    With `useIsPaidFlag` set to `true` (selected), the service:
    
    1.  Uses payment schedule to calculate the total amount already paid for the policy. The total amount paid for the policy equals the sum of amounts in payment schedules with **Is Paid** set to true (selected). This amount is used in refund calculations.
        
    2.  Prorates the policy's Total Premium For Term, Total Fee For Term, and Total Tax For Term, and calculates refund amounts based on the Cancellation Date and the total amount already paid for the policy.
        
    3.  Adjusts payment schedules based on either the current date or the cancellation date, whichever is later. If payment schedules on or after this date have **Is Paid** set to false (deselected), the service deletes them.
        
    4.  Updates the status of all unpaid payment schedules (which are in past from `cancellationDate`) to `Invalid`. The unpaid amount is added to the new payment schedule.
        
    5.  Creates a new payment schedule for the current date with an amount equal to the refund amount already calculated and marks the status as `Valid`. If `createTransaction` is true, the service creates a cancellation transaction.
        
    6.  Updates all the future policy versions with cancellation information:
        
        -   Status: Canceled
            
        -   Cancellation Date: The `effectiveDate` passed to the service
            
        -   Term Premium, Term Tax, and Term Fee: 0
            
        -   Expiration Date: Day before the `effectiveDate` passed to the service with a Timestamp of 11:59 PM
            
5.  Commits the prorated TotalPremiumForTerm to the database.
    
6.  If createTransaction=true and the Id passed is assetId, creates AssetTransaction\_c (Amount\_c=refund, postDate\_c and transactionDate\_c=effectiveDate, type=transactionType (defaults to Canceled). If createTransaction=true and the Id passed is policyId, the service creates InsurancePolicyTransaction\_c or InsurancePolicyTransaction (Amount\_c=refund, postDate\_c and transactionDate\_c=effectiveDate, type=transactionType (defaults to Canceled).
    
    The service also populates transaction breakdown data into the transaction detail object. It displays data about how much each asset, participant, and coverage contributes to the total transaction amount in terms of premium, tax, and fees. Only those assets, participants, and coverages are displayed which have at least one non-zero value for premium, tax, and fees.
7.  Calls [InsPolicyRevenueScheduleService:cancel](https://help.salesforce.com/s/articleView?id=ind.insurance_inspolicyrevenuescheduleservice__cancelrevenueschedule.htm&language=en_US&type=5 "When a policy is canceled, this service adjusts the revenue schedule to calculate revenue until the cancellation date.") using the `assetId` and the newly created `transactionId`.
    
8.  The InsPolicyRevenueScheduleService: cancel service calculates the end of the revenue schedule and posts the results in the revenue schedule section of the policy. The refund amounts are from the insurance company's perspective. A negative amount results in a refund to the policyholder, and a positive amount represents an unpaid amount by the policyholder.
    

Note

The service additionally supports cancellation of policies where the original policy version has a duration of less than 365 days, or less than 366 days in a leap year. See [Considerations and Limitations for Insurance Policies](https://help.salesforce.com/s/articleView?id=ind.insurance_considerations_and_limitations_for_insurance_policies.htm&language=en_US&type=5).

[](https://help.salesforce.com/s?language=en_US)

## Surcharges (Taxes and Fees)

This service (along with the `[prepareToCancel](https://help.salesforce.com/s/articleView?id=ind.insurance_inspolicyservice__preparetocancelpolicy.htm&language=en_US&type=5 "Use this service to calculate the premium price difference before canceling a policy. The service prorates the premium, fee, and tax amounts, and calculates the premium, fee, and tax refund.")` service) facilitates prorations and refunds for taxes and fees when a policy is cancelled. Here's how that works:

[](https://help.salesforce.com/s?language=en_US)

-   If the target policy has a `TotalTaxAmount__c`, that value is prorated over the cancellation date and is set on the `TotalTaxForTerm__c` field.
    
-   If the target policy has a `TotalFeeAmount__c`, that value is prorated over the cancellation date and set on the `TotalFeeForTerm__c` field.
    
-   If the `createTransaction` option (see below) is set to true and the target policy has refundable `AssetPricingAdjustment__c` records, then the prorated refund amounts are set on the transaction’s `TaxAmount__c` and `FeeAmount__c` fields.
    

If you're using the Insurance Policy object model (instead of the Asset object model), the field names are different:

-   `TotalTaxAmount__c` = `StandardTaxAmount`
    
-   `TotalTaxForTerm__c` = `TermTaxAmount`
    
-   `TotalFeeAmount__c` = `StandardFeeAmount`
    
-   `TotalFeeForTerm__c` = `TermFeeAmount`
    
-   `AssetPricingAdjustment__c` = `InsurancePolicySurcharge`
    
-   `TaxAmount__c` = `TransactionTaxAmount`
    
-   `FeeAmount__c` = `TransactionFeeAmount`
    

[](https://help.salesforce.com/s?language=en_US)Tip

Want to learn about transitioning from the Asset object model to the Insurance Policy object model? Read [Harmonize Insurance Policies](https://help.salesforce.com/s/articleView?id=ind.insurance_harmonize_insurance_policies.htm&language=en_US&type=5 "To benefit from new and enhanced Insurance Policy features in the future, harmonize existing data and move to the Salesforce data model.").

[](https://help.salesforce.com/s?language=en_US)

## Remote Options

| 
Option

 | 

Description

 |
| --- | --- |
| 

`additionalFees`

 | 

Optional.

Add one or more fees to an insurance policy cancellation. The service reduces the cancellation refund amount by the sum of the fees, adjusts the payment schedule entry, and reflects the fees in the cancellation transaction breakdown.

Format each fee as `"<_fee type_>": <_amount_>`.

For example, to add a $10 administrative fee and a $20 cancellation fee, enter:

```
  "additionalFees": {
    "Cancellation Fee": 20,
    "Admin Fee": 10
  }
```

If a cancellation refund is $120 gross of fees, these additionalFees reduce it by $30. This results in a net cancellation refund amount of $90.

 |
| 

`assetId` or `policyId`

 | 

Required.

`%theIdYouAreLookingFor%`

The Id of the Policy (Asset) or InsurancePolicy being canceled.

 |
| 

`cancelRevenueScheduleCustomeClassName`

 | 

Optional (FSC only).

The default value is set to `CancelRevenueSchedule`.

 |
| 

`createTransaction`

 | 

Optional.

`true` or `false`

Defaults to `false`.

If `true`, the service creates a transaction that will be used by the revenue schedule service.

 |
| 

`effectiveDate`

 | 

Required.

`“YYYY-MM-DD HH:MM:SS”` or `%OmniScriptDataElement%`

The date the policy will be canceled.

If you're using the Insurance Industries Extension package, the timestamp value in the effective date option is ignored. Instead, the cancellation effective date timestamp value is set to 12:00 a.m. of the selected effective date. The expiration date value is set to 11:59 p.m. of the day before the selected effective date. The timestamp is set by using the user's specified timezone.

 |
| 

`getDataCustomClassName`

 | 

Optional (FSC only).

[](https://help.salesforce.com/s?language=en_US)The name of the custom class this service uses to retrieve policy (asset) information.

[](https://help.salesforce.com/s?language=en_US)If you're using Salesforce FSC, you must specify either this option or `getDataDRBundleName`.

The default value is set to `GetInsurancePolicy`.

 |
| 

`getDataDRBundleName`

 | 

Optional (FSC only).

[](https://help.salesforce.com/s?language=en_US)The name of the Omnistudio Data Mapper this service uses to retrieve policy (asset) information.

[](https://help.salesforce.com/s?language=en_US)If you're using Salesforce FSC, you must specify either this option or `getDataCustomClassName`.

[](https://help.salesforce.com/s?language=en_US)

-   If you specify both, the service uses the `getDataDRBundleName` value.
    
-   If you don't specify either, the service uses the default value for `getDataCustomClassName` (**GetInsurancePolicy**).
    

 |
| 

`includeRevenueSchedule`

 | 

Optional.

`true` or `false`

If `true`, this option tells the service to call the `InsPolicyRevenueScheduleService: cancel` service to cancel the revenue schedule.

If `false`, the service doesn't do anything about revenue scheduling.

Default is `false`.

 |
| 

`updateDataCustomClassName`

 | 

Optional (FSC only).

If you're using Salesforce FSC, you must specify either this option or `updateDataDRBundleName`.

The default value is set to `PostInsurancePolicy`.

 |
| 

`updateDataDRBundleName`

 | 

Optional (FSC only).

If you're using Salesforce FSC, you must specify either this option or `updateDataCustomClassName`.

[](https://help.salesforce.com/s?language=en_US)

-   If you specify both, the service uses the `updateDataDRBundleName` value.
    
-   If you don't specify either, the service uses the default value for `updateDataCustomClassName` (**PostInsurancePolicy**).
    

 |
| 

`useIsPaidFlag`

 | 

Optional.

true or false

If true, the new proration logic is used (which considers payment schedules).

If false, the existing pro-ration logic is used (which uses cancellation date and paidToDate).

Default value is set to false.

 |

[](https://help.salesforce.com/s?language=en_US)

## Input JSON

This service doesn't take an input JSON.

[](https://help.salesforce.com/s?language=en_US)

## Output JSON

If you're using the Asset object model, this service returns a JSON `output` node. Here's an example:

[](https://help.salesforce.com/s?language=en_US)`{   "output": {     "records": [       {         "instest10__TotalAmount__c": 420.97,         "instest10__TaxAmount__c": 37.93,         "instest10__FeeAmount__c": 3.68,         "instest10__Amount__c": 379.36,         "Id": "a416g0000002CZpAAM"       }     ],     "totalSize": 1   } }`

If you're using the Insurance Policy object model, this service returns a JSON `results` node. Here's an example:

```json
{
    "result": {
        "type": "Cancelled",
        "transactionNumber": null,
        "transactionDate": 
        "totalAmount": null,
        "taxAmount": null,
        "postDate": "2021-09-01T07:00:00.000Z",
        "name": "Cancelled"
        "Id": null,
        "feeAmount": null,
        "amount": -133.4,
        "additionalInfo": null
    },
    "error": "OK"
}
```

Did this article solve your issue?

Let us know so we can improve!

YesNo