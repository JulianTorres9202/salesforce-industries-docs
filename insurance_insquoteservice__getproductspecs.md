---
title: "InsQuoteService:getProductSpecs"
source: "https://help.salesforce.com/s/articleView?id=ind.insurance_insquoteservice__getproductspecs.htm&language=en_US&type=5"
scraped: "2026-04-14"
filter: "ind.insurance_"
---# InsQuoteService:getProductSpecs

InsQuoteService:getProductSpecs[](https://help.salesforce.com/s?language=en_US)

You are here:

1.  [Salesforce Help](/s/?language=en_US)
2.  [Docs](/s/products?language=en_US)
3.  [Digital Insurance](https://help.salesforce.com/s/articleView?id=ind.insurance_admin_standard.htm&language=en_US&type=5)

# InsQuoteService:getProductSpecs

Use this service in an OmniScript to get a list of specific product specs used in a quote, at the Quote Line Item level, and which includes product information.

This is helpful in large group quoting when you want to retrieve the unique products in a quote with multiple root products and multiple instances of the same root product.

[](https://help.salesforce.com/s?language=en_US)

[](https://help.salesforce.com/s?language=en_US)Note

This service isn't supported for guest users.

If a guest user tries to run an OmniScript or Integration Procedure or UI function that uses this service, the service will not run and the guest user will see an error message.

[](https://help.salesforce.com/s?language=en_US)

Class: `InsQuoteService`

Method: `getProductSpecs`

[](https://help.salesforce.com/s?language=en_US)

## How It Works

1.  The service takes a `quoteId` and finds the quote.
    
2.  Returns a JSON that includes these values:
    
    -   `productId`
        
    -   `productName`
        
    -   `ProductCode`
        
    -   `Type`
        
    -   `Subtype`
        

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

Id of target quote.

 |

[](https://help.salesforce.com/s?language=en_US)

## Input JSON

This service does not take an input JSON.

[](https://help.salesforce.com/s?language=en_US)

## Output JSON

The service returns a list of unique product specs and product information in the output JSON (example below).

Note

These fields can be changed in the output JSON by modifying the `GetProductSpec` fieldSet on the Product2 object. Note that these fields will always be returned, even if they are removed from the fieldSet.

```
{
    "totalSize": 2,
    "records": [
        {
            "displaySequence": -1,
            "productId": "01tf4000003GucXAAS",
            "productName": "Large Group PMI Advance",
            "ProductCode": "LGPA",
            "Type": "Medical",
            "SubType": "PPO"
        },
        {
            "displaySequence": -1,
            "productId": "01tf4000003GucDAAS",
            "productName": "Customizable Benefit Plan - PPO2",
            "ProductCode": "ANTM CPD PPO2",
            "Type": "Medical",
            "SubType": "PPO"
        }
    ]
}
```

Did this article solve your issue?

Let us know so we can improve!

YesNo