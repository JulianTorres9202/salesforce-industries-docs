---
title: "InsProviderNetworkService:getProvidersDetail"
source: "https://help.salesforce.com/s/articleView?id=ind.insurance_insprovidernetworkservice__getprovidersdetail.htm&language=en_US&type=5"
scraped: "2026-04-14"
filter: "ind.insurance_"
---# InsProviderNetworkService:getProvidersDetail

InsProviderNetworkService:getProvidersDetail[](https://help.salesforce.com/s?language=en_US)

You are here:

1.  [Salesforce Help](/s/?language=en_US)
2.  [Docs](/s/products?language=en_US)
3.  [Digital Insurance](https://help.salesforce.com/s/articleView?id=ind.insurance_admin_standard.htm&language=en_US&type=5)

# InsProviderNetworkService:getProvidersDetail

This service allows you to retrieve Provider information, including group affiliations and locations.

[](https://help.salesforce.com/s?language=en_US)

Class:`InsProviderNetworkService`

Method:`getProvidersDetail`

[](https://help.salesforce.com/s?language=en_US)

## How It Works

1.  Using the Id, the service searches for the Provider record (Contact) using constructed SOQL with a number of inner queries, including related records.
    
2.  If fieldSetName is set as part of input, its fields as used for Provider details.
    
3.  If no fieldset is provided in the input, the following default set of fields will be included in the Provider details (Contact):
    
    -   Id
        
    -   FirstName
        
    -   LastName
        
    -   Email
        
    -   Phone
        
    -   Fax
        
    -   ProviderIdentifier\_\_c
        
    -   Has24x7Service\_\_c
        
    -   MailingStreet
        
    -   MailingCity
        
    -   MailingState
        
    -   MailingPostalCode
        
    -   MailingCountry
        
4.  The result includes AccountContactRelations (Provider Location and Provider Group) with the following fields:
    
    -   AccountId
        
    -   Account.Name
        
    -   Account.RecordTypeId
        
    -   Account.BillingStreet
        
    -   Account.BillingCity
        
    -   Account.BillingState
        
    -   Account.BillingPostalCode
        
    -   Account.BillingCountry
        
    -   IsPrimaryRelationship\_\_c
        
    -   OperatingHoursId\_\_c
        
5.  The resulting data in the form of a Contact object instance is deserialized and parsed to Map <_String_, _Object_\> and returned as part of an output JSON in the `result` node.
    

[](https://help.salesforce.com/s?language=en_US)

## User Inputs

| 
Input

 | 

Description

 |
| --- | --- |
| 

`id`

 | 

Provider record ID

 |
| 

`fieldSetName`

 | 

Contact object fieldset name

 |

[](https://help.salesforce.com/s?language=en_US)

## Input JSON

JSON input is formatted like this:

```json
{
  "Id": <Contact Id>,
  "fieldSetName": <Contact object fieldset>
}
```

Sample JSON input with data:

```json
{
  "Id": "0035w0000396WMzAAM",
  "fieldSetName": "ProviderFieldSet"
}
```

[](https://help.salesforce.com/s?language=en_US)

## Output JSON

JSON output is formatted like this:

```json
{
  "fieldSetName": <COntact fieldset used during service call>,
  "Id": <Provider/Contact record ID used during service call>,
  "result": {
    "RecordTypeId": <Contact Record Type>,
    "Id": <Contact record ID>,
    "Field 1": <Contact object field value>,
    "Field 2": <Contact object field value>,
    "AccountContactRelations": {
      "records": [
        {
          "Account": {
            "Id": <Account record ID>,
            "BillingCountry": <Account.BillingCountry value>,
            "BillingCity": <Account.BillingCity value>,
            "RecordTypeId": <Account Record Type>,
            "Name": <Account.Name value>
          },
          "IsPrimaryRelationship__c": <Primary relationship indicator>,
          "AccountId": <Account record ID>,
          "Id": <AccountContactRelation record ID>,
          "ContactId": <Contact record ID>
        }
      "done": true,
      "totalSize": <AccountContactRelations count>
    }
  },
  "error": "OK"
}
```

Sample JSON output with data.

```json
{
  "fieldSetName": "ProviderFieldSet",
  "Id": "0035w0000396WMzAAM",
  "result": {
    "RecordTypeId": "0125w000001FVCuAAO",
    "Id": "0035w0000396WMzAAM",
    "Email": "lesliejohann@email.com",
    "Name": "Leslie Johann",
    "AccountContactRelations": {
      "records": [
        {
          "Account": {
            "Id": "0015w00002EiEyNAAV",
            "BillingCountry": "Germany",
            "BillingCity": "Berlin",
            "RecordTypeId": "0125w000001FVChAAO",
            "Name": "Berlin Facility (Location)"
          },
          "IsPrimaryRelationship__c": false,
          "AccountId": "0015w00002EiEyNAAV",
          "Id": "07k5w00000JPRM0AAP",
          "ContactId": "0035w0000396WMzAAM"
        },
        {
          "Account": {
            "Id": "0015w00002EiF2KAAV",
            "RecordTypeId": "0125w000001FVCgAAO",
            "Name": "First EU Medical Group"
          },
          "IsPrimaryRelationship__c": false,
          "AccountId": "0015w00002EiF2KAAV",
          "Id": "07k5w00000JPRMFAA5",
          "ContactId": "0035w0000396WMzAAM"
        }
      ],
      "done": true,
      "totalSize": 2
    }
  },
  "error": "OK"
}
```

Did this article solve your issue?

Let us know so we can improve!

YesNo