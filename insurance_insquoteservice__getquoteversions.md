---
title: "InsQuoteService:getQuoteVersions"
source: "https://help.salesforce.com/s/articleView?id=ind.insurance_insquoteservice__getquoteversions.htm&language=en_US&type=5"
scraped: "2026-04-14"
filter: "ind.insurance_"
---# InsQuoteService:getQuoteVersions

InsQuoteService:getQuoteVersions[](https://help.salesforce.com/s?language=en_US)

You are here:

1.  [Salesforce Help](/s/?language=en_US)
2.  [Docs](/s/products?language=en_US)
3.  [Digital Insurance](https://help.salesforce.com/s/articleView?id=ind.insurance_admin_standard.htm&language=en_US&type=5)

# InsQuoteService:getQuoteVersions

Use this service to retrieve different versions of a quote based on its Opportunity Id, and then return a list of quotes based on the Quote field set **QuoteCompareHeader**.

[](https://help.salesforce.com/s?language=en_US)

[](https://help.salesforce.com/s?language=en_US)Note

This service isn't supported for guest users.

If a guest user tries to run an OmniScript or Integration Procedure or UI function that uses this service, the service will not run and the guest user will see an error message.

[](https://help.salesforce.com/s?language=en_US)

Class: `InsQuoteService`

Method: `getQuoteVersions`

[](https://help.salesforce.com/s?language=en_US)

## How It Works

1.  The service receives the **quoteId** as input.
    
2.  The service queries for other quotes that share the same Opportunity Id.
    
3.  The service returns a list of quotes.
    

[](https://help.salesforce.com/s?language=en_US)

## Remote Options

| 
Option

 | 

Description

 |
| --- | --- |
| 

**quoteId**

 | 

Id of the quote used to retrieve other versions

 |
| 

**activeQuotesOnly**

 | 

Optional

The default is false. If true, adds additional conditions to the quote query to retrieve only quotes that are currently active (for example, the current date that is between the Effective date and End date of the quote).

 |
| 

**includeFieldInfo**

 | 

Optional

The default is true. If true, includes the quote field information used by the UI.

 |

[](https://help.salesforce.com/s?language=en_US)

## Input JSON

See the following example of input JSON.

```
{
  "quoteId":"0Q06g0000009YA3CAM"
}
```

[](https://help.salesforce.com/s?language=en_US)

## Output JSON

See the following example of output JSON.

```
{
  "fieldInfo": {
    "instest10__EndDate__c": {
      "isUpdateable": true,
      "isCreatable": true,
      "isRequired": false,
      "fieldType": "DATE",
      "fieldLabel": "End Date",
      "fieldName": "instest10__EndDate__c"
    },
    "instest10__EffectiveDate__c": {
      "isUpdateable": true,
      "isCreatable": true,
      "isRequired": false,
      "fieldType": "DATE",
      "fieldLabel": "Effective Date",
      "fieldName": "instest10__EffectiveDate__c"
    },
    "instest10__Type__c": {
      "options": [
        {
          "Id": "New Business",
          "Name": "New Business"
        },
        {
          "Id": "Endorsement",
          "Name": "Endorsement"
        }
      ],
      "isUpdateable": true,
      "isCreatable": true,
      "isRequired": false,
      "fieldType": "PICKLIST",
      "fieldLabel": "Type",
      "fieldName": "instest10__Type__c"
    },
    "Name": {
      "isUpdateable": true,
      "isCreatable": true,
      "isRequired": false,
      "fieldType": "STRING",
      "fieldLabel": "Quote Name",
      "fieldName": "Name"
    },
    "Id": {
      "isUpdateable": false,
      "isCreatable": false,
      "isRequired": false,
      "fieldType": "ID",
      "fieldLabel": "Quote ID",
      "fieldName": "Id"
    },
    "Status": {
      "options": [
        {
          "Id": "Draft",
          "Name": "Draft"
        },
        {
          "Id": "Needs Review",
          "Name": "Needs Review"
        },
        {
          "Id": "In Review",
          "Name": "In Review"
        },
        {
          "Id": "Approved",
          "Name": "Approved"
        },
        {
          "Id": "Rejected",
          "Name": "Rejected"
        },
        {
          "Id": "Presented",
          "Name": "Presented"
        },
        {
          "Id": "Accepted",
          "Name": "Accepted"
        },
        {
          "Id": "Denied",
          "Name": "Denied"
        },
        {
          "Id": "Issued",
          "Name": "Issued"
        }
      ],
      "isUpdateable": true,
      "isCreatable": true,
      "isRequired": false,
      "fieldType": "PICKLIST",
      "fieldLabel": "Status",
      "fieldName": "Status"
    },
    "CreatedDate": {
      "isUpdateable": false,
      "isCreatable": false,
      "isRequired": false,
      "fieldType": "DATETIME",
      "fieldLabel": "Created Date",
      "fieldName": "CreatedDate"
    },
    "instest10__RootItemTotal__c": {
      "isUpdateable": false,
      "isCreatable": false,
      "isRequired": false,
      "fieldType": "CURRENCY",
      "fieldLabel": "Total Price",
      "fieldName": "instest10__RootItemTotal__c"
    }
  },
  "quotesToCompare": [
    {
      "attributes": {
        "type": "Quote",
        "url": "/services/data/v48.0/sobjects/Quote/0Q06g0000009yAWCAY"
      },
      "instest10__RootItemTotal__c": 2740,
      "CreatedDate": "2020-04-01T20:35:57.000+0000",
      "Status": "Draft",
      "Id": "0Q06g0000009yAWCAY",
      "Name": "Alan6 Auto Quote New Version",
      "instest10__Type__c": "New Business",
      "instest10__EffectiveDate__c": "2020-05-01",
      "instest10__EndDate__c": "2021-04-30"
    },
    {
      "attributes": {
        "type": "Quote",
        "url": "/services/data/v48.0/sobjects/Quote/0Q06g0000009yAHCAY"
      },
      "instest10__RootItemTotal__c": 1575,
      "CreatedDate": "2020-04-01T18:53:26.000+0000",
      "Status": "Issued",
      "Id": "0Q06g0000009yAHCAY",
      "Name": "Alan6 Auto Quote",
      "instest10__Type__c": "New Business",
      "instest10__EffectiveDate__c": "2020-04-01",
      "instest10__EndDate__c": "2021-03-31"
    }
  ],
  "errorCode": "INVOKE-200",
  "error": "OK"
}
```

[](https://help.salesforce.com/s?language=en_US)

## Results Description

**fieldInfo** Information about the fields in the quote

**quotesToCompare** The list of quotes for comparison

Did this article solve your issue?

Let us know so we can improve!

YesNo