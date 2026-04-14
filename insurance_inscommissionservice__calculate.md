---
title: "InsCommissionService:calculate"
source: "https://help.salesforce.com/s/articleView?id=ind.insurance_inscommissionservice__calculate.htm&language=en_US&type=5"
scraped: "2026-04-14"
filter: "ind.insurance_"
---# InsCommissionService:calculate

InsCommissionService:calculate[](https://help.salesforce.com/s?language=en_US)

You are here:

1.  [Salesforce Help](/s/?language=en_US)
2.  [Docs](/s/products?language=en_US)
3.  [Digital Insurance](https://help.salesforce.com/s/articleView?id=ind.insurance_admin_standard.htm&language=en_US&type=5)

# InsCommissionService:calculate

Use this service to calculate the commission for a producer.

[](https://help.salesforce.com/s?language=en_US)

Class: `InsCommissionService`

Method: `calculate`

[](https://help.salesforce.com/s?language=en_US)

## Description

This service uses details about the producer, the insurance product, and the commissionable event to calculate a commission for a producer.

[](https://help.salesforce.com/s?language=en_US)

## How It Works

To calculate a commission, this service:

[](https://help.salesforce.com/s?language=en_US)

1.  Accepts `productionCode`, `producerId`, `productId`, `commissionableEvent`, `context`, and `effectiveDate` inputs to find the appropriate `CommissionSchedule` to use for the calculation.
    
2.  [](https://help.salesforce.com/s?language=en_US)
    
    Calculates the commission based on the Commission Schedule.
    
3.  [](https://help.salesforce.com/s?language=en_US)
    
    Evaluates the commission to determine whether it's a chargeback (a returned commission amount).
    
    -   If the commissionable amount is negative, the service treats the commission as a chargeback.
        
    -   If the commission isn't a chargeback, the service compares the calculated commission amount to minimum and maximum commission amounts. If the calculated amount it too low or too high, the service returns the minimum or maximum amount instead of the calculated amount.
        
4.  [](https://help.salesforce.com/s?language=en_US)
    
    Returns the commission amount, the ID of the commission schedule used to calculate it, and the minimum and maximum amounts that apply to this commission.
    

[](https://help.salesforce.com/s?language=en_US)

## Inputs

| 
Input

 | 

Description

 |
| --- | --- |
| 

`productionCode`

 | 

Optional.

The production code name, not the ID, for the processing producer.

 |
| 

`producerId`

 | 

Optional.

The ID of the processing producer.

 |
| 

`productId`

 | 

Required.

The ID of the product for which the commission is paid.

 |
| 

`commissionableEvent`

 | 

[](https://help.salesforce.com/s?language=en_US)Optional.

The event or transaction that triggers a commission calculation (for example, Quote, Sold Policy, or Changed/Endorsed).

 |
| 

`effectiveDate`

 | 

Optional.

The effective date of the commission payment. If null, the service uses today's date.

 |
| 

`context`

 | 

Required.

Field name and value pairs for the record on which commission is calculated. You must:

-   Include a namespace in the API name if one exists.
    
-   Include `objectId`, that is, the ID of the record for which the commission is calculated.
    

Format without lookup field:

`{ objectAPI.fieldAPI : fieldValue }`

Format with lookup field:

`{ objectAPI.relationshipAPI.fieldAPI : fieldValue }`

You can specify up to two levels of fields if you format the input with a lookup field.

 |
| 

`commissionableAmount`

 | 

[](https://help.salesforce.com/s?language=en_US)Optional.

The amount on which the commission calculation is based.

 |

[](https://help.salesforce.com/s?language=en_US)

## Input JSON

Here's how to format input JSON.

```json
{
   "productionCode": ProductionCode.Name,
   "producerId": Producer.Id,
   "product2Id": Product2.Id,
   "commissionableEvent": event type,
   "commissionableAmount": amount of the transaction,
   "context": {
      "objectId": ID of applicable object used,
	  "objectAPI.fieldAPI" : value
   }
}
```

This sample calculates a commission for an endorsement.

```json
{
   "productionCode":AX001,
   "producerId":ay001jh002,
   "product2Id":az011jh022,
   "commissionableEvent":"Endorsement",
   "commissionableAmount":500,
   "context":{
      "Quote.vlocity_ins__TotalPremiumforTerm__c":100,
      "QuoteLineItem.vlocity_ins__GroupClassId__r.vlocity_ins__ClassCode__c":"Managers",
      "QuoteLineItem.vlocity_ins__FeeAmount__c":5,
      "objectId":ax003jh001
   }
}
```

[](https://help.salesforce.com/s?language=en_US)

## Output JSON

Here's the format of output JSON.

```
{
   "commissionAmount": amount,
   "commissionScheduleId": ID of the commission schedule used,
   "minCommissionAmount": CommissionScheduleAssignment.MinCommissionAmount,
   "maxCommissionAmount": CommissionScheduleAssignment.MaxCommissionAmount
}
```

Here's sample output that shows the calculated amount ($167) is within the range defined by minimum and maximum values ($100-$500).

```
{
   "commissionAmount":167,
   "commissionScheduleId":"ab001od002",
   "minCommissionAmount":100,
   "maxCommissionAmount":500
}
```

Did this article solve your issue?

Let us know so we can improve!

YesNo