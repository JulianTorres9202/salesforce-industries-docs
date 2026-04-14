---
title: "InsProviderNetworkService:getProvidersByNameOrNPI"
source: "https://help.salesforce.com/s/articleView?id=ind.insurance_insprovidernetworkservice__getprovidersbynameornpi.htm&language=en_US&type=5"
scraped: "2026-04-14"
filter: "ind.insurance_"
---# InsProviderNetworkService:getProvidersByNameOrNPI

InsProviderNetworkService:getProvidersByNameOrNPI[](https://help.salesforce.com/s?language=en_US)

You are here:

1.  [Salesforce Help](/s/?language=en_US)
2.  [Docs](/s/products?language=en_US)
3.  [Digital Insurance](https://help.salesforce.com/s/articleView?id=ind.insurance_admin_standard.htm&language=en_US&type=5)

# InsProviderNetworkService:getProvidersByNameOrNPI

Use this service to allow users to search for Providers using a search key.

[](https://help.salesforce.com/s?language=en_US)

Class:`InsProviderNetworkService`

Method:`getProvidersByNameOrNPI`

[](https://help.salesforce.com/s?language=en_US)

## How It Works

1.  The service retrieves Provider records where the Firstname, Lastname, or NPI (ProviderIdentifier\_\_c) starts with the `searchKey`.
    
2.  The resulting list is returned as part of the output JSON in the result node.
    

[](https://help.salesforce.com/s?language=en_US)

## User Inputs

| 
Input

 | 

Description

 |
| --- | --- |
| 

`searchKey`

 | 

String

Used to check against FirstName, LastName, or Provider NPI.

 |

[](https://help.salesforce.com/s?language=en_US)

## Input JSON

JSON input is formatted like this:

```json
{
  "searchKey": <search string>
}
```

Sample JSON input with data:

```json
{
  "searchKey": "John"
}
```

[](https://help.salesforce.com/s?language=en_US)

## Output JSON

JSON output is formatted like this:

```json
{
  "searchKey": <search string>,
  "result": [
    {
      "Name": <Contact.name field value>,
      "FirstName": <Contact.FirstName field value>,
      "LastName": <Contact.LastName field value>,
      "ProviderIdentifier__c": <Contact.ProviderIdentifier__c field value>,
      "Id": <Contact record ID>,
      "RecordTypeId": <Contact Record Type>
    }
  ],
  "error": "OK"
}
```

Sample JSON output with data, with `searchKey` Joh. Notice how John and Johann are returned in the result.

```json
{
  "searchKey": "Joh",
  "result": [
    {
      "Name": "John Smith",
      "FirstName": "John",
      "LastName": "Smith",
      "ProviderIdentifier__c": "DE0049",
      "Id": "0035w0000396WMzAAM",
      "RecordTypeId": "0125w000001FVCuAAO"
    },
    {
      "Name": "Leslie Johann",
      "FirstName": "Leslie",
      "LastName": "Johann",
      "Id": "0035w00003976D2AAI",
      "RecordTypeId": "0125w000001FVCuAAO"
    },
  ],
  "error": "OK"
}
```

Did this article solve your issue?

Let us know so we can improve!

YesNo