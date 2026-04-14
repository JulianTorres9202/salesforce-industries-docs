---
title: "InsClaimItemService:getPayees"
source: "https://help.salesforce.com/s/articleView?id=ind.insurance_insclaimitemservice__getpayees.htm&language=en_US&type=5"
scraped: "2026-04-14"
filter: "ind.insurance_"
---# InsClaimItemService:getPayees

InsClaimItemService:getPayees[](https://help.salesforce.com/s?language=en_US)

You are here:

1.  [Salesforce Help](/s/?language=en_US)
2.  [Docs](/s/products?language=en_US)
3.  [Digital Insurance](https://help.salesforce.com/s/articleView?id=ind.insurance_admin_standard.htm&language=en_US&type=5)

# InsClaimItemService:getPayees

Use this service to return a list of payees for a specified claim.

[](https://help.salesforce.com/s?language=en_US)

Class: `InsClaimItemService`

Method: `getPayees`

[](https://help.salesforce.com/s?language=en_US)

## How It Works

1.  Takes the `claimId` and retrieves the claim record.
    
2.  Returns a list of payees attached to this claim.
    
    The policy holder for the claim is designated by the field `policyHolder` = `true`.
    

[](https://help.salesforce.com/s?language=en_US)

## Remote Options

| 
Option

 | 

Description

 |
| --- | --- |
| 

`claimId`

 | 

Required.

The Id of the claim for which the service will return a list of payees.

 |

[](https://help.salesforce.com/s?language=en_US)

## Input JSON

This service does not use an input JSON.

[](https://help.salesforce.com/s?language=en_US)

## Output JSON

The service returns

```
[
    "payees": [
        { 
           "instest03__PayeePartyId__c": "a0x1U000001Uaq1QAC", 
           "instest03__PayeeContactId__c": null, 
           "instest03__PayeeAccountId__c": "0011U00000KtW4fQAF", 
           "instest03__PayeePartyName__c": "VlocityAccount" 
        },{ 
           "instest03__PayeePartyId__c": "a0x1U000001V8VqQAK", 
           "instest03__PayeeContactId__c": "0031U00000MrU1SQAV", 
           "instest03__PayeeAccountId__c": null, 
           "instest03__PayeePartyName__c": "John Doe" 
        },{ 
           "PolicyHolder": true, 
           "instest03__PayeePartyId__c": "a0x1U0000008JWDQA2",             
           "instest03__PayeeContactId__c": "0031U00000CHQCYQA5", 
           "instest03__PayeeAccountId__c": null, 
           "instest03__PayeePartyName__c": "Joan Smith" 
        }
    ]
]
```

Did this article solve your issue?

Let us know so we can improve!

YesNo