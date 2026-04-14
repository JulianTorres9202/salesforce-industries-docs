---
title: "InsFormularyService:getListOfDrugs"
source: "https://help.salesforce.com/s/articleView?id=ind.insurance_insformularyservice__getlistofdrugs.htm&language=en_US&type=5"
scraped: "2026-04-14"
filter: "ind.insurance_"
---# InsFormularyService:getListOfDrugs

InsFormularyService:getListOfDrugs[](https://help.salesforce.com/s?language=en_US)

You are here:

1.  [Salesforce Help](/s/?language=en_US)
2.  [Docs](/s/products?language=en_US)
3.  [Digital Insurance](https://help.salesforce.com/s/articleView?id=ind.insurance_admin_standard.htm&language=en_US&type=5)

# InsFormularyService:getListOfDrugs

Use this service to get a list of drugs within their effective marketing dates.

[](https://help.salesforce.com/s?language=en_US)

Class: `InsFormularyService`

Method: `getListOfDrugs`

[](https://help.salesforce.com/s?language=en_US)

## How It Works

1.  Goes to `Drug__c` for list of drugs.
    
2.  Uses `MarketingStartDate__c` and `MarketingEndDate__c` for effective marketing date start and end points.
    
3.  Returns list with `TradeName__c` and `GenericName__c` as per effective marketing date (`Date effectiveDate`).
    

[](https://help.salesforce.com/s?language=en_US)

## Remote Options

| 
Option

 | 

Description

 |
| --- | --- |
| 

`effectiveMarketingDate`

 | 

Required.

Marketing end and start dates for drugs, required for output list.

 |

Did this article solve your issue?

Let us know so we can improve!

YesNo