---
title: "InsQuoteService:addInsuredItem"
source: "https://help.salesforce.com/s/articleView?id=ind.insurance_insquoteservice__addinsureditem.htm&language=en_US&type=5"
scraped: "2026-04-14"
filter: "ind.insurance_"
---# InsQuoteService:addInsuredItem

InsQuoteService:addInsuredItem[](https://help.salesforce.com/s?language=en_US)

You are here:

1.  [Salesforce Help](/s/?language=en_US)
2.  [Docs](/s/products?language=en_US)
3.  [Digital Insurance](https://help.salesforce.com/s/articleView?id=ind.insurance_admin_standard.htm&language=en_US&type=5)

# InsQuoteService:addInsuredItem

Use this service to add insured items to quotes.

[](https://help.salesforce.com/s?language=en_US)

[](https://help.salesforce.com/s?language=en_US)Note

This service isn't supported for guest users.

If a guest user tries to run an OmniScript or Integration Procedure or UI function that uses this service, the service will not run and the guest user will see an error message.

[](https://help.salesforce.com/s?language=en_US)

Class: `InsQuoteService`

Method: `addInsuredItem`

[](https://help.salesforce.com/s?language=en_US)

## How It Works

The service adds the insured item, identified by the product Id, to a quote.

[](https://help.salesforce.com/s?language=en_US)

## Remote Options

| 
Option

 | 

Description

 |
| --- | --- |
| 

`rootLineId`

 | 

Required

Id of the root level QuoteLineItem, which is the parent of the insured item to add

 |
| 

`productId`

 | 

Required

Product Id of the insured item

 |
| 

`parentLineId`

 | 

Optional

If this is a grandchild insured item, this is the Id of the child QuoteLineItem

 |
| 

`instanceKey`

 | 

Optional

Unique name for the insured item

 |
| 

`attributeValues`

 | 

Optional

Attribute values for the insured item in a map where the key is attribute name and the value is the new attribute value

 |
| 

`isPrimary`

 | 

Optional

`true` or `false`

Defaults to `false`

If `true`, specifies that this is the primary grandchild insured item.

If `false`, specifies this is not the primary grandchild insured item.

 |

[](https://help.salesforce.com/s?language=en_US)

## Input JSON

This is an example of input JSON:

```
{
        "rootLineId": "0QL2E0000063VzJWAU",
        "productId": "01t2E00000MyUkbQAF",
        "attributeValues": {
          "autoYear": 2020,
          "autoMake": "Porsche",
          "autoModel": "911"
        }
```

[](https://help.salesforce.com/s?language=en_US)

## Output JSON

This service doesn't have output JSON.

Did this article solve your issue?

Let us know so we can improve!

YesNo