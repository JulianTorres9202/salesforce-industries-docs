---
title: "InsFormularyService:getProducts"
source: "https://help.salesforce.com/s/articleView?id=ind.insurance_insformularyservice__getproducts.htm&language=en_US&type=5"
scraped: "2026-04-14"
filter: "ind.insurance_"
---# InsFormularyService:getProducts

InsFormularyService:getProducts[](https://help.salesforce.com/s?language=en_US)

You are here:

1.  [Salesforce Help](/s/?language=en_US)
2.  [Docs](/s/products?language=en_US)
3.  [Digital Insurance](https://help.salesforce.com/s/articleView?id=ind.insurance_admin_standard.htm&language=en_US&type=5)

# InsFormularyService:getProducts

One of the eligibility rules to retrieve health plans is to ensure that the plan covers the medications that the customer is taking. Use this service to facilitate the process to retrieve eligible products linked to Formularies, which contains medications (`drugs`) where the customer (`accountId`) medications are included.

[](https://help.salesforce.com/s?language=en_US)

Class: `InsFormularyService`

Method: `getProducts`

[](https://help.salesforce.com/s?language=en_US)

## How It Works

In the Medicare line of business, the members must know that their current medications are covered by the available plans during the quoting process. The current quoting process for Medicare allows members to create a list of current medications before presenting the eligible plans.

1.  To retrieve all prescribed drugs on the ID and the object `ConsumerDrug__c` object, if both accountID and Drugs parameters are passed into the service, the service will use the `accountId`. The input must be either the list of drugs or accountId.
    
    Note
    
    Here the account is a Person Account that represents the Consumer or Member.
    
2.  Retrieves all related `FormularyDrug__c` using the list of drugs
    
3.  Retrieves all related `Formulary__c` Ids using the retrieved list of `FormularyDrug__c`.
    
4.  Matches all drugs on the input on the list of FormularyDrug\_\_c. If all the drugs exists on `Formulary__c`, it is considered an eligible `Formulary__c`.
    
5.  Finally, the service returns a list of all products in the `eligibleProducts` JSON output node that are related to all eligible `Formulary__c`.
    

Note

You can also run filters, based on `FieldNames` and associated values, to further refine results.

[](https://help.salesforce.com/s?language=en_US)

## Inputs

| 
`accountId`

 | 

Person Account Id of the customer.

Must be entered only if the list of drugs is not supplied.

 |
| --- | --- |
| 

`drugs`

 | 

List of Drug Ids

Optional if `accountId` is not supplied.

So required if accountId is supplied?

 |

[](https://help.salesforce.com/s?language=en_US)

## Remote Options

| 
Option

 | 

Description

 |
| --- | --- |
| 

`filters`

 | 

String

Filters formatted as `FieldName:Value,`delimited by comma. A custom field must include namespace.

Example:

ProductCode:PPO, ProductType\_\_c:Test

 |

[](https://help.salesforce.com/s?language=en_US)

## Input JSON

Here is a sample JSON input that uses an `accountId` input:

```
{
  "ContextId": "",
  "timeStamp": "2020-03-25T06:04:15.282Z",
  "userId": "0056g000003cVLZAA2",
  "userName": "ins-test09@vlocity.com",
  "userProfile": "System Administrator",
  "userTimeZone": -420,
  "userCurrencyCode": "USD",
  "sfdcIFrameOrigin": "https://ins-test09-dev-ed--instest09.visualforce.com",
  "sfdcIFrameHost": "web",
  "layout": "lightning",
  "isdtp": "p1",
  "id": "a236g000000NAiRAAW",
  "vlcPersistentComponent": {},
  "accountId": "0016g00000IqoMqAAJ"
}
```

And here's one that uses the `filters` remote option:

```
{
  "ContextId": "",
  "timeStamp": "2020-03-25T06:04:15.282Z",
  "userId": "0056g000003cVLZAA2",
  "userName": "ins-test09@vlocity.com",
  "userProfile": "System Administrator",
  "userTimeZone": -420,
  "userCurrencyCode": "USD",
  "sfdcIFrameOrigin": "https://ins-test09-dev-ed--instest09.visualforce.com",
  "sfdcIFrameHost": "web",
  "layout": "lightning",
  "isdtp": "p1",
  "id": "a236g000000NAiRAAW",
  "vlcPersistentComponent": {},
  "drugs": ["a4D6g000000NFJzEAO","a4D6g000000NFF9EAO"],
  "filters": "ProductCode:SG-HMO-500"
}
```

[](https://help.salesforce.com/s?language=en_US)

## Output JSON

Here is a sample output of eligible products:

```
{
  "ContextId": "",
  "timeStamp": "2020-03-25T05:51:55.663Z",
  "userId": "0056g000003cVLZAA2",
  "userName": "ins-test09@vlocity.com",
  "userProfile": "System Administrator",
  "userTimeZone": -420,
  "userCurrencyCode": "USD",
  "sfdcIFrameOrigin": "https://ins-test09-dev-ed--instest09.visualforce.com",
  "sfdcIFrameHost": "web",
  "layout": "lightning",
  "isdtp": "p1",
  "id": "a236g000000NAiRAAW",
  "vlcPersistentComponent": {},
  "accountId": "0016g00000IqoMqAAJ",
  "error": "OK",
  "eligibleProducts": [
    {
      "attributes": {
        "type": "Product2",
        "url": "/services/data/v48.0/sobjects/Product2/01t6g000000RzEbAAK"
      },
      "Id": "01t6g000000RzEbAAK",
      "Name": "HMO 500",
      "ProductCode": "SG-HMO-500",
      "instest09__Type__c": "Medical",
      "instest09__SubType__c": "HMO",
      "instest09__FormularyId__c": "a4L6g000000XCKVEA4",
      "instest09__LineOfBusiness__c": "Group Health",
      "RecordTypeId": "0126g000000NZDOAA4",
      "instest09__FormularyId__r": {
        "attributes": {
          "type": "instest09__Formulary__c",
          "url": "/services/data/v48.0/sobjects/instest09__Formulary__c/a4L6g000000XCKVEA4"
        },
        "Name": "Formulary1",
        "Id": "a4L6g000000XCKVEA4"
      }
    }
  ]
}
```

Did this article solve your issue?

Let us know so we can improve!

YesNo