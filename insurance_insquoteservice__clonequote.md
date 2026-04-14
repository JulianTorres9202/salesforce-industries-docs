---
title: "InsQuoteService:cloneQuote"
source: "https://help.salesforce.com/s/articleView?id=ind.insurance_insquoteservice__clonequote.htm&language=en_US&type=5"
scraped: "2026-04-14"
filter: "ind.insurance_"
---# InsQuoteService:cloneQuote

InsQuoteService:cloneQuote[](https://help.salesforce.com/s?language=en_US)

You are here:

1.  [Salesforce Help](/s/?language=en_US)
2.  [Docs](/s/products?language=en_US)
3.  [Digital Insurance](https://help.salesforce.com/s/articleView?id=ind.insurance_admin_standard.htm&language=en_US&type=5)

# InsQuoteService:cloneQuote

Use this service to clone a quote.

You can either add this service to the Quotes page layout as an action or button, or you can use it in an OmniScript or Integration Procedure flow.

Note

Before this service runs, the system runs a guest user check.

This service can be used by guest users. A guest user who's running an OmniScript, Integration Procedure, or UI task will be able to continue; this service will run. However, the quoteId and opportunityId are encrypted in these cases, so guest users cannot see these Ids.

[](https://help.salesforce.com/s?language=en_US)

Class: `InsQuoteService`

Method: `cloneQuote`

[](https://help.salesforce.com/s?language=en_US)

## How It Works

1.  This service takes the `quoteId` of the policy product to be cloned.
    
2.  Creates a clone of the quote, including coverages, insured items, insured parties, and quote line items.
    
    [](https://help.salesforce.com/s?language=en_US)The new (cloned) quote has a new unique `quoteId` and a unique **Quote Number** you can see on the quote detail page.
    

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

`%theIdYouAreLookingFor%`

The Id of the quote the service will clone.

 |

[](https://help.salesforce.com/s?language=en_US)

## Input JSON

This service doesn't take an input JSON.

[](https://help.salesforce.com/s?language=en_US)

## Output JSON

The service returns an Id for the cloned quote in the output JSON.

```
{
    "clonedId": a1j1I000000i6ElQAI,
    "error": "OK"
}
```

Did this article solve your issue?

Let us know so we can improve!

YesNo