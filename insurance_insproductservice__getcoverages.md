---
title: "InsProductService:getCoverages"
source: "https://help.salesforce.com/s/articleView?id=ind.insurance_insproductservice__getcoverages.htm&language=en_US&type=5"
scraped: "2026-04-14"
filter: "ind.insurance_"
---# InsProductService:getCoverages

InsProductService:getCoverages[](https://help.salesforce.com/s?language=en_US)

You are here:

1.  [Salesforce Help](/s/?language=en_US)
2.  [Docs](/s/products?language=en_US)
3.  [Digital Insurance](https://help.salesforce.com/s/articleView?id=ind.insurance_admin_standard.htm&language=en_US&type=5)

# InsProductService:getCoverages

Use this service to get all the coverages for a product spec.

[](https://help.salesforce.com/s?language=en_US)

[](https://help.salesforce.com/s?language=en_US)Class: `InsProductService`

[](https://help.salesforce.com/s?language=en_US)

Method: `getCoverages`

[](https://help.salesforce.com/s?language=en_US)

## How It Works

1.  The service takes the `productID` of the target.
    
2.  Creates a Product JSON of product coverages.
    

[](https://help.salesforce.com/s?language=en_US)

## Remote Options

| 
Option

 | 

Description

 |
| --- | --- |
| 

`productId`

 | 

Id of the target Product

 |
| 

`onlyOptional`

 | 

Optional

Return only optional coverages. If not provided, defaults to false.

 |

[](https://help.salesforce.com/s?language=en_US)

## Input JSON

This service does not take an input JSON.

[](https://help.salesforce.com/s?language=en_US)

## Output JSON

The service returns the Product JSON for a specific product. Note that this Product JSON will not include pricing information.

If `onlyOptional` flag is set to true, only those coverages designated as optional will be included in the Product JSON; otherwise, all coverages are returned.

```
{
    "totalSize": 1,
    "records": [
        {
            "Id": "01tf4000003GucXAAS",
            "Name": "Product 1",
            ...,
            "childProducts": [
                "totalSize": 2,
                "records": [
                    {
                        "Id": "01tf4000003GucXAAS",
                        "Name": "Coverage 1",
                        "isOptional": false,
                        ...
                    },
                    {
                        "Id": "01tf4000003GucXAAS",
                        "Name": "Coverage 2",
                        "isOptional": true,
                        ...
                    }

                ]
            ],
            "attributeCategories": [...]
        }
    ]
}
```

Did this article solve your issue?

Let us know so we can improve!

YesNo