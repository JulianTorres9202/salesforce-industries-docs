---
title: "InsPolicyService:createPolicyTerms"
source: "https://help.salesforce.com/s/articleView?id=ind.insurance_inspolicyservice__createpolicyterms.htm&language=en_US&type=5"
scraped: "2026-04-14"
filter: "ind.insurance_"
---# InsPolicyService:createPolicyTerms

InsPolicyService:createPolicyTerms[](https://help.salesforce.com/s?language=en_US)

You are here:

1.  [Salesforce Help](/s/?language=en_US)
2.  [Docs](/s/products?language=en_US)
3.  [Digital Insurance](https://help.salesforce.com/s/articleView?id=ind.insurance_admin_standard.htm&language=en_US&type=5)

# InsPolicyService:createPolicyTerms

Create policy terms in the **AssetTerm\_\_c** or **InsurancePolicyTerm\_\_c** (for Salesforce FSC) object for all the power attributes at the Policy and PolicyCoverage level. A power attribute is an attribute that has an attribute class, attribute scope, applicable item, and applicable actions.

[](https://help.salesforce.com/s?language=en_US)

[](https://help.salesforce.com/s?language=en_US)Class: `InsPolicyService`

Method: `createPolicyTerms`

[](https://help.salesforce.com/s?language=en_US)

## How It Works

1.  The service receives the **assetId** as input.
    
2.  The service retrieves all the power attributes assigned at the policy level and policy coverage level.
    
3.  Depending on the assetID input, the service creates the policy terms in the **AssetTerm\_\_c** or **InsurancePolicyTerm\_\_c** object for the power attributes. If assetID is an ID of InsurancePolicy object, the policy terms are created in **InsurancePolicyTerm\_\_c** object, else the policy terms are created in **AssetTerm\_\_c** object.
    

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

**scopes**

 | 

Optional

Comma-separated string, or a string list for which the power attribute is applicable. It works as a filter. If you specify the scopes parameter, the service creates only the attributes of the given scopes. Possible values include:

-   **Policy**
    
-   **Policy Coverage**
    
-   **Claim**
    
-   **Claim Coverage**
    

 |

[](https://help.salesforce.com/s?language=en_US)

## Input JSON

Here's the format of the input JSON:

```
{ 
   "assetId":"",
   "scopes":""
}
```

See the following example of input JSON.

```
{ 
   "assetId":"02i6g000000h3T6AAI"
}
```

[](https://help.salesforce.com/s?language=en_US)

## Output JSON

Here's the format of the output JSON:

```
{  
   "policyTermCreationErrors": {},
   "policyTermIds": []
   "inactivatedPolicyTerms": []
}
```

See the following example of output JSON.

```
{
  "policyTermCreationErrors": {
    "a3w6g000000TxurAAC_COLLISION": "Invalid decimal: No Coverage"
  },
  "policyTermIds": [
    "a5X6g000001LeUUEA0",
    "a5X6g000001LeUVEA0",
    "a5X6g000001LeUWEA0",
    "a5X6g000001LeUXEA0",
    "a5X6g000001LeUYEA0",
    "a5X6g000001LeUZEA0"
  ]
  "inactivatedPolicyTerms": [
    "a5X6g000001LeUVEA0"
  ]
}
```

[](https://help.salesforce.com/s?language=en_US)

## Results Description

**fieldInfo** Detailed information about the Policy fields

**policyVersions** A list of policies for comparison

Did this article solve your issue?

Let us know so we can improve!

YesNo