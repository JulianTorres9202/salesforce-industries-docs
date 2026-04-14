---
title: "InsQuoteService:calculateTaxesAndFees"
source: "https://help.salesforce.com/s/articleView?id=ind.insurance_insquoteservice__calculatetaxesandfees.htm&language=en_US&type=5"
scraped: "2026-04-14"
filter: "ind.insurance_"
---# InsQuoteService:calculateTaxesAndFees

InsQuoteService:calculateTaxesAndFees[](https://help.salesforce.com/s?language=en_US)

You are here:

1.  [Salesforce Help](/s/?language=en_US)
2.  [Docs](/s/products?language=en_US)
3.  [Digital Insurance](https://help.salesforce.com/s/articleView?id=ind.insurance_admin_standard.htm&language=en_US&type=5)

# InsQuoteService:calculateTaxesAndFees

Use this service to calculate and save taxes and fees on a target quote.

Tax and fee information is saved on both the quote object and on the quote line item object.

[](https://help.salesforce.com/s?language=en_US)

[](https://help.salesforce.com/s?language=en_US)Note

This service isn't supported for guest users.

If a guest user tries to run an OmniScript or Integration Procedure or UI function that uses this service, the service will not run and the guest user will see an error message.

[](https://help.salesforce.com/s?language=en_US)

Class: `InsQuoteService`

[](https://help.salesforce.com/s?language=en_US)

Method: `calculateTaxesAndFees`

[](https://help.salesforce.com/s?language=en_US)

## How It Works

1.  Takes the `quoteId`, and the `jurisdictionId` and the `effectiveDate` (if specified) and calculates the taxes and fees to be applied to the quote.
    
2.  If saveChanges is set (or defaulted) to `true`, saves the calculated taxes and fees in one of three ways.
    
    -   If a Quote Line Item has calculated taxes and fees, a `QuotePricingAdjustment__c` record representing that tax/fee is saved. The `QuotePricingAdjustment__c` record holds the calculated amount (`Amount__c`), the associated Quote Line Item (`QuoteItemId__c`) and Quote (`QuoteId__c`), the type (`tax` or `fee`; `AdjustmentType__c`), and the associated tax/fee (`PriceListEntryId__c`).
        
    -   If a Quote Line Item or its children have calculated taxes, the sum of the calculated taxes on itself and its children will be stored on the `TaxAmount__c` field.
        
    -   If a Quote Line Item or its children have calculated fees, the sum of the calculated fees on itself and its children are stored on the `FeeAmount__c` field.
        
    
    [](https://help.salesforce.com/s?language=en_US)Note
    
    If `saveChanges` is set to `false`, the `QuotePricingAdjustment__c` and updates to the Quote Line Item records are not saved.
    
3.  At the Quote level, the sum of all of the tax amounts and fee amounts are stored on the `TotalTaxAmount__c` and `TotalFeeAmount__c` fields respectively.
    

[](https://help.salesforce.com/s?language=en_US)

## Remote Options

| 
Option

 | 

Description

 |
| --- | --- |
| 

`quoteId`

 | 

Required

Id of the quote that this service will calculate taxes and fees for.

 |
| 

`jurisdictionIds`

 | 

Optional

Calculates taxes and fees associated with the provided jurisdictions only.

 |
| 

`effectiveDate`

 | 

Optional

Calculate taxes and fees that become effective on the specified date only.

If not provided, the value defaults to the target quote's `EffectiveDate__c`. If `EffectiveDate__c` is null, value defaults to today’s date.

 |
| 

`saveChanges`

 | 

Optional

`true` or `false`

Defaults to `true`.

If `true`, saves calculated taxes and fees on the quote.

If `false`, does not save the calculated taxes and fees on the quote.

 |
| `withTaxFeeRounding` | 

Optional

If true, the calculated tax and fee amounts are rounded to two decimal places by using the half even rounding method. If false, rounding is disabled.

Defaults to false.

 |

[](https://help.salesforce.com/s?language=en_US)

## Input JSON

This service doesn't take an input JSON.

[](https://help.salesforce.com/s?language=en_US)

## Output JSON

The service returns a JSON representation of the quote containing only product and tax/fee information.

```
{
  "productId": 1,
  "productName": "Product",
  "ProductCode": "P",
  "taxesAndFees": [{
    "Id": 1,
    "Amount__c": 10,
    "PriceListEntryId__c": 11,
    "AdjustmentType__c": "Tax"
  }, {
    "Id": 2,
    "Amount__c": 15,
    "PriceListEntryId__c": 12,
    "AdjustmentType__c": "Fee"
  }],
  "taxAmount": 25
  "feeAmount": 30
  "childProducts": [{
    "productId": 2,
    "productName": "Insured Item",
    "ProductCode": "II",
    "instanceKey": "My Insured Item",
    "taxesAndFees": [{
      "Id": 3,
      "Amount__c": 15,
      "PriceListEntryId__c": 16,
      "AdjustmentType__c": "Tax"
    }],
    "taxAmount": 15
  }, {
    "productId": 3,
    "productName": "Coverage",
    "ProductCode": "C",
    "taxesAndFees": [{
      "Id": 4,
      "Amount__c": 15,
      "PriceListEntryId__c": 21
      "AdjustmentType__c": "Fee"
    }],
    "feeAmount": 15
  }]
}
```

Did this article solve your issue?

Let us know so we can improve!

YesNo