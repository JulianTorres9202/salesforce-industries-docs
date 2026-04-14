---
title: "InsClaimItemService:invokeInitiatePaymentIP"
source: "https://help.salesforce.com/s/articleView?id=ind.insurance_insclaimitemservice__invokeinitiatepaymentip.htm&language=en_US&type=5"
scraped: "2026-04-14"
filter: "ind.insurance_"
---# InsClaimItemService:invokeInitiatePaymentIP

InsClaimItemService:invokeInitiatePaymentIP[](https://help.salesforce.com/s?language=en_US)

You are here:

1.  [Salesforce Help](/s/?language=en_US)
2.  [Docs](/s/products?language=en_US)
3.  [Digital Insurance](https://help.salesforce.com/s/articleView?id=ind.insurance_admin_standard.htm&language=en_US&type=5)

# InsClaimItemService:invokeInitiatePaymentIP

Use this service to initiate loss or expense payments.

[](https://help.salesforce.com/s?language=en_US)

Class: `InsClaimItemService`

Method: `invokeInitiatePaymentIP`

[](https://help.salesforce.com/s?language=en_US)

## How It Works

This service is triggered in these scenarios:

-   When you click Pay on each Loss/Expense line item (for per line payment) in the Claim Financials tab.
    
-   When you click Pay Selected Items (for multiple line payments) in the Claim Financials tab.
    

1.  The service parses the received Ids.
    
2.  The service checks if the Ids are Vlocity's `ClaimLineItem__c` or Salesforce's `ClaimCoveragePaymentDetail`.
    
3.  It then checks if the line items are of the same type (loss/expense) and in the same currency (if you have enabled multiple currencies in the org). The service throws an error if the validation fails or proceeds to the next step if the validation succeeds.
    
4.  The service calculates the sum of the line items and then checks the total amount against all applicable LIMIT Power Attributes of the Policy/Claim, if any.
    
5.  The service invokes the integration procedure defined under Custom Setting → Insurance Configuration Setup → ClaimInitiatePaymentIP.
    
    You can customize the Integration Procedure. The default integration procedure follows this workflow in the Salesforce Data Model:
    
    -   Performs a RemoteAction call to [InsClaimItemService:createPayments](https://help.salesforce.com/s/articleView?id=ind.insurance_insclaimitemservice__createpayments.htm&language=en_US&type=5 "Use this service to create and save claim payment records based on the line item IDs and the groupPayments option.").
        
    -   Saves the LIMITs Power Attributes (Policy Terms Tracking Entry) records.
        
    
    To use a financial authorization workflow, you add a remote action to the Integration Procedure and configure it to call `InsClaimItemService: claimCoverageValuation`.
    
    Error Handling
    
    If you want to configure any business rules to run between when a user clicks the Pay button and when the payment is processed, you can configure a `Response Action` step in the Integration Procedure. Use `errorMessage` as the Key and the `description` of the error message as the Value. If the error message is thrown before the createPayments Remote Action, then that error message is thrown to the user via a Toast Message on the Claims Financials page.
    

[](https://help.salesforce.com/s?language=en_US)

## Remote Options

| 
Remote Option

 | 

Description

 |
| --- | --- |
| 

`itemIds`

 | 

A list of `ClaimLineItem__c` Ids (Vlocity Data Model) or `ClaimCoveragePaymentDetail` Ids (Salesforce Data Model).

 |

[](https://help.salesforce.com/s?language=en_US)

## Input JSON

Here's the format of the input JSON:

```json
{ 
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

```json
{ 
    "itemIds": [
        {
            "Id" : "01t000000000000001"
        },
        {
            "Id" : "01t000000000000002"
        }
    ]
}
```

[](https://help.salesforce.com/s?language=en_US)

## Output JSON

-   The service throws an exception message if the type/currency isn’t the same.
    
-   The service throws an exception message if the total amount exceeds any applicable LIMIT Power Attribute defined in the policy/claim.
    

## See Also

-   [InsClaimItemService:claimCoverageValuation](https://help.salesforce.com/s/articleView?id=ind.insurance_insclaimitemservice_claimcoveragevaluation.htm&language=en_US&type=5 "Use this service to verify that users have the authority to pay or approve amounts in different types of financial activities.")
    

Did this article solve your issue?

Let us know so we can improve!

YesNo