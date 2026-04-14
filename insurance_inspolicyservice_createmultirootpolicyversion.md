---
title: "InsPolicyService:createMultiRootPolicyVersion"
source: "https://help.salesforce.com/s/articleView?id=ind.insurance_inspolicyservice_createmultirootpolicyversion.htm&language=en_US&type=5"
scraped: "2026-04-14"
filter: "ind.insurance_"
---# InsPolicyService:createMultiRootPolicyVersion

InsPolicyService:createMultiRootPolicyVersion[](https://help.salesforce.com/s?language=en_US)

You are here:

1.  [Salesforce Help](/s/?language=en_US)
2.  [Docs](/s/products?language=en_US)
3.  [Digital Insurance](https://help.salesforce.com/s/articleView?id=ind.insurance_admin_standard.htm&language=en_US&type=5)

# InsPolicyService:createMultiRootPolicyVersion

Use this service to endorse a multi-root policy from an endorsed quote.

The service uses the `quoteId` and `effectiveDate` options and triggers an asynchronous batch job to issue a new policy version and update the previous policy version.

[](https://help.salesforce.com/s?language=en_US)

Class: `InsPolicyService`

[](https://help.salesforce.com/s?language=en_US)

Method: `createMultiRootPolicyVersion`

[](https://help.salesforce.com/s?language=en_US)

## How It Works

The service:

[](https://help.salesforce.com/s?language=en_US)

1.  Uses the `quoteId` and `effectiveDate` options to endorse a multi-root policy.
    
2.  Generates child policies for each root product.
    
3.  Aggregates premiums, taxes, and fees from the child policies into the parent policy.
    
4.  Shortens and prorates the previous policy version based on dates for both parent and child policies.
    
5.  When `createTransaction` set to true, the service:
    
    1.  Creates transactions for parent and child policies.
        
    2.  Calculates the transaction amount for the child policies as the difference between the current term amount and the previous term amount for the root product.
        
    3.  Calculates the transaction amount for the parent policy as the sum of the values from each child policy.
        
    4.  Specifies the transaction name and type in the `transactionType` option. If no value is specified, it defaults to Changed/Endorsed.
        

[](https://help.salesforce.com/s?language=en_US)

## Additional Fields

[](https://help.salesforce.com/s?language=en_US)

-   Users can override the policy field values by passing `additionalFields` as an option.
    
-   Additional fields are supported for both parent and child policies at the root-policy level.
    
-   The `additionalFields` option updates fields only at the Insurance Policy object level.
    
-   For multi-root policy endorsements, these changes affect only the new policy version, leaving the previous version unchanged.
    
-   The child policy uses the product code as an identifier for the product in the `additionalFields` JSON structure.
    
-   The parent multi-root policy uses the MULTI\_ROOT\_PARENT\_POLICY as an identifier in the `additionalFields` JSON structure.
    

[](https://help.salesforce.com/s?language=en_US)

## Remote Options

| 
Option

 | 

Description

 |
| --- | --- |
| 

`quoteId`

 | 

Required

The ID of the endorsed quote from which the policy is to be created.

 |
| 

`effectiveDate`

 | 

Required

The effective date of the new policy version.

 |
| 

`createTransaction`

 | 

Optional

A Boolean flag to indicate if parent and child transactions must be created for the policy.

Default is **False.**

 |
| 

`transactionType`

 | 

Optional

Transaction name and type, applicable only when `createTransaction` is True.

Default is **Changed/Endorsed**.

 |
| 

`additionalFields`

 | 

Optional

A JSON structure that maps policy product codes to policy fields and their respective values.

 |

[](https://help.salesforce.com/s?language=en_US)

## Input JSON

This service doesn't take an input JSON.

Here’s a sample of the `additionalFields` JSON.

[](https://help.salesforce.com/s?language=en_US)`"additionalFields": {       "MULTI_ROOT_PARENT_POLICY": {         "name": "parent policy",         "term": "Annual"       },       "AUTOROOT": {         "name": "test",         "year": "2024"       },       "COMMERCIAL": {         "name": "Commercial",         "type": "Comprehensive"       }     }` 

[](https://help.salesforce.com/s?language=en_US)

## Output

| 
Option

 | 

Description

 |
| --- | --- |
| 

`jobId`

 | The ID of the asynchronous batch job. |

[](https://help.salesforce.com/s?language=en_US)

## Output JSON

Here's the sample output JSON.

[](https://help.salesforce.com/s?language=en_US)`{  "jobId": "7073t0000BNGivxAQD" }`

Did this article solve your issue?

Let us know so we can improve!

YesNo