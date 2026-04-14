---
title: "InsProductService:cloneProduct"
source: "https://help.salesforce.com/s/articleView?id=ind.insurance_insproductservice__cloneproduct.htm&language=en_US&type=5"
scraped: "2026-04-14"
filter: "ind.insurance_"
---# InsProductService:cloneProduct

InsProductService:cloneProduct[](https://help.salesforce.com/s?language=en_US)

You are here:

1.  [Salesforce Help](/s/?language=en_US)
2.  [Docs](/s/products?language=en_US)
3.  [Digital Insurance](https://help.salesforce.com/s/articleView?id=ind.insurance_admin_standard.htm&language=en_US&type=5)

# InsProductService:cloneProduct

Use this service to clone a product.

[](https://help.salesforce.com/s?language=en_US)

[](https://help.salesforce.com/s?language=en_US)Class: `InsProductService`

Method: `cloneProduct`

You can either add this service to the Products page layout as an action or button, or you can use it in an OmniScript or Integration Procedure flow.

[](https://help.salesforce.com/s?language=en_US)

## How It Works

1.  The service takes the `productId` of the policy product to be cloned.
    
2.  Creates a cloned policy product, including attributes, coverages, insured items, rating facts, and rules.
    
    The new (cloned) policy product has a unique `productId`.
    

[](https://help.salesforce.com/s?language=en_US)

## Remote Options

| 
Option

 | 

Description

 |
| --- | --- |
| 

`batchMode`

 | 

`true` or `false`

When set to `true`, this service submits a `VlocityBatchFramework` batch to clone the product.

Use this option if you have large products you need to clone.

 |
| 

`productId`

 | 

`theIdYouAreLookingFor`

The Id of the product the service will clone.

 |

[](https://help.salesforce.com/s?language=en_US)

## Input JSON

This service doesn't take an input JSON.

[](https://help.salesforce.com/s?language=en_US)

## Output JSON

The service returns an Id for the cloned product in the output JSON.

```
{
    "clonedId": a1j1I000000i6ElQAI,
    "error": "OK"
}
```

Did this article solve your issue?

Let us know so we can improve!

YesNo