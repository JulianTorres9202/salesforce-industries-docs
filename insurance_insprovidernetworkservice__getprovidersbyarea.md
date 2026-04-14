---
title: "InsProviderNetworkService:getProvidersByArea"
source: "https://help.salesforce.com/s/articleView?id=ind.insurance_insprovidernetworkservice__getprovidersbyarea.htm&language=en_US&type=5"
scraped: "2026-04-14"
filter: "ind.insurance_"
---# InsProviderNetworkService:getProvidersByArea

InsProviderNetworkService:getProvidersByArea[](https://help.salesforce.com/s?language=en_US)

You are here:

1.  [Salesforce Help](/s/?language=en_US)
2.  [Docs](/s/products?language=en_US)
3.  [Digital Insurance](https://help.salesforce.com/s/articleView?id=ind.insurance_admin_standard.htm&language=en_US&type=5)

# InsProviderNetworkService:getProvidersByArea

Use this service to get all providers and their networks for a given geographical location. This service returns both individual and organizational providers along with the networks they are a member of, by using `state` and `postalCode` as inputs.

[](https://help.salesforce.com/s?language=en_US)

Class: `InsProviderNetworkService`

Method: `getProvidersByArea`

[](https://help.salesforce.com/s?language=en_US)

## How It Works

1.  The service takes the `state` and `postalCode` inputs where the search matches state = MailingState (from the Mailing Address field) and postalCode= MailingPostalCode (from the Mailing Address field) for Contacts (such as Individual Providers).
    
    However, for Accounts, the search matches state = BillingState (from the Billing Address field) and postalCode= BillingPostalCode (from the Billing Address field) for Accounts (such as Organizational Providers ).
    
    The search returns all Account records with RecordType = `Provider Location` or `Provider`, and all Contacts records with RecordType = `Provider`.
    
2.  Finds all current and active Network Memberships from `ProviderNetworkMember__c`, for the Providers identified in Step 1.
    
3.  Retrieves all Provider Networks that are currently active and referenced by the Network Memberships identified in the previous step.
    
4.  Finally, the service returns the count of Individual Providers (i.e. Contacts) and Organizational Providers (i.e. Accounts) and a list for each of them in the output JSON. The organizational providers are output in the Group Providers node.
    

[](https://help.salesforce.com/s?language=en_US)

## Inputs

| 
Option

 | 

Description

 |
| --- | --- |
| 

`state`

 | 

Required.

U.S. state where provider is located.

 |
| 

`postalCode`

 | 

Required.

Postal Code where the provider is located.

 |

[](https://help.salesforce.com/s?language=en_US)

## Input JSON

Here's a sample input JSON, using `postalCode` and `state` inputs.

```
{
  "ContextId": "",
  "timeStamp": "2020-03-25T06:59:52.230Z",
  "userId": "0056g000003cVLZAA2",
  "userName": "ins-test09@vlocity.com",
  "userProfile": "System Administrator",
  "userTimeZone": -420,
  "userCurrencyCode": "USD",
  "sfdcIFrameOrigin": "https://ins-test09-dev-ed--instest09.visualforce.com",
  "sfdcIFrameHost": "web",
  "layout": "lightning",
  "isdtp": "p1",
  "id": "a236g000000NAiWAAW",
  "vlcPersistentComponent": {},
  "postalCode": 90000,
  "state": "CA"
}
```

[](https://help.salesforce.com/s?language=en_US)

## Output JSON

This sample JSON output shows a list of Contacts with their lists of Provider Networks, and another list of Accounts and their list of Provider Networks.

```
{
  "postalCode": 90000,
  "state": "CA",
  "ContextId": "",
  "timeStamp": "2020-04-02T01:10:21.666Z",
  "userId": "0053j000009zQLnAAM",
  "userName": "jl@vlocity.com",
  "userProfile": "System Administrator",
  "userTimeZone": -420,
  "userCurrencyCode": "USD",
  "sfdcIFrameOrigin": "https://jireh-dev-ed--jireh.visualforce.com",
  "sfdcIFrameHost": "web",
  "layout": "lightning",
  "isdtp": "p1",
  "id": "a223j00000GCmWIAA1",
  "vlcPersistentComponent": {},
  "Group Providers Count": 1,
  "Group Providers": [
    {
      "Provider Networks": [
        {
          "jireh__LocationDependent__c": false,
          "jireh__LineofBusiness__c": null,
          "Name": "Network 1",
          "jireh__EffectiveStartDate__c": "2020-04-01",
          "jireh__IsActive__c": true,
          "Id": "a543j000000sXVRAA2"
        },
        {
          "jireh__LocationDependent__c": false,
          "jireh__LineofBusiness__c": null,
          "Name": "Network 2",
          "jireh__EffectiveStartDate__c": "2020-04-01",
          "jireh__IsActive__c": true,
          "Id": "a543j000000sXVRAA2"
        }
      ],
      "RecordTypeId": "0123j000001MWKBAA4",
      "jireh__CalculatedAddress__c": "<br>None CA 90000",
      "Id": "0013j00002mVO47AAG",
      "BillingCountry": "USA",
      "BillingPostalCode": "90000",
      "BillingState": "CA",
      "BillingCity": "None",
      "BillingStreet": null,
      "Industry": null,
      "jireh__PrimaryContactId__c": null,
      "Name": "Acc Test"
    }
  ],
  "Individual Providers Count": 3,
  "Individual Providers": [
    {
      "Provider Networks": [
        {
          "jireh__LocationDependent__c": false,
          "jireh__LineofBusiness__c": null,
          "Name": "Network 1",
          "jireh__EffectiveStartDate__c": "2020-04-01",
          "jireh__IsActive__c": true,
          "Id": "a543j000000sXVRAA2"
        }
      ],
      "FirstName": "Test",
      "Id": "0033j00003UCJlIAAX",
      "LastName": "Test",
      "Email": null,
      "AccountId": null
    },
    {
      "FirstName": "Test 2",
      "Id": "0033j00003UCLtWAAX",
      "LastName": "Test 2",
      "Email": null,
      "AccountId": null
    },
    {
      "Provider Networks": [
        {
          "jireh__LocationDependent__c": false,
          "jireh__LineofBusiness__c": null,
          "Name": "Network 1",
          "jireh__EffectiveStartDate__c": "2020-04-01",
          "jireh__IsActive__c": true,
          "Id": "a543j000000sXVRAA2"
        }
      ],
      "FirstName": "Test 3",
      "Id": "0033j00003UCLtXAAX",
      "LastName": "Test 3",
      "Email": null,
      "AccountId": null
    }
  ],
  "error": "OK"
}
```

Did this article solve your issue?

Let us know so we can improve!

YesNo