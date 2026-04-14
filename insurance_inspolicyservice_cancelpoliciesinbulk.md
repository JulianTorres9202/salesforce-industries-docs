---
title: "InsPolicyService:cancelPoliciesInBulk"
source: "https://help.salesforce.com/s/articleView?id=ind.insurance_inspolicyservice_cancelpoliciesinbulk.htm&language=en_US&type=5"
scraped: "2026-04-14"
filter: "ind.insurance_"
---# InsPolicyService:cancelPoliciesInBulk

InsPolicyService:cancelPoliciesInBulk[](https://help.salesforce.com/s?language=en_US)

You are here:

1.  [Salesforce Help](/s/?language=en_US)
2.  [Docs](/s/products?language=en_US)
3.  [Digital Insurance](https://help.salesforce.com/s/articleView?id=ind.insurance_admin_standard.htm&language=en_US&type=5)

# InsPolicyService:cancelPoliciesInBulk

Use this service to cancel policy records (InsurancePolicy) in bulk. The service uses InsPolicyService:cancelPolicy service and Vlocity batch Framework to process the cancellation of multiple policies asynchronously.

This service uses Contract Group Plan and is specific to the Group Benefits feature.

Class: `InsPolicyService`

Method: `cancelPoliciesInBulk`

## How It Works

The service takes a list of policy details (policyId and effectiveDate) and then creates batch job to cancel policies in bulk. The batchSize is provided as an input parameter in options. If no value is provided, the service takes 12 as the default batch size. The service only processes valid policy details from the list and returns the invalid ones in output. A policy is considered invalid for cancellation if the policyId or effectiveDate is null/empty.

Note

The maximum batch size supported by the service is 12. Any batch size over 12 will throw an error.

## Input Options

| Option | Description |
| --- | --- |
| `policyId` | 
Required

The ID of policy to be canceled.

 |
| `effectiveDate` | 

Required

The date on which policy cancellation becomes effective. The supported format is `"YYYY-MM-DD HH:MM:SS"` or `%OmniScriptDataElement%`.

 |
| `batchSize` | 

Optional

The size of batches to be processed. The maximum batch size supported is 12.

 |

## Remote Options

| 
Option

 | 

Description

 |
| --- | --- |
| `batchSize` | 

Optional.

The size of batches to be processed. The maximum batch size supported is 12.

 |

[](https://help.salesforce.com/s?language=en_US)

## Sample Input and Output JSON Format

Use case 1: When user provides invalid policy details, the service returns the invalid policy details in output.

**Input JSON**

```json
inputs : 

{
	"policies": [
           {
               "policyId" : "0YTR00000000000000",
               "effectiveDate" : "12/22/2022"
           },
           {
               "policyId" : "0YTR00000000000001",
               "effectiveDate" : "12/22/2022"
           },
           {
               "policyId" : null, //invalid policy detail
               "effectiveDate" : "12/22/2022"
           },
        ]
}

options : 
{
       "batchSize" : 1
}
```

**Output JSON**

```json
{
    "invalidPolicies" : [
            {
               "policyId" : null, //invalid policy detail
               "effectiveDate" : "12/22/2022"
            }
        ]
}
```

Use case 2: When batchSize is greater than 12, the service throws an error.

**Input JSON**

```json
inputs : 
{
    "policies": [
           {
               "policyId" : "0YTR00000000000000",
               "effectiveDate" : "12/22/2022"
           },
           {
               "policyId" : "0YTR00000000000001",
               "effectiveDate" : "12/22/2022"
           },
           {
               "policyId" : null, //invalid policy detail
               "effectiveDate" : "12/22/2022"
           },
        ]
}
options : 
{
       "batchSize" : 13
}
```

**Output JSON**

```json
{
  "error": "batchSize should not be greater than 12/null/non-zero"
}
```

Did this article solve your issue?

Let us know so we can improve!

YesNo