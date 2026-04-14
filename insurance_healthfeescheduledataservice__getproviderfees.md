---
title: "HealthFeeScheduleDataService:getProviderFees"
source: "https://help.salesforce.com/s/articleView?id=ind.insurance_healthfeescheduledataservice__getproviderfees.htm&language=en_US&type=5"
scraped: "2026-04-14"
filter: "ind.insurance_"
---# HealthFeeScheduleDataService:getProviderFees

HealthFeeScheduleDataService:getProviderFees[](https://help.salesforce.com/s?language=en_US)

You are here:

1.  [Salesforce Help](/s/?language=en_US)
2.  [Docs](/s/products?language=en_US)
3.  [Digital Insurance](https://help.salesforce.com/s/articleView?id=ind.insurance_admin_standard.htm&language=en_US&type=5)

# HealthFeeScheduleDataService:getProviderFees

Use this service to retrieve data from the given provider fee schedule and use the supplied date to determine the appropriate base fee schedule version.

Class: `HealthFeeScheduleDataService`

Method: `getProviderFees`

Important This service is retired from Vlocity Health and Insurance Spring '22 release and onward.

[](https://help.salesforce.com/s?language=en_US)

## How It Works

1.  The service takes a `providerFeeSchedId`, determines which `FeeSchedule__c` it is associated with, and what the currently active version of that `FeeSchedule__c` is for a given date. 
    
2.  Services uses the `executionDateTime`t option as the given date. If `executionDateTime` has no value, the service uses the current date.
    
3.  The service then retrieves the list of base fees from the `FeeSchedule__c`. If offset has value, the next 2,000 rows after the specified offset will be returned. Otherwise, the first 2,000 rows will be returned.
    
4.  The list of `ProviderFeeScheduleEntry__c` for the given `providerFeeSchedId` is retrieved.
    
5.  Service then computes the provider fees in one of two ways:
    
    -   If the base fee has a matching entry in the `ProviderFeeScheduleEntry__c`, the service looks at `FeeType_c` along with Additional Amount and Rate Factor. The value of `AdditionalAmount__c` is added to the base fee. The value of `RateFactor__c` is multiplied to the base fee and divided by 100.
        
    -   If the base fee has no matching entry in the `ProviderFeeScheduleEntry__c`, the provider fee is the same as the base fee.
        

[](https://help.salesforce.com/s?language=en_US)

## Remote Options

| 
Option

 | 

Description

 |
| --- | --- |
| 

`providerFeeSchedId`

 | 

Required

Id of the provider fee schedule.

 |
| 

`executionDateTime`

 | 

Optional

Date specified determines which enabled version of the schedule is selected.

Format: `DD/MM/YYYY`

 |
| 

`retrieveOptions`

 | 

Optional

Key value pair.

offset: <_value_\>

where _value_ = fee schedule column that has the procedure code column mapping type applied to it.

Used to determine where the returned rows of procedure codes will start.

With no value, service returns the first 2,000 values from the base fee schedule.

If a value is provided, the next 2,000 rows after the procedure code value (that is to say, below it) are returned. The rows before/above the value are not returned. In any case, only 2,000 rows are returned.

Important Returned data sorting order is presently based on ascending procedure code hash values, not by procedure code. For example, procedure code ABC with hash value 789 would come after procedure code DEF with hash value 456.





 |

[](https://help.salesforce.com/s?language=en_US)

## Input JSON

The following sample input JSON shows the inputs the service uses:

```
{ 
   "providerFeeSchedId":"a444P000001H44GQAS",
   "executionDateTime":11/25/2019,
   "retrieveOptions":{ 
      "offset":"99215"
   }
}
```

[](https://help.salesforce.com/s?language=en_US)

## Output JSON

The service returns an output JSON of base fee schedule data, based on the `providerFeeSchedId` and options provided:

```
{ 
   "providerFees":[ 
      { 
         "Provider-Non-Facility Price":0.05,
         "Provider-Facility Price":0.05,
         "Description":"99215",
         "Facility Price":1,
         "Non-Facility Price":1,
         "Procedure Code":"99215",
         "deleted":false,
         "versionEnabled":true,
         "versionId":"a1I6F00000nM7LxUAK",
         "Name":"9952ac9010c8edba8ee0f2b4e80793e0",
         "vLineItemId":"a1H6F000006SvT8UAK"
      },
      { 
         "Provider-Non-Facility Price":2,
         "Provider-Facility Price":2,
         "Description":"99214",
         "Facility Price":1,
         "Non-Facility Price":1,
         "Procedure Code":"99214",
         "deleted":false,
         "versionEnabled":true,
         "versionId":"a1I6F00000nM7LxUAK",
         "Name":"f88f1140bdd063cfc2ce8652abb6f581",
         "vLineItemId":"a1H6F000006SvT9UAK"
      }
   ],
   "error":"OK"
}
```

Did this article solve your issue?

Let us know so we can improve!

YesNo