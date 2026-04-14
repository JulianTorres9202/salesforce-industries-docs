---
title: "InsQuoteService:getAccountQuotes"
source: "https://help.salesforce.com/s/articleView?id=ind.insurance_insquoteservice__getaccountquotes.htm&language=en_US&type=5"
scraped: "2026-04-14"
filter: "ind.insurance_"
---# InsQuoteService:getAccountQuotes

InsQuoteService:getAccountQuotes[](https://help.salesforce.com/s?language=en_US)

You are here:

1.  [Salesforce Help](/s/?language=en_US)
2.  [Docs](/s/products?language=en_US)
3.  [Digital Insurance](https://help.salesforce.com/s/articleView?id=ind.insurance_admin_standard.htm&language=en_US&type=5)

# InsQuoteService:getAccountQuotes

Use this service to retrieve quote records associated with an `accountId`.

[](https://help.salesforce.com/s?language=en_US)

Class: InsQuoteService

Method: getAccountQuotes

[](https://help.salesforce.com/s?language=en_US)

## Description

This service is intended for Experience Site users who don’t have access to quotes and the default quote list.

[](https://help.salesforce.com/s?language=en_US)

## How It Works

1.  If the user is an authenticated Experience Site User:
    
    1.  The service decrypts the provided `accountId`. If the `accountId` provided is not encrypted and can't be decrypted, the service throws an exception.
        
    2.  The service decrypts the provided `accountId`. If the `accountId` provided is not encrypted and can't be decrypted, the service throws an exception.
        
    3.  The quote fields returned are based on the **QuoteDetail** field set and exclude the fields not in **CustomerCommunityFLSCheckFields**. `ObjectIds` are encrypted.
        
2.  If the user is a Guest User, an **IllegalArgumentException** error message displays: "Method `getAccountQuotes` is not supported for Guest User."
    
3.  For other user types:
    
    1.  The service queries for quotes where `Quote.AccountId` = <`accountId`\> LIMIT 10000.
        
    2.  The quote fields returned are based on the **QuoteDetail** field set.
        

[](https://help.salesforce.com/s?language=en_US)

## Remote Options

| 
Remote Option

 | 

Description

 |
| --- | --- |
| 

`accountId`

 | 

Required.

The `AccountId`, or the encrypted `AccountId` if the request is for a customer or guest user.

 |

[](https://help.salesforce.com/s?language=en_US)

## Input JSON

This service doesn't take an input JSON.

[](https://help.salesforce.com/s?language=en_US)

## Output JSON

The service returns a quote list in the output JSON.

```json
{
  "error": "OK",
  "quoteList": [
    {
      "Id": "cfqsBqZvLizhq97-3uhwCPPAdOk2JUvR7WoUHsuSMUw.R0wt7dIpwjaoYN46iO6-5vtTWy2JMfMxHEHlWnOc9NYQTYXsaUa7wKM9_rVBSZgR",
      "<namespace>__TotalFeeAmount__c": 0,
      "<namespace>__TotalTaxAmount__c": 0,
      "<namespace>__TotalAmount__c": 20,
      "<namespace>__GroupCensusId__c": "a4f5w000000yIixAAE",
      "<namespace>__Type__c": "New Business",
      "<namespace>__RecordTypeName__c": "Quote",
      "<namespace>__RatingType__c": "Composite",
      "<namespace>__RootItemTotal__c": 20,
      "AccountId": "8SjtZ9HRDSZwNMblhy1VZKjj5J20HJXhYAQ75iwd_Ns.GC1PAoy2IUb1uvWCth0ycEVvgP_iWUgOTA1O9uqTJIos70elovNXQV5DWlpc9I4T",
      "<namespace>__TotalPremiumforTerm__c": 20,
      "<namespace>__TotalSumInsured__c": 0,
      "<namespace>__Term__c": "Annual",
      "<namespace>__TotalTaxTermDifference__c": 0,
      "<namespace>__TotalPremiumTermDifference__c": 20,
      "<namespace>__TotalFeeTermDifference__c": 0,
      "<namespace>__TotalAmountTermDifference__c": 20,
      "<namespace>__EndDate__c": "2022-04-15",
      "<namespace>__EffectiveDate__c": "2021-04-16",
      "<namespace>__DaysRemaining__c": 365
    }
  ]
}
```

Did this article solve your issue?

Let us know so we can improve!

YesNo