---
title: "InsPolicyService:createMultiRootPolicy"
source: "https://help.salesforce.com/s/articleView?id=ind.insurance_inspolicyservice_createmultirootpolicy.htm&language=en_US&type=5"
scraped: "2026-04-14"
filter: "ind.insurance_"
---# InsPolicyService:createMultiRootPolicy

InsPolicyService:createMultiRootPolicy[](https://help.salesforce.com/s?language=en_US)

You are here:

1.  [Salesforce Help](/s/?language=en_US)
2.  [Docs](/s/products?language=en_US)
3.  [Digital Insurance](https://help.salesforce.com/s/articleView?id=ind.insurance_admin_standard.htm&language=en_US&type=5)

# InsPolicyService:createMultiRootPolicy

Use this service to issue a multi-root policy from a quote.

[](https://help.salesforce.com/s?language=en_US)

Class: `InsPolicyService`

[](https://help.salesforce.com/s?language=en_US)

Method: `createMultiRootPolicy`

[](https://help.salesforce.com/s?language=en_US)

## How It Works

The service:

[](https://help.salesforce.com/s?language=en_US)

1.  Uses the `quoteId` and `effectiveDate` options to issue a multi-root policy.
    
2.  Generates child policies for each root product.
    
3.  Consolidates premiums, taxes, and fees from the child policies into the parent policy.
    
4.  Creates the necessary transactions if `createTransaction` is set to true.
    
5.  Consolidates these transactions into the parent multi-root policy.
    

[](https://help.salesforce.com/s?language=en_US)

## Additional Fields

[](https://help.salesforce.com/s?language=en_US)

-   Users can override the policy field values by using the `additionalFields` option.
    
-   Additional fields are supported for both parent and child policies at the root-policy level.
    
-   The `additionalFields` option updates fields only at the Insurance Policy object level.
    
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

The ID of the quote from which the policy is to be created.

 |
| 

`effectiveDate`

 | 

Required

The effective date of the policy.

 |
| 

`endDate`

 | 

Optional

The end date of the policy.

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

Default is **Sold Policy**.

 |
| 

`createContactForParticipants`

 | 

Optional

A Boolean flag to determine if contact records must be created for the participant.

Default is **True**.

 |
| 

`term`

 | 

Optional

Term of the insurance policy.

Default is **Annual.**

 |
| 

`ratingDate`

 | 

Optional

The rating date that was used to price the input JSON.

 |
| 

`additionalFields`

 | 

Optional

A JSON structure that maps policy product codes to policy fields and their respective values.

 |
| 

`refPolicyNumToPopulate`

 | 

Optional

A Boolean flag to indicate if the reference policy number must be generated. This option is required when a reference policy number field is added to the `additionalFields` JSON structure.

Default is **True**.

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

Here's the sample output JSON:

[](https://help.salesforce.com/s?language=en_US)`{  "jobId": "7073t0000BNGivxAQD" }`

Did this article solve your issue?

Let us know so we can improve!

YesNo