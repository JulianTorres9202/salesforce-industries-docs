---
title: "InsClaimItemService:cancelPayments"
source: "https://help.salesforce.com/s/articleView?id=ind.insurance_insclaimitemservice__cancelpayments.htm&language=en_US&type=5"
scraped: "2026-04-14"
filter: "ind.insurance_"
---# InsClaimItemService:cancelPayments

InsClaimItemService:cancelPayments[](https://help.salesforce.com/s?language=en_US)

You are here:

1.  [Salesforce Help](/s/?language=en_US)
2.  [Docs](/s/products?language=en_US)
3.  [Digital Insurance](https://help.salesforce.com/s/articleView?id=ind.insurance_admin_standard.htm&language=en_US&type=5)

# InsClaimItemService:cancelPayments

Use this service to cancel claim loss and expense payments.

This service:

-   Updates the status of claim payment records to Cancelled.
    
-   Creates offsetting tracking entries that effectively remove the payment from claim financials and policy term standings.
    

[](https://help.salesforce.com/s?language=en_US)

Class: `InsClaimItemService`

Method: `cancelPayments`

[](https://help.salesforce.com/s?language=en_US)

## How It Works

[](https://help.salesforce.com/s?language=en_US)

1.  When a user clicks **Cancel** for one or more payment details on a claim’s **Financials** tab, an internal service called `InsClaimItemService: invokeInitiateCancelPaymentIP` initiates the cancellation process.
    
2.  The `InsClaimItemService: invokeInitiateCancelPaymentIP` internal service, which relies on a `ClaimInitiateCancelPaymentIP` custom setting and integration procedure that you configure, invokes `InsClaimItemService: cancelPayments`.
    
    To learn how to configure the `ClaimInitiateCancelPaymentIP` custom setting and integration procedure, see [Configure the Cancel Payment Action](https://help.salesforce.com/s/articleView?id=ind.insurance_configure_the_cancel_payment_action_619550.htm&language=en_US&type=5 "Configure your org with custom settings and an integration procedure to support canceling the payment made for a payment detail record.").
    
3.  The `InsClaimItemService: cancelPayments` service parses the `itemIds` or `paymentIds` provided, fetches corresponding data, and queries the corresponding `ClaimCoveragePaymentDetail` or `ClaimPaymentSummary` records.
    
    The service generates an error if:
    
    -   Any `lineItemIds` are missing for `ClaimCoveragePaymentDetail` records that are part of a linked payment.
        
    -   Any of the `ClaimCoveragePaymentDetail` records aren't paid.
        
4.  The service updates the status of `ClaimCoveragePaymentDetail` records to `Cancelled` unless you enter a different value for the `status` remote option.
    
5.  The service creates `ClaimCoveragePaymentDetail` records that are equal and opposite versions of the original ones. The new records have:
    
    -   Status set to `Reverted`.
        
    -   Negative `Amount` values.
        
6.  The service reverts applicable Deductible, Copay, Coinsurance, or Out of Pocket Maximum power attribute amounts, and creates corresponding term tracking entries.
    
7.  The service updates `ClaimPaymentSummary` records based on the `groupPayments` input. It:
    
    -   Sets `Payment Status` to `Cancelled` unless you enter a different value for the `status` remote option.
        
    -   Sets `Cancellation Date` to the date and time of the cancellation.
        
8.  The service reverts applicable Rolling, Lifetime, and Calendar Limit power attribute amounts, and creates corresponding term tracking entries.
    

[](https://help.salesforce.com/s?language=en_US)

## Remote Options

| 
Remote Option

 | 

Description

 |
| --- | --- |
| 

`itemIds` or `paymentIds`

 | 

Required.

A list of payment details or payment summaries to cancel. Specify either `itemIds` or `paymentIds`, not both.

For `itemIds`, specify a list of `ClaimCoveragePaymentDetail` IDs.

For `paymentIds`, specify a list of `ClaimPaymentSummary` IDs.

 |
| 

`groupPayments`

 | 

Required.

Whether to group payments by recipient when processing multiple loss or expense line items.

-   If `true` (the default), the service creates a single ClaimPaymentSummary record per recipient for multiple line item payments.
    
-   If `false`, the service creates a single ClaimPaymentSummary record per line item.
    

 |
| 

`status`

 | 

Optional.

The status value to set for each canceled `ClaimCoveragePaymentDetail` or `ClaimPaymentSummary`. The default value is `Cancelled`.

 |

[](https://help.salesforce.com/s?language=en_US)

## Input JSON

Here's the format of the input JSON if you use `itemIds`:

```json
{
    "groupPayments": <Boolean>,
    "itemIds": [
        {
            "Id" : <Id>
        },
        {
            "Id" : <Id>
        }
    ]
}
```

Here's an example of the input JSON with `itemIds`:

```json
{
    "groupPayments": true,
    "itemIds": [
        {
            "Id" : "01t000000000000003"
        },
        {
            "Id" : "01t000000000000004"
        }
    ]
}
```

[](https://help.salesforce.com/s?language=en_US)Here's the format of the input JSON if you use `paymentIds`:

```json
{
    "groupPayments": <Boolean>,
    "paymentIds": [
        {
            "Id" : <Id>
        },
        {
            "Id" : <Id>
        }
    ]
}
```

[](https://help.salesforce.com/s?language=en_US)Here's an example of the input JSON with `paymentIds`:

[](https://help.salesforce.com/s?language=en_US)`{     "groupPayments": false,     "paymentIds": [         {             "Id" : "0l8RN0000000000005"         },         {             "Id" : "0l8RN0000000000006"         }     ] }`

[](https://help.salesforce.com/s?language=en_US)

## Output JSON

There's no output JSON associated with this service.

Did this article solve your issue?

Let us know so we can improve!

YesNo