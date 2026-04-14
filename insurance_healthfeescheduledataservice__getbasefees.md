---
title: "HealthFeeScheduleDataService:getBaseFees"
source: "https://help.salesforce.com/s/articleView?id=ind.insurance_healthfeescheduledataservice__getbasefees.htm&language=en_US&type=5"
scraped: "2026-04-14"
filter: "ind.insurance_"
---# HealthFeeScheduleDataService:getBaseFees

HealthFeeScheduleDataService:getBaseFees[](https://help.salesforce.com/s?language=en_US)

You are here:

1.  [Salesforce Help](/s/?language=en_US)
2.  [Docs](/s/products?language=en_US)
3.  [Digital Insurance](https://help.salesforce.com/s/articleView?id=ind.insurance_admin_standard.htm&language=en_US&type=5)

# HealthFeeScheduleDataService:getBaseFees

Use this service to retrieve the currently active base fee schedule data—Description, Facility Price, and Non-Facility Price, and so forth—based on the date specified.

Class: `HealthFeeScheduleDataService`

Method: `getBaseFees`

Important This service is retired from Vlocity Health and Insurance Spring '22 release and onward.

[](https://help.salesforce.com/s?language=en_US)

## How It Works

1.  Service uses the `feeSchedId` to determine the currently active version of the `FeeSchedule__c` for a given date. If more than one version satisfies the given date, data from the most recent version is returned.
    
2.  Service uses the `executionDateTime`t option as the given date. If `executionDateTime` has no value, service uses the current date.
    

[](https://help.salesforce.com/s?language=en_US)

## Remote Options

| 
Option

 | 

Description

 |
| --- | --- |
| 

`feeSchedId`

 | 

Required.

Id of the fee schedule.

 |
| 

`executionDateTime`

 | 

Optional.

Date specified determines which enabled version of the schedule is selected.

Format: `DD/MM/YYYY`

 |
| 

`retrieveOptions`

 | 

Optional.

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

This following JSON example shows the inputs the service uses:

```
{ 
   "feeSchedId":"a444P000001H44GQAS",
   "executionDateTime":11/25/2019,
   "retrieveOptions":{ 
      "offset":"99215"
   }
}
```

[](https://help.salesforce.com/s?language=en_US)

## Output JSON

The service returns an output JSON of base fee schedule data, based on the `feeSchedId` and options provided:

```
{ 
   "baseFees":[ 
      { 
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