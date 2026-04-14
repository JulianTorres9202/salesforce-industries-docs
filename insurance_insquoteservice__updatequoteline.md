---
title: "InsQuoteService:updateQuoteLine"
source: "https://help.salesforce.com/s/articleView?id=ind.insurance_insquoteservice__updatequoteline.htm&language=en_US&type=5"
scraped: "2026-04-14"
filter: "ind.insurance_"
---# InsQuoteService:updateQuoteLine

InsQuoteService:updateQuoteLine[](https://help.salesforce.com/s?language=en_US)

You are here:

1.  [Salesforce Help](/s/?language=en_US)
2.  [Docs](/s/products?language=en_US)
3.  [Digital Insurance](https://help.salesforce.com/s/articleView?id=ind.insurance_admin_standard.htm&language=en_US&type=5)

# InsQuoteService:updateQuoteLine

Use this service to update items on the quote.

[](https://help.salesforce.com/s?language=en_US)

[](https://help.salesforce.com/s?language=en_US)Note

This service isn't supported for guest users.

If a guest user tries to run an OmniScript or Integration Procedure or UI function that uses this service, the service will not run and the guest user will see an error message.

[](https://help.salesforce.com/s?language=en_US)

Class: `InsQuoteService`

Method: `updateQuoteLine`

[](https://help.salesforce.com/s?language=en_US)

## How It Works

1.  The service takes the quoteId, quoteLineId, and attributeValues.
    
2.  Updates the quote.
    

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

Id of the quote

 |
| 

`quoteLineId`

 | 

Required

Id of QuoteLineItem to update

 |
| 

`attributeValues`

 | 

Required

Map of attributes to update on the target QuoteLineItem

 |
| 

`rootItemId`

 | 

Required

Root level QuoteLineItem for the target QuoteLineItem

 |
| 

`rootProductId`

 | 

Required

Product Id of root level QuoteLineItem

 |
| 

`attributeValueDecoder`

 | 

Optional

Map used to decode split attributes

 |
| 

`reprice`

 | 

Optional

`false` or `true`

Defaults to `false`

If `true`, the quote is repriced after being updated.

If `false`, the quote is not repriced after being updated.

 |
| 

`recalculateTaxesAndFees`

 | 

Optional

`true` or `false`

Defaults to `true`

If `true`, taxes and fees are recalculated after being updated.

If `false`, does not recalculate taxes and fees after being updated.

 |
| 

`runRules`

 | 

Optional

`true` or `false`

Defaults to `true`

If `true`, set value rules are run after being updated.

If `false`, set value rules are not run after being updated.

 |

[](https://help.salesforce.com/s?language=en_US)

## Input JSON

This is an example of the input JSON for this service.

```
{
        "quoteId": "0Q02E000004H8KASA0",
        "quoteLineId": "0QL2E0000063VzPWAU",
        "rootItemId": "0QL2E0000063VzJWAU",
        "rootProductId": "01t2E00000MyUkpQAF",
        "attributeValues": {
          "autoMake": "Honda",
          "autoModel": "Odyssey",
          "autoYear": 2008
}
```

[](https://help.salesforce.com/s?language=en_US)

## Output JSON

This service returns the following:

-   If 'runRules' option is true, 'updatedAttrs' output field is returned, containing a map of attributes that were updated and their new values.
    
-   If 'reprice' options is true, 'calculatedPrice' output field is returned, containing a map of QuoteLineItem ids and their new prices.
    
-   If 'recalculateTaxesAndFees' option is true, 'calculatedTaxesAndFees' output field is returned, containing a map of QuoteLineItem ids and the associated taxes/fees.
    

```
{
    "result": {
        "calculatedTaxesAndFees": {
            "0QL2E0000063VzLWAU": {
                "feeAmount": null,
                "taxAmount": null
            },
            "0QL2E0000063VzdWAE": {
                "feeAmount": 5,
                "taxAmount": 0.625
            },
            "0QL2E0000063VzcWAE": {
                "feeAmount": null,
                "taxAmount": null
            },
            "0QL2E0000063VzbWAE": {
                "feeAmount": 5,
                "taxAmount": 2.5
            },
            "0QL2E0000063VzaWAE": {
                "feeAmount": null,
                "taxAmount": null
            },
            "0QL2E0000063VzZWAU": {
                "feeAmount": null,
                "taxAmount": null
            },
            "0QL2E0000063VzYWAU": {
                "feeAmount": null,
                "taxAmount": null
            },
            "0QL2E0000063VzPWAU": {
                "feeAmount": 220,
                "taxAmount": 3.125
            },
            "0QL2E0000063VzNWAU": {
                "feeAmount": null,
                "taxAmount": null
            },
            "0QL2E0000063VzkWAE": {
                "feeAmount": null,
                "taxAmount": null
            },
            "0QL2E0000063VzpWAE": {
                "feeAmount": 5,
                "taxAmount": 0.625
            },
            "0QL2E0000063VzoWAE": {
                "feeAmount": null,
                "taxAmount": null
            },
            "0QL2E0000063VznWAE": {
                "feeAmount": 5,
                "taxAmount": 2.5
            },
            "0QL2E0000063VzmWAE": {
                "feeAmount": null,
                "taxAmount": null
            },
            "0QL2E0000063VzlWAE": {
                "feeAmount": null,
                "taxAmount": null
            },
            "0QL2E0000063VzRWAU": {
                "feeAmount": 220,
                "taxAmount": 3.125
            },
            "0QL2E0000063VzJWAU": {
                "feeAmount": 540,
                "taxAmount": 156.25
            }
        },
        "calculatedPrice": {
            "0Q02E000004H8KASA0": "{\"2016 Camry Toyota\":{\"AUTO.instanceKey\":\"2016 Camry Toyota\",\"totalPrice\":7500.00,\"stateTotal\":6250.00,\"alanTotal\":0.00,\"collisionTotal\":250.00,\"comprehensiveTotal\":1000.00,\"liabilityTotal\":0.00,\"totalLimitTotal\":0.00,\"perAccidentalTotal\":0.00,\"perPersonTotal\":0.00,\"ID\":\"0\"},\"2018 530 BMW\":{\"AUTO.instanceKey\":\"2018 530 BMW\",\"totalPrice\":6000.00,\"stateTotal\":5000.00,\"alanTotal\":0.00,\"collisionTotal\":500.00,\"comprehensiveTotal\":500.00,\"liabilityTotal\":0.00,\"totalLimitTotal\":0.00,\"perAccidentalTotal\":0.00,\"perPersonTotal\":0.00,\"ID\":\"3\"},\"2006 Honda Odyssey\":{\"AUTO.instanceKey\":\"2006 Honda Odyssey\",\"totalPrice\":7500.00,\"stateTotal\":6250.00,\"alanTotal\":0.00,\"collisionTotal\":250.00,\"comprehensiveTotal\":1000.00,\"liabilityTotal\":0.00,\"totalLimitTotal\":0.00,\"perAccidentalTotal\":0.00,\"perPersonTotal\":0.00,\"ID\":\"1\"},\"2015 Lexus LX250\":{\"ID\":\"2\",\"perPersonTotal\":100.00,\"perAccidentalTotal\":250.00,\"totalLimitTotal\":1000.00,\"liabilityTotal\":1350.00,\"comprehensiveTotal\":500.00,\"collisionTotal\":500.00,\"alanTotal\":0.00,\"stateTotal\":11750.00,\"totalPrice\":14100.00,\"AUTO.instanceKey\":\"2015 Lexus LX250\"},\"2006  Odyssey\":{\"AUTO.instanceKey\":\"2006  Odyssey\",\"totalPrice\":7500.00,\"stateTotal\":6250.00,\"alanTotal\":0.00,\"collisionTotal\":250.00,\"comprehensiveTotal\":1000.00,\"liabilityTotal\":0.00,\"totalLimitTotal\":0.00,\"perAccidentalTotal\":0.00,\"perPersonTotal\":0.00,\"ID\":\"1\"},\"2018  BMW\":{\"AUTO.instanceKey\":\"2018  BMW\",\"totalPrice\":33000.00,\"stateTotal\":27500.00,\"alanTotal\":0.00,\"collisionTotal\":2500.00,\"comprehensiveTotal\":3000.00,\"liabilityTotal\":0.00,\"totalLimitTotal\":0.00,\"perAccidentalTotal\":0.00,\"perPersonTotal\":0.00,\"ID\":\"11\"},\"2020 Porsche 911\":{\"AUTO.instanceKey\":\"2020 Porsche 911\",\"totalPrice\":14100.00,\"stateTotal\":11750.00,\"alanTotal\":0.00,\"collisionTotal\":500.00,\"comprehensiveTotal\":500.00,\"liabilityTotal\":1350.00,\"totalLimitTotal\":1000.00,\"perAccidentalTotal\":250.00,\"perPersonTotal\":100.00,\"ID\":\"12\"},\"2008 Honda Odyssey\":{\"AUTO.instanceKey\":\"2008 Honda Odyssey\",\"totalPrice\":7500.00,\"stateTotal\":6250.00,\"alanTotal\":0.00,\"collisionTotal\":250.00,\"comprehensiveTotal\":1000.00,\"liabilityTotal\":0.00,\"totalLimitTotal\":0.00,\"perAccidentalTotal\":0.00,\"perPersonTotal\":0.00,\"ID\":\"1\"}}",
            "0QL2E0000063VzkWAE": 0,
            "0QL2E0000063VzpWAE": 250,
            "0QL2E0000063VzoWAE": 0,
            "0QL2E0000063VznWAE": 1000,
            "0QL2E0000063VzmWAE": 0,
            "0QL2E0000063VzlWAE": 0,
            "0QL2E0000063VzZWAU": 0,
            "0QL2E0000063VzaWAE": 0,
            "0QL2E0000063VzbWAE": 1000,
            "0QL2E0000063VzcWAE": 0,
            "0QL2E0000063VzdWAE": 250,
            "0QL2E0000063VzYWAU": 0,
            "0QL2E0000063VzPWAU": 0,
            "0QL2E0000063VzRWAU": 0,
            "0QL2E0000063VzKWAU": 0,
            "0QL2E0000063VzLWAU": 0,
            "0QL2E0000063VzMWAU": 0,
            "0QL2E0000063VzNWAU": 0,
            "0QL2E0000063VzJWAU": 15000
        },
        "updatedAttrs": {
            "COMP_COVERAGE.COMPREHENSIVE": 1000
        },
        "0QL2E0000063VzbWAE": true,
        "0QL2E0000063VzPWAU": true
    },
    "errorCode": "INVOKE-200",
    "error": "OK"
}
```

Did this article solve your issue?

Let us know so we can improve!

YesNo