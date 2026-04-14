---
title: "InsPolicyService:getPolicyVersions"
source: "https://help.salesforce.com/s/articleView?id=ind.insurance_inspolicyservice__getpolicyversions.htm&language=en_US&type=5"
scraped: "2026-04-14"
filter: "ind.insurance_"
---# InsPolicyService:getPolicyVersions

InsPolicyService:getPolicyVersions[](https://help.salesforce.com/s?language=en_US)

You are here:

1.  [Salesforce Help](/s/?language=en_US)
2.  [Docs](/s/products?language=en_US)
3.  [Digital Insurance](https://help.salesforce.com/s/articleView?id=ind.insurance_admin_standard.htm&language=en_US&type=5)

# InsPolicyService:getPolicyVersions

Use this service to retrieve the different versions of a policy. The service returns a list of policies with high level fields determined by the Policy field set **PolicyCompareHeader**.

[](https://help.salesforce.com/s?language=en_US)

[](https://help.salesforce.com/s?language=en_US)Class: `InsPolicyService`

Method: `getPolicyVersions`

[](https://help.salesforce.com/s?language=en_US)

## How It Works

Note

This service uses the same inputs and options for Vlocity objects and FSC objects. Based on the Id passed, the service determines whether the Id refers to a Vlocity object or FSC object, and retrieves the versions accordingly.

1.  The service receives the **assetId** as input.
    
2.  The service queries for other policies that share the same version Id.
    
3.  The service returns a list of policies.
    

[](https://help.salesforce.com/s?language=en_US)

## Remote Options

| 
Option

 | 

Description

 |
| --- | --- |
| 

**assetId**

 | 

Required

Asset (policy) Ids

 |
| 

**originalPolicy**

 | 

Optional

The default is false. If true, return the original version of the policy only.

 |
| 

**lastPolicy**

 | 

Optional

The default is false. if true, return the latest version of the policy only.

 |

[](https://help.salesforce.com/s?language=en_US)

## Input JSON

See the following example of input JSON.

```
{
  "assetId":"02i6g000000I21EAAS"
}
```

[](https://help.salesforce.com/s?language=en_US)

## Output JSON

See the following example of output JSON.

```
{
  "fieldInfo": {
    "instest10__AttributeSelectedValues__c": {
      "isUpdateable": true,
      "isCreatable": true,
      "isRequired": false,
      "fieldType": "TEXTAREA",
      "fieldLabel": "Attribute Selected Values",
      "fieldName": "instest10__AttributeSelectedValues__c"
    },
    "Product2Id": {
      "isUpdateable": true,
      "isCreatable": true,
      "isRequired": false,
      "fieldType": "REFERENCE",
      "fieldLabel": "Product ID",
      "fieldName": "Product2Id"
    },
    "Name": {
      "isUpdateable": true,
      "isCreatable": true,
      "isRequired": false,
      "fieldType": "STRING",
      "fieldLabel": "Asset Name",
      "fieldName": "Name"
    },
    "instest10__TotalPremiumForTerm__c": {
      "isUpdateable": true,
      "isCreatable": true,
      "isRequired": false,
      "fieldType": "CURRENCY",
      "fieldLabel": "Total Premium for Term",
      "fieldName": "instest10__TotalPremiumForTerm__c"
    },
    "Id": {
      "isUpdateable": false,
      "isCreatable": false,
      "isRequired": false,
      "fieldType": "ID",
      "fieldLabel": "Asset ID",
      "fieldName": "Id"
    },
    "instest10__EffectiveDate__c": {
      "isUpdateable": true,
      "isCreatable": true,
      "isRequired": false,
      "fieldType": "DATE",
      "fieldLabel": "Effective Date",
      "fieldName": "instest10__EffectiveDate__c"
    },
    "instest10__ExpirationDate__c": {
      "isUpdateable": true,
      "isCreatable": true,
      "isRequired": false,
      "fieldType": "DATE",
      "fieldLabel": "Expiration Date",
      "fieldName": "instest10__ExpirationDate__c"
    }
  },
  "policyVersions": [
    {
      "attributes": {
        "type": "Asset",
        "url": "/services/data/v48.0/sobjects/Asset/02i6g000000HxXzAAK"
      },
      "Name": "M Auto 1",
      "Id": "02i6g000000HxXzAAK",
      "IsCompetitorProduct": false,
      "instest10__ExpirationDate__c": "2020-04-21",
      "instest10__EffectiveDate__c": "2020-03-17",
      "instest10__EffectiveTerm__c": "2020-03-17 - 2020-04-21",
      "instest10__MonthlyPremium__c": 393.75,
      "instest10__StandardPremium__c": 4725,
      "Product2Id": "01t6g000000LZKoAAO",
      "ProductCode": "AUTOROOT",
      "instest10__Term__c": "Annual",
      "instest10__TotalAmount__c": 5272.5,
      "instest10__TotalAmountForTerm__c": 520.03,
      "instest10__TotalFeeAmount__c": 75,
      "instest10__TotalFeeForTerm__c": 7.4,
      "instest10__TotalPremiumForTerm__c": 466.03,
      "instest10__TotalSumInsured__c": 350000,
      "instest10__TotalTaxForTerm__c": 46.6,
      "instest10__TotalTaxAmount__c": 472.5
    },
    {
      "attributes": {
        "type": "Asset",
        "url": "/services/data/v48.0/sobjects/Asset/02i6g000000HxY4AAK"
      },
      "Name": "M Auto 1 v1",
      "Id": "02i6g000000HxY4AAK",
      "instest10__PreviousVersionId__c": "02i6g000000HxXzAAK",
      "instest10__OriginalVersionId__c": "02i6g000000HxXzAAK",
      "IsCompetitorProduct": false,
      "instest10__ExpirationDate__c": "2020-07-15",
      "instest10__EffectiveDate__c": "2020-04-22",
      "instest10__EffectiveTerm__c": "2020-04-22 - 2020-07-15",
      "instest10__MonthlyPremium__c": 393.75,
      "instest10__StandardPremium__c": 4725,
      "Product2Id": "01t6g000000LZKoAAO",
      "ProductCode": "AUTOROOT",
      "instest10__Term__c": "Annual",
      "instest10__TotalAmount__c": 5272.5,
      "instest10__TotalAmountForTerm__c": 1227.84,
      "instest10__TotalFeeAmount__c": 75,
      "instest10__TotalFeeForTerm__c": 17.47,
      "instest10__TotalPremiumForTerm__c": 1100.34,
      "instest10__TotalSumInsured__c": 350000,
      "instest10__TotalTaxForTerm__c": 110.03,
      "instest10__TotalTaxAmount__c": 472.5
    },
    {
      "attributes": {
        "type": "Asset",
        "url": "/services/data/v48.0/sobjects/Asset/02i6g000000HxY9AAK"
      },
      "Name": "M Auto 1 v1 v1",
      "Id": "02i6g000000HxY9AAK",
      "instest10__PreviousVersionId__c": "02i6g000000HxY4AAK",
      "instest10__OriginalVersionId__c": "02i6g000000HxXzAAK",
      "IsCompetitorProduct": false,
      "instest10__ExpirationDate__c": "2020-08-25",
      "instest10__EffectiveDate__c": "2020-07-16",
      "instest10__EffectiveTerm__c": "2020-07-16 - 2020-08-25",
      "instest10__MonthlyPremium__c": 393.75,
      "instest10__StandardPremium__c": 4725,
      "Product2Id": "01t6g000000LZKoAAO",
      "ProductCode": "AUTOROOT",
      "instest10__Term__c": "Annual",
      "instest10__TotalAmount__c": 5272.5,
      "instest10__TotalAmountForTerm__c": 592.25,
      "instest10__TotalFeeAmount__c": 75,
      "instest10__TotalFeeForTerm__c": 8.42,
      "instest10__TotalPremiumForTerm__c": 530.75,
      "instest10__TotalSumInsured__c": 350000,
      "instest10__TotalTaxForTerm__c": 53.08,
      "instest10__TotalTaxAmount__c": 472.5
    }
}
```

[](https://help.salesforce.com/s?language=en_US)

## Results Description

**fieldInfo** Detailed information about the policy fields

**policyVersions** List of policies for comparison

Did this article solve your issue?

Let us know so we can improve!

YesNo