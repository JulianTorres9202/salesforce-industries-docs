---
title: "InsCensusServiceStd:getFields"
source: "https://help.salesforce.com/s/articleView?id=ind.insurance_inscensusservicestd__getfields.htm&language=en_US&type=5"
scraped: "2026-04-14"
filter: "ind.insurance_"
---# InsCensusServiceStd:getFields

InsCensusServiceStd:getFields[](https://help.salesforce.com/s?language=en_US)

You are here:

1.  [Salesforce Help](/s/?language=en_US)
2.  [Docs](/s/products?language=en_US)
3.  [Digital Insurance](https://help.salesforce.com/s/articleView?id=ind.insurance_admin_standard.htm&language=en_US&type=5)

# InsCensusServiceStd:getFields

Use this service to retrieve field definitions and field API names for group census members and group census member plans.

Class: `​InsCensusServiceStd​​`

Method: `getFields`

[](https://help.salesforce.com/s?language=en_US)

## How It Works

1.  The service retrieves the list of ​​`GroupCensusMember`​​ fields that are part of the fieldset passed in the input parameter `fieldsetName`.
2.  If ​`withPlans`​​ parameter is true, the service also retrieves the list of ​`GroupCensusMemberPlan​​` fields.
    
3.  The list of field definitions (field data types, field labels, field API names, and field .csv headers) is combined to form the ​​`headers`​​.
    
    -   If `​​GroupClassId`​​ is included in the retrieved list of fields, the service adds a node under the headers - ​`GroupClassId.Name​`.
        
4.  The list of field API names is combined to form the ​​JSON node.
    
    -   If ​​`GroupClassId`​ is included in the retrieved list of fields, the service adds a node under the fields - ​`GroupClassId.Name`​​.
        

[](https://help.salesforce.com/s?language=en_US)

## Remote Options

| 
Option

 | 

Description

 |
| --- | --- |
| 

`fieldsetName`

 | 

Retrieves ​`GroupCensusMember​​` fields that are part of the specified field set.

If the input doesn't match with existing field set, the service returns an error - "The specified field set name <fieldsetName> doesn't exist."

If the user doesn't specify a value, the service uses the default field set - `StandardFieldset`.

 |
| 

`planFieldsetName`

 | 

Retrieves ​`GroupCensusMemberPlan`​​ fields that are part of the field set for any valid values.

If the input doesn't match with existing field set, the service returns an error - "The specified field set name <planFieldsetName> doesn't exist."

If the user doesn't specify a value, the service returns all `GroupCensusMemberPlan` fields.

 |
| 

`withPlans`

 | 

Boolean

If `true`, the service includes fields from `GroupCensusMemberPlan`.

The default value is `false`.

 |

## Input JSON

Here's the sample input JSON:

```json
{
    "fieldsetName": "memberFields",
    "withPlans": true,
    "planFieldsetName": "planFields"
}
```

[](https://help.salesforce.com/s?language=en_US)

## Output JSON

The service returns a list of all the field API names that are part of the field set `myFieldsetName` in `GroupCensusMember` object. If `withPlans` parameter is true, the output also includes field API names that are part of the field set `myPlanFieldsetName` in `GroupCensusMemberPlan` object.

Headers consist of a list of field API names, field labels, field data type, and field CSV header for all the fields retrieved by the service.

The service returns an output JSON formatted as per this example:

```json
{
  "fields": [
    "vlocityins__AttributeSelectedValues__c",
    "AccountId",
    "Gender",
    "ContractGroupPlanId",
  ],
  "headers": [
    {
      "fieldId": "",
      "type": "StringPlusClob",
      "label": "Attribute Selected Values",
      "name": "vlocityins__AttributeSelectedValues__c"
    },
    {
      "fieldId": "",
      "type": "EntityId",
      "label": "Account ID",
      "name": "AccountId"
    },
    {
      "fieldId": "",
      "type": "DynamicEnum",
      "label": "Gender",
	  "name": "Gender"
      "options": [
        {
          "label": "Male",
          "name": "Male"
        },
        {
          "label": "Female",
          "name": "Female"
        }
      ],
    },
    {
      "fieldId": "",
      "type": "EntityId",
      "label": "Contract Group Plan ID",
      "name": "ContractGroupPlanId",
   	  "options":[ 
           { 
              "value":"a2N4P000006ygEiUAI",
              "type":"Medical",
              "name":"rootProd",
			  "childProducts": [
				{
					"value": "0rgDC000000000RYAQ",
					"IsOptional": false,
					"name": "MandatoryCoverage"
				},
			 	{
					"value": "0rgDC000000000RYBQ",
					"IsOptional": true,
					"name": "OptionalCoverage"
				}
			  ]
           },
           { 
              "value":"a2N4P000006ygEjUAI",
              "type":"Dental",
              "name":"rootProd2",
			  "childProducts": [
				{
					"value": "0rgDC000000000RYCQ",
					"IsOptional": false,
					"name": "MandatoryCoverage"
				},
			 	{
					"value": "0rgDC000000000RYDQ",
					"IsOptional": true,
					"name": "OptionalCoverage"
				}
			  ]
           }
      ]
    }
  ]
} 
``` 

Did this article solve your issue?

Let us know so we can improve!

YesNo