---
title: "InsQuoteService:createEndorsementQuote"
source: "https://help.salesforce.com/s/articleView?id=ind.insurance_insquoteservice_createendorsementquote.htm&language=en_US&type=5"
scraped: "2026-04-14"
filter: "ind.insurance_"
---# InsQuoteService:createEndorsementQuote

InsQuoteService:createEndorsementQuote[](https://help.salesforce.com/s?language=en_US)

You are here:

1.  [Salesforce Help](/s/?language=en_US)
2.  [Docs](/s/products?language=en_US)
3.  [Digital Insurance](https://help.salesforce.com/s/articleView?id=ind.insurance_admin_standard.htm&language=en_US&type=5)

# InsQuoteService:createEndorsementQuote

Use this service to create an endorsement quote with quote line items for single-root and multi-root policies.

[](https://help.salesforce.com/s?language=en_US)

Class: `InsQuoteService`

[](https://help.salesforce.com/s?language=en_US)

Method: `createEndorsementQuote`

[](https://help.salesforce.com/s?language=en_US)

## How It Works

The service takes the `policyId` and `effectiveDate` as the input parameters to create an endorsement quote and quote line items.

To create a single-root quote, the service:

[](https://help.salesforce.com/s?language=en_US)

1.  Creates only one root quote line item.
    
2.  Transforms the InsurancePolicyCoverages, InsurancePolicyAssets, and InsurancePolicyParticipants records to create quote line items and establishes relationships between them.
    
3.  Transforms the InsurancePolicySurcharge records to create `QuotePricingAdjustment__c` records
    
    .
4.  Returns a `quoteId` in the output JSON.
    

To create a multi-root quote, the service:

[](https://help.salesforce.com/s?language=en_US)

1.  Creates multiple root quote line items corresponding to the number of child policies.
    
2.  Transforms the InsurancePolicyCoverages, InsurancePolicyAssets, and InsurancePolicyParticipants records to create quote line items and establishes relationships between them for each child policy.
    
3.  Transforms the InsurancePolicySurcharge records to create `QuotePricingAdjustment__c` records.
    
4.  Returns a `quoteId` in the output JSON.
    

[](https://help.salesforce.com/s?language=en_US)

## Inputs

You must pass these inputs.

| 
INPUT

 | 

Description

 |
| --- | --- |
| 

`policyId`

 | 

Required

The ID of the latest parent policy version from which the endorsement quote is to be created.

 |
| 

`effectiveDate`

 | 

Required

The effective date of the quote.

 |
| 

`name`

 | 

Optional

The name of the quote to be created.

 |
| 

`options`

 | 

Optional

A JSON structure that specifies options to execute rules.

 |

| 
INPUT

 | 

Description

 |
| --- | --- |
| 

`policyId`

 | 

Required

The ID of the latest parent policy version from which the endorsement quote is to be created.

 |
| 

`effectiveDate`

 | 

Required

The effective date of the quote.

 |
| 

`name`

 | 

Optional

The name of the quote to be created.

 |
| 

`remoteOptions`

 | 

Optional

A JSON structure that specifies options to execute rules.

[](https://help.salesforce.com/s?language=en_US)

-   `unEligibilityRequiredDefaultSelectedRules`—Specifies whether to execute the eligibility and default selected rules.
    
    Default is **False**.
    
-   `runRelationshipRules`—Specifies whether to execute relationship rules.
    
    Default is **False**.
    
-   `runSelectedValidationRules` —Specifies whether to execute selected validation rules.
    
    Default is **False**.
    

 |

[](https://help.salesforce.com/s?language=en_US)

## Input JSON

Here's a sample of the input JSON.

[](https://help.salesforce.com/s?language=en_US)`{    "policyId": "0YT5w000000Y8MNGA0",    "effectiveDate":"2024-04-04",    "Name":"Endorse-Quote",    "remoteOptions": {       "runEligibilityRequiredDefaultSelectedRules": false,         "runRelationshipRules": false,         "runSelectedValidationRules": false     } }`     

[](https://help.salesforce.com/s?language=en_US)

## Output

| 
Option

 | 

Description

 |
| --- | --- |
| 

`Id`

 | The ID of the endorsement quote created. |

[](https://help.salesforce.com/s?language=en_US)

## Output JSON

Here's the sample output JSON:

[](https://help.salesforce.com/s?language=en_US)`{   "Id":"0Q04x0000077hZFCAY" }`

Did this article solve your issue?

Let us know so we can improve!

YesNo