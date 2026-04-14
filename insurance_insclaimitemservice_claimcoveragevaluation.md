---
title: "InsClaimItemService:claimCoverageValuation"
source: "https://help.salesforce.com/s/articleView?id=ind.insurance_insclaimitemservice_claimcoveragevaluation.htm&language=en_US&type=5"
scraped: "2026-04-14"
filter: "ind.insurance_"
---# InsClaimItemService:claimCoverageValuation

InsClaimItemService:claimCoverageValuation[](https://help.salesforce.com/s?language=en_US)

You are here:

1.  [Salesforce Help](/s/?language=en_US)
2.  [Docs](/s/products?language=en_US)
3.  [Digital Insurance](https://help.salesforce.com/s/articleView?id=ind.insurance_admin_standard.htm&language=en_US&type=5)

# InsClaimItemService:claimCoverageValuation

Use this service to verify that users have the authority to pay or approve amounts in different types of financial activities.

Financial authorization workflows call this service when:

-   Users attempt to issue a claim payment.
    
-   Supervisors set maximum approval amounts for their team members.
    
-   Approvers attempt to update a claim's financial authority status to Authority Approved.
    

Class: `InsClaimItemService`

Method: `claimCoverageValuation`

Works with: Salesforce data model

## How It Works

The claim coverage valuation service uses input JSON and a `userId` to determine whether a claim financial amount exceeds a user's maximum approval amount. Configure the claim payment process to check a user's financial authority by running this service. When claim team leaders approve a financial authorization request, the approve action runs this service to check the approver's financial authority.

The service:

1.  Accepts an array of `objectIds` as input, either Claim Coverage Payment Detail IDs (`ClaimCoveragePaymentDetailId` values) or Claim Coverage IDs (`ClaimCoverageId` values).
    
2.  Validates the `objectIds`.
    
    -   The service can't process a mix of Claim Coverage Payment Detail and Claim Coverage records.
        
    -   Input for a `ClaimCoverageId` must also include a `claimFinancialType` value of Loss or Expense.
        
3.  Retrieves Claim Coverage Payment Detail or Claim Coverage record details, and the user ID of the user who's logged in.
    
4.  Retrieves the active User Financial Authority record for the user who's logged in.
    
5.  Determines the claim coverage valuation amount.
    
    The service calculates a new claim coverage valuation.
    
    If `objectIds` are Claim Coverage Payment Detail IDs, the service adds the sum of the input details to the amount that's already been paid for the claim coverage. Optionally, the service also adds pending payment amounts.
    
6.  Determines if the new claim coverage valuation amount exceeds the user's maximum approval amount.
    
    If the new valuation amount exceeds the user's maximum approval amount, the service evaluates the user's financial authority as false.
    
    The service returns a detailed accounting of which Claim Coverage Payment Detail IDs or Claim Coverage IDs fail the authority evaluation. If any detail fails the evaluation, the service returns a false value for the entire transaction. For transactions that fail the evaluation, the service updates statuses to values specified for remote options. The service updates:
    
    -   **Status** values for all the related Claim Coverage IDs or Claim Coverage Payment Detail IDs.
        
    -   **Financial Authority Status** values of all the related Claim IDs.
        

Example: Judith is a claims adjuster who can pay or approve up to $10,000 for claim coverage losses. She wants to issue a $3,000 payment for Dwelling coverage on a homeowner's policy.

-   If no other payments have been issued or are pending for the Dwelling coverage, Judith can issue the $3,000 payment without requesting approval.
    
-   If $8,000 has already been paid for the Dwelling coverage, another $3,000 payment requires approval because a total coverage payment of $11,000 brings Judith over her $10,000 financial authority limit.
    
-   If in addition to the $6,000 already paid for Dwelling coverage, a $2,000 Dwelling coverage payment in an unrelated transaction is yet to be paid, a $3,000 payment increases the total of Paid and Pending amounts to $11,000. Since $11,000 is greater than Judith's financial authority limit, her payment requires approval by default. If the service is configured with `includePendingPayments` set to `false`, Judith can issue the $3,000 payment because the total coverage payment is just $9,000 when the service excludes the $2,000 pending payment in the unrelated transaction. And $9,000 is below Judith's $10,000 limit.
    

## Remote Options

| 
Option

 | 

Description

 |
| --- | --- |
| 

`objectIds`

 | 

Required.

An array of either Claim Coverage Payment Detail IDs (`ClaimCoveragePaymentDetailId` values) or Claim Coverage IDs (`ClaimCoverageId` values).

 |
| 

`claimFinancialType`

 | 

Required if objectIds are claimCoverageId values.

The type of financial transaction in the authorization request. Possible values are: Loss, Expense.

 |
| 

`includePendingPayments`

 | 

Optional.

For Claim Coverage Payment Detail ID inputs, `true` (the default value) to include pending payments in the calculation of payments already made for a coverage, or `false` to exclude them.

 |
| 

`requestedCoverageAmount`

 | 

Required if `objectIds` are `claimCoverageId` values.

 |
| 

`AuthorityFailClaimStatus`,

`AuthorityFailClaimCoverageStatus`,

`AuthorityFailClaimCoveragePaymentDetailStatus`

 | 

Optional.

If the user doesn't have the authority to pay or approve the requested amount (`userFinancialAuthority` = `false`), set the Status of the claim, claim coverage, or claim coverage payment detail to the value specified for each option.

Default: `Pending Authority`

 |
| 

`ClaimCovPaymentDetailStatusBypassFinancialAuthorityValuation`

 | 

Optional.

Do not evaluate the user financial authority of the claim coverage payment detail record if its Status matches this value.

Default: `Authority Approved`

If you omit this option, the service evaluates all claim coverage payment details regardless of their Status value.

 |

## Input JSON

This input JSON passes payment detail IDs. It's used to verify a user's authority to pay amounts in payment details.

```json
{
  "objectIds": [
    "claimCovergePaymentDetailId4",
    "claimCovergePaymentDetailId2"
  ]
}
```

This input JSON passes claim coverage IDs. It's used to request pre-approval of $10,000 in payments for claim coverage losses.

```json
{
 "objectIds": "claimCoverageId_ABC",
 "claimFinanicalType": "Loss",
 "requestedCoverageAmount": "10000"
}
```

## Output JSON

Output JSON shows:

| 
Key

 | 

Value

 |
| --- | --- |
| 

`passedItemIds` and `failedItemIds`

 | 

Payment details that fall within the user's financial authority, and those that don't.

 |
| 

`passedClaimCoverageIds` and `failedClaimCoverageIds`

 | 

Claim coverages that fall within the user's financial authority, and those that don't.

 |
| 

`userFinancialAuthority`

 | 

The service's evaluation of the user's authority to pay or approve all transactions in the input. If `true`, the user passed all aspects of the financial authority evaluation based on input parameters. If `false`, one or more aspects of the evaluation failed.

 |
| 

`claimCoverageDetails`

 | 

A detailed accounting of each claim coverage evaluated, independent of the overall financial authority status of the entire transaction. For each transaction, details show:

-   The amount of the current request.
    
-   What's already been paid for losses and expenses.
    
-   Pending payments for losses and expenses, if `includePendingPayments` is true.
    
-   The maximum amounts the user can pay or approve for losses and expenses.
    
-   The service's evaluation of the user's authority to pay or approve each transaction amount.
    

 |
| 

`AuthorityFailStatusUpdate`

 | 

Status updates made based on `AuthorityFailClaimStatus`, `AuthorityFailClaimCoverageStatus`, and `AuthorityFailClaimCoveragePaymentDetailStatus` remote options in input JSON.

 |

```json
{
 "userId": "UserA",
 "userFinancialAuthority": false,
 "formattedErrorMessage": "User requested amount exceeded the maximum Authority amount",
 "failedItemIds": [
   "ClaimCoveragePaymentId1",
   "ClaimCoveragePaymentDetailId4"
 ],
 "passedItemIds": [
   "ClaimCoveragePaymentId3",
   "ClaimCoveragePaymentDetailId2"
 ],
 "failedClaimCoverageIds": [
   "ClaimCoverageCollision",
   "ClaimCoverageBodilyInjury"
 ],
 
 "claimCoveragesDetails": [
   {
     "userFinancialAuthority": false,
     "claimCoverageId": "ClaimCoverageCollision",
     "previousPaidLossAmount": "6000",
     "currentRequestedLossValuationAmount": "11000", // paid + pending items
     "maximumLossUserAuthorityAmount": "10000",
     "previousPaidExpenseAmount": "0",
     "currentRequestedExpenseValuationAmount": "100", // paid + pending items
     "maximumExpenseUserAuthorityAmount": "100",
     "claimCoveragePaymentDetails": [
       {
         "id": "ClaimCoveragePaymentId1",
         "name": "ClaimCoveragePayment1",
         "status": "Open",
         "adjustedAmount": "5000",
         "type": "loss"
       },
       {
         "id": "ClaimCoveragePaymentId3",
         "name": "ClaimCoveragePayment3",
         "status": "Open",
         "adjustedAmount": "50",
         "type": "expense"
       }
     ]
   },
   {
     "userFinancialAuthority": false,
     "claimCoverageId": "ClaimCoverageBodilyInjury",
     "previousPaidLossAmount": "0",
     "currentRequestedLossValuationAmount": "10000", // paid + pending items
     "maximumLossUserAuthorityAmount": "10000",
     "previousPaidExpenseAmount": "150",
     "currentRequestedExpenseValuationAmount": "250", // paid + pending items
     "maximumExpenseUserAuthorityAmount": "200",
     "claimCoveragePaymentDetails": [
       {
           "id": "ClaimCoveragePaymentDetailId2",
           "name": "ClaimCoveragePayment2",
           "status": "Open",
           "adjustedAmount": "10000",
           "type": "loss"
       },
       {
           "id": "ClaimCoveragePaymentDetailId4",
           "name": "ClaimCoveragePayment4",
           "status": "Open",
           "adjustedAmount": "100",
           "type": "expense"
        }
     ]
   }
 ]
}
```

## See Also

[Create a Payment Authorization Workflow](https://help.salesforce.com/s/articleView?id=ind.insurance_finauth_create_workflow.htm&language=en_US&type=5 "Configure the building blocks of your business process for financial transaction payment authorization.")

Did this article solve your issue?

Let us know so we can improve!

YesNo