---
title: "InsPolicyService:prepareToCancelPolicy"
source: "https://help.salesforce.com/s/articleView?id=ind.insurance_inspolicyservice__preparetocancelpolicy.htm&language=en_US&type=5"
scraped: "2026-04-14"
filter: "ind.insurance_"
---# InsPolicyService:prepareToCancelPolicy

InsPolicyService:prepareToCancelPolicy[](https://help.salesforce.com/s?language=en_US)

You are here:

1.  [Salesforce Help](/s/?language=en_US)
2.  [Docs](/s/products?language=en_US)
3.  [Digital Insurance](https://help.salesforce.com/s/articleView?id=ind.insurance_admin_standard.htm&language=en_US&type=5)

# InsPolicyService:prepareToCancelPolicy

Use this service to calculate the premium price difference before canceling a policy. The service prorates the premium, fee, and tax amounts, and calculates the premium, fee, and tax refund.

This service needs to be invoked before the `InsPolicyService:cancelPolicy` service.

[](https://help.salesforce.com/s?language=en_US)

This service works with the Salesforce Financial Services Cloud.

[](https://help.salesforce.com/s?language=en_US)

[](https://help.salesforce.com/s?language=en_US)Class: `InsPolicyService`

Method: `prepareToCancelPolicy`

[](https://help.salesforce.com/s?language=en_US)

## How It Works

1.  Takes the `assetId` or `policyId` and finds the policy to be canceled.
    
2.  Uses the appropriate calculation process based on the `useIsPaidFlag` value.
    
    With `useIsPaidFlag` set to false (deselected), the service prorates the policy's Total Premium For Term, Total Fee For Term, and Total Tax For Term, and calculates refunded amounts based on the Cancellation Date and Policy Paid To Date. If Policy Paid To Date is Null, the service considers the policy paid in full and uses Expiration Date.
    
    With `useIsPaidFlag` set to `true` (selected), the service:
    
    1.  Uses payment schedules to calculate the total amount already paid for the policy. The total amount paid for the policy equals the sum of amounts in payment schedules with **Is Paid** set to true (selected). This amount is used in refund calculations.
        
    2.  Prorates the policy's Total Premium For Term, Total Fee For Term, and Total Tax For Term, and calculates refund amounts based on the Cancellation Date and the total amount already paid for the policy.
        
3.  The service takes into consideration if the fees or taxes are refundable or not.
    
4.  Returns the price difference between the original total premium for the policy and the canceled policy in the output JSON.
    
    [](https://help.salesforce.com/s?language=en_US)
    -   The refund amounts are from the policy holder's perspective. A positive amount represents a refund to the policyholder. A negative amount indicates an unpaid amount by the policyholder.
        
5.  If taxes and fees are included in this policy, the `Total Tax For Term`, `Total Fee For Term`, `refundedTax`, and/or `refundedFee` are also included in the output JSON.
    
    If the policy the service is canceling does not include taxes or fees, these fields are omitted from the output JSON.
    

[](https://help.salesforce.com/s?language=en_US)

## Surcharges (Taxes and Fees)

This service (along with the `[InsPolicyService:cancelPolicy](https://help.salesforce.com/s/articleView?id=ind.insurance_inspolicyservice__cancelpolicy.htm&language=en_US&type=5 "Use this service to cancel an existing insurance policy.")` service) facilitates prorations and refunds for taxes and fees when a policy is canceled. Here's how that works:

[](https://help.salesforce.com/s?language=en_US)

-   The `priceDiff` is essentially the refund amount, and uses the formula = (old `GrossWrittenPremium` \- updated `GrossWrittenPremium`) + `refundedTax` + `refundedFee`.
    
-   The updated `GrossWrittenPremium` is the `PremiumAmount` prorated over the policy's effective date and cancellation date.
    
-   The new total amount is equal to the target policy’s `PremiumAmount` plus the `StandardTaxAmount` plus the `StandardFeeAmount`, all prorated to the cancellation date.
    
-   If the target policy has a `StandardTaxAmount`, that value is prorated over the cancellation date and returned via the `TermTaxAmount` field in the output.
    
-   If the target policy has a `StandardFeeAmount`, that value is prorated over the cancellation date and returned via the `TermFeeAmount` field in the output.
    
-   If the target policy has refundable `InsurancePolicySurcharge` or `AssetPricingAdjustment__c` records, the prorated refund amounts are returned via the `refundedTax` and `refundedFee` fields in the output. An `InsurancePolicySurcharge` or `AssetPricingAdjustment__c` is refundable if the associated `PriceListEntry__c` is refundable. The prorated refund amounts are calculated over the cancellation date and the original expiration date.
    

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

`%theIdYouAreLookingFor%`

The Id of the insurance policy to be canceled.

 |
| 

`effectiveDate`

 | 

Required.

`“YYYY-MM-DD HH:MM:SS”` or `%OmniScriptDataElement%`

The date the policy will be canceled.

 |
| 

`getDataDRBundleName`

 | 

Optional (FSC only).

[](https://help.salesforce.com/s?language=en_US)The name of the Omnistudio Data Mapper this service uses to retrieve policy (asset) information.

[](https://help.salesforce.com/s?language=en_US)If you're using Salesforce FSC, you must specify either this option or `getDataCustomClassName`.

 |
| 

`getDataCustomClassName`

 | 

Optional (FSC only).

[](https://help.salesforce.com/s?language=en_US)The name of the custom class this service uses to retrieve policy (asset) information.

[](https://help.salesforce.com/s?language=en_US)If you're using Salesforce FSC, you must specify either this option or `getDataDRBundleName`.

Default value is set to `GetInsurancePolicy`.

 |
| `useIsPaidFlag` | 

Optional.

true or false

If true, the new pro-ration logic is used (which considers payment schedules).

If false, the existing pro-ration logic is used (which uses cancellation date and paidToDate).

Default value is set to false.

 |

[](https://help.salesforce.com/s?language=en_US)

## Input JSON

This service takes an input JSON that includes the `effectiveDate` (date to be canceled).

[](https://help.salesforce.com/s?language=en_US)`{     "Id": "02i6g000002f07VAAQ",     "effectiveDate": "08/12/2019" }`

[](https://help.salesforce.com/s?language=en_US)

## Output JSON

The service returns the price difference calculated for the policy with the new cancellation date.

[](https://help.salesforce.com/s?language=en_US)`{   "Id": "02i6g000002f07VAAQ",   "output": {     "refundedFee": -3.68,     "totalFeeForTerm": 14.06,     "refundedTax": -37.93,     "totalTaxForTerm": 144.84,     "aggregateTotalPremiumForTerms": 4002.28,     "priceDiff": -420.97,     "totalPremiumForTerm": 1448.44,     "errorCode": "INVOKE-200",     "error": "OK"   } }`

[](https://help.salesforce.com/s?language=en_US)

## Output Keys and Values

| 
Output

 | 

Description

 |
| --- | --- |
| 

`Id`

 | 

The Id of the Policy (Asset) or InsurancePolicy that was updated.

 |
| 

`output`

 | 

-   `totalPremiumForTerm`: the prorated Total Premium For Term
    
-   `totalFeeForTerm`: the prorated Total Fee For Term
    
-   `totalTaxForTerm`: the prorated Total Tax For Term
    
-   `aggregateTotalPremiumForTerms`: the sum of the Total Premium For Term of all Policy versions and the prorated Total Premium For Term of the current version being canceled
    
-   `refundedFee`: the amount of fees to be refunded
    
-   `refundedTax`: the amount of taxes to be refunded
    
-   `priceDiff`: the total amount of premiums, fees and taxes for refund
    

 |

Did this article solve your issue?

Let us know so we can improve!

YesNo