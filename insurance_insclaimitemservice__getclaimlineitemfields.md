---
title: "InsClaimItemService: getClaimLineItemFields"
source: "https://help.salesforce.com/s/articleView?id=ind.insurance_insclaimitemservice__getclaimlineitemfields.htm&language=en_US&type=5"
scraped: "2026-04-14"
filter: "ind.insurance_"
---# InsClaimItemService: getClaimLineItemFields

InsClaimItemService: getClaimLineItemFields[](https://help.salesforce.com/s?language=en_US)

You are here:

1.  [Salesforce Help](/s/?language=en_US)
2.  [Docs](/s/products?language=en_US)
3.  [Digital Insurance](https://help.salesforce.com/s/articleView?id=ind.insurance_admin_standard.htm&language=en_US&type=5)

# InsClaimItemService: getClaimLineItemFields

Use this service to retrieve the list of fields of a field set (and optionally the field's values). This field set is specific for a particular CoverageSpec.

[](https://help.salesforce.com/s?language=en_US)

Class: `InsClaimItemService`

Method: `getClaimLineItemFields`

To define a custom field set:

1.  Create a field set in the Object Manager page for ClaimCoveragePaymentDetail / ClaimLineItem\_\_c.
    
2.  Create a record in Setup → Custom Settings → Insurance Configuration Setup → Manage.
    
    -   Name = ClaimCoverage + : + <CovSpec's Product Code>. For example: ClaimCoverage:autoBIPD
        
    -   Setup Value = ClaimLineItem\_\_c / ClaimCoveragePaymentDetail fully-qualified (including namespace if any) fieldSet name.
        

[](https://help.salesforce.com/s?language=en_US)

## How It Works

1.  From the Claim Coverage Id, retrieve the PolicyCoverage's CovSpec ProductCode.
    
2.  Get the fieldSet name from the Custom Settings.
    
3.  Gets the details of each field including isRequired, dataType, label, and fieldName. Field names common between the ClaimCoveragePaymentDetail and ClaimLineItem\_\_c now use object interface fields. If not, it takes the ApiName of the field.
    
4.  For dataType=Picklist, the picklist options are included as "options."
    
5.  For benefit type, the service retrieves all the PowerAttributes' Benefit Type based on the claimId, and then lists them down as picklist options.
    
6.  On edit of the Loss item (claimItemId is passed in the option), the corresponding value of that field for the record is included in the output.
    

[](https://help.salesforce.com/s?language=en_US)

## Remote Options

| 
Option

 | 

Description

 |
| --- | --- |
| 

`claimId`

 | 

Required.

The Id of the claim for which the service gets the claim line item fields.

 |
| 

`claimCoverageId`

 | 

Required.

The Id of the claim coverage.

 |
| 

`claimItemId`

 | 

Optional.

The Id of the claim item.

 |

[](https://help.salesforce.com/s?language=en_US)

## Input JSON

Here's the format of the input JSON:

```
{ 
	"claimId": <Id>,
	"claimCoverageId": <Id>,
	"claimItemId": <Id>
}
```

Here's the sample of the input JSON:

```
{ 
	"claimId": '01t000000000000001',
	"claimCoverageId": '01t000000000000002',
	"claimItemId": '01t000000000000003'
}
```

[](https://help.salesforce.com/s?language=en_US)

## Output JSON

Here's the format of the output JSON:

```
{  
   	"isDefault": <boolean>,
	"fieldNameList": [<String>, <String>, ..,],
	"fieldList": [<JSON>, <JSON>, ...]
}
```

Here's the sample of the output JSON:

```
{
  "isDefault": false,
  "fieldList": [
    {
      "options": [
        {
          "Name": "Hospital Confinement",
          "Id": "Hospital Confinement"
        },
        {
          "Name": "Transportation",
          "Id": "Transportation"
        }
      ],
      "isNillable": true,
      "isUpdateable": true,
      "isCreatable": true,
      "isRequired": false,
      "dataType": "PICKLIST",
      "label": "Benefit Name",
      "fieldName": "benefitType"
    },
    {
      "isNillable": true,
      "isUpdateable": true,
      "isCreatable": true,
      "isRequired": false,
      "dataType": "INTEGER",
      "label": "Limit Unit Count",
      "fieldName": "unitCount"
    },
    {
      "options": [
        {
          "Id": "New",
          "Name": "New"
        },
        {
          "Id": "Open",
          "Name": "Open"
        },
        {
          "Id": "Pending Authority",
          "Name": "Pending Authority"
        },
        {
          "Id": "Authority Approved",
          "Name": "Authority Approved"
        },
        {
          "Id": "Authority Denied",
          "Name": "Authority Denied"
        },
        {
          "Id": "Payment Pending",
          "Name": "Payment Pending"
        },
        {
          "Id": "Paid",
          "Name": "Paid"
        },
        {
          "Id": "Closed W/O Pay",
          "Name": "Closed W/O Pay"
        },
        {
          "Id": "Cancelled",
          "Name": "Cancelled"
        },
        {
          "Id": "Stopped",
          "Name": "Stopped"
        }
      ],
      "isNillable": true,
      "isUpdateable": true,
      "isCreatable": true,
      "isRequired": false,
      "dataType": "PICKLIST",
      "label": "Status",
      "fieldName": "status"
    },
    {
      "options": [
        {
          "Id": "Loss",
          "Name": "Loss"
        },
        {
          "Id": "Expense",
          "Name": "Expense"
        }
      ],
      "isNillable": true,
      "isUpdateable": true,
      "isCreatable": true,
      "isRequired": false,
      "dataType": "PICKLIST",
      "label": "Type",
      "fieldName": "type"
    }
  ],
  "fieldNameList": [
    "benefitType",
    "unitCount",
    "status",
    "type"
  ]
}
```

Did this article solve your issue?

Let us know so we can improve!

YesNo