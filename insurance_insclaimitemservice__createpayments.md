---
title: "InsClaimItemService:createPayments"
source: "https://help.salesforce.com/s/articleView?id=ind.insurance_insclaimitemservice__createpayments.htm&language=en_US&type=5"
scraped: "2026-04-14"
filter: "ind.insurance_"
---# InsClaimItemService:createPayments

InsClaimItemService:createPayments[](https://help.salesforce.com/s?language=en_US)

You are here:

1.  [Salesforce Help](/s/?language=en_US)
2.  [Docs](/s/products?language=en_US)
3.  [Digital Insurance](https://help.salesforce.com/s/articleView?id=ind.insurance_admin_standard.htm&language=en_US&type=5)

# InsClaimItemService:createPayments

Use this service to create and save claim payment records based on the line item IDs and the `groupPayments` option.

[](https://help.salesforce.com/s?language=en_US)

Class: `InsClaimItemService`

Method: `createPayments`

[](https://help.salesforce.com/s?language=en_US)

## How It Works

Depending on the claim payment Id, the service either creates a Vlocity payment or a Salesforce payment.

Important

Salesforce Data Model support is available from the Insurance Summer '21 release onward.

_Salesforce Data Model_

1.  The service parses the line item Ids and queries the corresponding `ClaimCoveragePaymentDetail` records.
    
2.  Depending on the input of the `groupPayments` option, the service creates and saves the `ClaimPaymentSummary` records.
    
3.  The service updates the following parameters in the `ClaimCoveragePaymentDetail` records:
    
    -   Sets the `ClaimPaymentSummary.Id`.
        
    -   Sets the `status` as paid unless you enter a different value for this remote option.
        
4.  The service updates the related `ClaimCoverage` ReserveAmounts (Loss/Expense) and the `ClaimCoverageReserveDetail`, if any.
    
5.  It then creates and saves the `ClaimCoverageReserveAdjustments` to track changes in the reserve amounts against the paid amounts.
    

_Vlocity Data Model_

1.  The service parses the transaction Ids and queries the corresponding `InsClaimReserveTransaction__c` records.
    
2.  Depending on the input of `groupPayments`, the service then creates and saves the `ClaimPayment__c records`.
    
3.  The service updates the `InsClaimReserveTransaction__c` records with the Payment Id.
    

[](https://help.salesforce.com/s?language=en_US)

## Remote Options

| 
Remote Option

 | 

Description

 |
| --- | --- |
| 

`groupPayments`

 | 

Required.

If "true", it creates a single `ClaimPayment__c` or `ClaimPaymentSummary` record per recipient for multiple line item payments.

If "false", it creates a single record per line item.

 |
| 

`transactionIds`

 | 

Required.

The list of transaction Ids. The service uses these transaction Ids to query the corresponding `InsClaimReserveTransaction__c` records. This remote option is applicable only for the Vlocity Data Model.

 |
| 

`itemIds`

 | 

Required.

The list of item Ids. The service uses these item Ids to query the corresponding `ClaimCoveragePaymentDetail` records. This remote option is applicable only for the Salesforce Data Model.

See also: [InsClaimItemService:invokeInitiatePaymentIP](https://help.salesforce.com/s/articleView?id=ind.insurance_insclaimitemservice__invokeinitiatepaymentip.htm&language=en_US&type=5 "Use this service to initiate loss or expense payments.")

 |
| 

`status`

 | 

Optional.

The status for the `ClaimCoveragePaymentDetail` paid. It defaults as paid if the value isn’t set. This remote option is applicable only for the Salesforce Data Model.

 |

[](https://help.salesforce.com/s?language=en_US)

## Input JSON

Here's the format of input JSON:

Vlocity Data Model

```json
{ 
    "groupPayments": <Boolean>,
    "transactionIds": [<Id>, <Id>]
}
```

Salesforce Data Model

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

Here's an example of the input JSON:

Vlocity Data Model

```json
{ 
    "groupPayments": false,
    "transactionIds": ["01t000000000000001", "01t000000000000002"]
}
```

Salesforce Data Model

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

[](https://help.salesforce.com/s?language=en_US)

## Output JSON

Creates and saves the claim payment records.

Did this article solve your issue?

Let us know so we can improve!

YesNo