---
title: "InsQuoteService:updateQuotePlans"
source: "https://help.salesforce.com/s/articleView?id=ind.insurance_insquoteservice__updatequoteplans.htm&language=en_US&type=5"
scraped: "2026-04-14"
filter: "ind.insurance_"
---# InsQuoteService:updateQuotePlans

InsQuoteService:updateQuotePlans[](https://help.salesforce.com/s?language=en_US)

You are here:

1.  [Salesforce Help](/s/?language=en_US)
2.  [Docs](/s/products?language=en_US)
3.  [Digital Insurance](https://help.salesforce.com/s/articleView?id=ind.insurance_admin_standard.htm&language=en_US&type=5)

# InsQuoteService:updateQuotePlans

Use this service in an OmniScript to add, update, or upsert (add and update) either coverages or attributes for one or more Group Benefit plans across a quote. This service is designed to process only coverages under root products.

[](https://help.salesforce.com/s?language=en_US)

[](https://help.salesforce.com/s?language=en_US)Note

This service isn't supported for guest users.

If a guest user tries to run an OmniScript or Integration Procedure or UI function that uses this service, the service will not run and the guest user will see an error message.

[](https://help.salesforce.com/s?language=en_US)

Class: `InsQuoteService`

Method: `updateQuotePlans`

[](https://help.salesforce.com/s?language=en_US)

## How It Works

For example, if a coverage has an attribute with the attribute code `cat1_copay_inn`, and the input data map contains a partial attribute code copay, there would be a match, since `cat1_copay_inn` contains the string `copay`, and the attributes on this coverage would be updated.

1.  The service takes the `quoteId` to find the target quote.
    
2.  Uses the `inputKey` to locate the input data (coverages, attributes).
    
3.  Modifies coverages or attributes in a quote, based on `operationScope` (coverages or attributes) and `operationType` (insert, updates, upserts).
    

-   If `operationScope` is _coverages_, the input coverages on the target plans are inserted, updated, or upserted in the target quote, based on the `operationType`.
    
-   If `operationScope` is _attributes_, the coverage attributes in the target quote are updated, based on which coverages contain attributes whose code contains one of the partial attribute codes as listed in the input data map.
    

Note

NOTE: If planIds are provided, the coverage will be updated only if it belongs to one of the planIds in the list, even if there is a match.

[](https://help.salesforce.com/s?language=en_US)Note

NOTE: To insert a new root product coverage, you need at least one child quote line item under the root product.

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

Required.

Id of target Quote.

 |
| 

`inputKey`

 | 

Required.

Key for where in the inputs map the input data (such as coverages) is specified.

 |
| 

`operationScope`

 | 

Required.

Scope of what is updated on the plans. Possible values are _coverages_ and _attributes_ (that is, either coverages or attributes can be updated).

 |
| 

`operationType`

 | 

Required when the operationScope is _coverages_ and ignored when the `operationScope` is _attributes_.

Type of operation performed: insert, update, or upsert.

 |
| 

`identifiers`

 | 

String value list of planIds.

Required when operationScope is _coverages_, optional when operationScope is _attributes_.

 |

[](https://help.salesforce.com/s?language=en_US)

## Options MAP

Here are sample options map variables, as used in a card, when the `operationScope` is _coverages_:

```
{
  'quoteId': '0Q0000000000000000',
  'inputKey': 'inputJson',
  'operationScope': 'coverages',
  'operationType': 'insert',
  'identifiers': planId1, planId2'
}
```

Here are sample options map variables, as used in a card, when the `operationScope` is _attributes_:

```

{
  'quoteId': '0Q0000000000000000',
  'inputKey': 'inputJson',
  'operationScope': 'attributes',
  'identifiers': '0QLf4000000SX3tGAG, 0QLf4000000SX3rGAG'
}
```

[](https://help.salesforce.com/s?language=en_US)

## Input JSON

If the `operationScope` is _coverages_, input data must contain a JSONResult object (or a map that can be parsed as a JSONResult object) which contains the coverages to insert or update (Coverage 1, Coverage 2, etc.):

```

{
  'inputJson': {
    'records': [{
      'productName': 'Coverage 1',
      'attributeCategories': [...],
      ...
    }, {
      'productName': 'Coverage 2',
      'attributeCategories': [...],
      ...
    }]
  }
}
```

If the `operationScope` is _attributes_, the input data must contain a map of partial attribute codes and their updated values, as shown in this example:

```
{
  'inputJson': {
    'copay': 20,
    'covered': '90%'
  }
}
```

[](https://help.salesforce.com/s?language=en_US)

## Example Usage

Let’s say you wanted to change the copay attribute value across the attribute category `ChirOffiProf`.

Assuming a standard naming convention of:

`attributeCategory_attributeCode_inNetwork/outOfNetwork`

With the following in-network and out-of-network copay attributes:

-   `ChirOffiProf_copay_inn`
    
-   `ChirOffiProf_copay_oon`
    

You would configure the `updateQuotePlans` service with the following inputs and options:

Inputs

Map of partial codes and their values (i.e., copay returns any attribute name with copay in the string.) The partial code in this case would be the attributeCode portion of the template:

```
{
    'copay': 20,
    'covered': 75
}
```

Options

-   quoteId
    
-   planId (QuoteLineItem Id)
    

The service will search for all of the coverages within the specified planIds that have an attribute which contains the partial attribute code (in this case, copay) and update those attributes with the new value (in this case, 20).

If no planId is specified, all coverages that have an attribute which contains the `attributeCode` partial being passed are updated.

Did this article solve your issue?

Let us know so we can improve!

YesNo