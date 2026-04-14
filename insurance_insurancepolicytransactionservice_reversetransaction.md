---
title: "InsurancePolicyTransactionService:reverseTransaction"
source: "https://help.salesforce.com/s/articleView?id=ind.insurance_insurancepolicytransactionservice_reversetransaction.htm&language=en_US&type=5"
scraped: "2026-04-14"
filter: "ind.insurance_"
---# InsurancePolicyTransactionService:reverseTransaction

InsurancePolicyTransactionService:reverseTransaction[](https://help.salesforce.com/s?language=en_US)

You are here:

1.  [Salesforce Help](/s/?language=en_US)
2.  [Docs](/s/products?language=en_US)
3.  [Digital Insurance](https://help.salesforce.com/s/articleView?id=ind.insurance_admin_standard.htm&language=en_US&type=5)

# InsurancePolicyTransactionService:reverseTransaction

Use this service to reverse an insurance policy transaction.

[](https://help.salesforce.com/s?language=en_US)This service creates a Reversal transaction for an insurance policy transaction. It also recreates the policy based on a snapshot of the policy from the time the original transaction was created.

Class: `InsurancePolicyTransactionService`

Method: `reverseTransaction`

[](https://help.salesforce.com/s?language=en_US)

## How It Works

To reverse an insurance policy transaction, this service:

1.  Validates that the given input `Id` is an instance of the `InsurancePolicyTransaction` object.
    
2.  Retrieves the `InsurancePolicyTransaction` record and validates that the transaction to reverse is:
    
    -   The policy's latest transaction.
        
    -   Linked to an active (not reversed) policy.
        
    -   Linked to the latest active policy version.
        
    -   Linked to a policy snapshot.
        
        Records linked to a policy snapshot have an attachment named `<policyId>_PolicySnapshot`. Policy snapshots are enabled for services that create transactions, specifically [InsPolicyService:createUpdatePolicy](https://help.salesforce.com/s/articleView?id=ind.insurance_inspolicyservice__createupdatepolicy.htm&language=en_US&type=5 "Use this service to create a new insurance policy or to update an existing policy with new information."), [InsPolicyService:createPolicyVersion](https://help.salesforce.com/s/articleView?id=ind.insurance_inspolicyservice__createpolicyversion.htm&language=en_US&type=5 "Use this service to create a new version of an existing policy, while maintaining the existing policy record as-is."), [InsPolicyService:cancelPolicy](https://help.salesforce.com/s/articleView?id=ind.insurance_inspolicyservice__cancelpolicy.htm&language=en_US&type=5 "Use this service to cancel an existing insurance policy."), and [InsPolicyService:createTransaction](https://help.salesforce.com/s/articleView?id=ind.insurance_inspolicyservice__createtransaction.htm&language=en_US&type=5 "Use this service to create a transaction on a target policy.").
        
    -   Not a Reversal transaction.
        
3.  Creates a Reversal transaction record with:
    
    -   Negative amounts from the original transaction.
        
    -   transactionDate and postDate values based on specified options.
        
    -   Transaction type and name set to Reversal.
        
    -   parentTransactionId equal to the transaction ID of the transaction getting reversed.
        
    -   policyVersionId equal to the policy ID of the snapshot.
        
4.  Sets the status of the current policy and the snapshot policy to Reversed.
    
5.  Recreates the policy based on the snapshot. The service:
    
    -   Removes existing IDs so that new records are created when saving.
        
    -   Recreates Payment and Revenue schedules via delete-insert, preserving the original lookup to the transactions.
        
6.  Calls `InsuranceCommissionDataService.reverseCommissions` to create and save a reversal commission for the commission related to the original transaction.
    

[](https://help.salesforce.com/s?language=en_US)

## Inputs

| 
Input

 | 

Description

 |
| --- | --- |
| 

`Id`

 | 

The ID of the `InsurancePolicyTransaction` to reverse. Invalid values generate an error.

 |

[](https://help.salesforce.com/s?language=en_US)

## Remote Options

All remote options are optional.

| 
Remote Option

 | 

Description

 |
| --- | --- |
| 

`effectiveDate`

 | 

Value assigned to reversal transaction's transaction date

 |
| 

`postDate`

 | 

Post date for the reversal transaction (Default: `effectiveDate`)

 |
| 

`getDRBundleName`

 | 

Omnistudio Data Mapper bundle for retrieving the `InsurancePolicy` and `InsurancePolicyTransaction` records needed to process the reversal

 |
| 

`getCustomClassName`

 | 

Class for retrieving `InsurancePolicy` and `InsurancePolicyTransaction` records needed to process the reversal (Default: `GetPolicyTransactionReversalFields`)

 |
| 

`postPolicyDRBundleName`

 | 

Data Mapper bundle for creating and updating `InsurancePolicy` records

 |
| 

`postPolicyCustomClassName`

 | 

Class for creating and updating `InsurancePolicy` records (Default: `PostInsurancePolicy`)

 |
| 

`postTxnDRBundleName`

 | 

Data Mapper bundle for creating and updating `InsurancePolicyTransaction` records

 |
| 

`postTxnCustomClassName`

 | 

Class for creating and updating `InsurancePolicyTransaction` records (Default: `PostInsurancePolicyTransaction`)

 |

[](https://help.salesforce.com/s?language=en_US)

## Output

| 
Output

 | 

Description

 |
| --- | --- |
| 

`transactionIdForReversal`

 | 

ID of the reversal transaction record. This value matches the input `Id`.

 |
| 

`reversalCommissionId`

 | 

ID of the reversal commission record

 |
| 

`reversedCommissionAmount`

 | 

Amount of the reversed commission

 |

[](https://help.salesforce.com/s?language=en_US)

## Input JSON

Here's how to format input JSON.

```json
{
    "Id": <transaction id>
}
```

Here's how to format options.

```json
{
    "effectiveDate": <Date>,
    "postDate" : <Date>,
    "getCustomClassname" : <String>,
    "postPolicyCustomClassName" : <String>,
    "postTxnCustomClassName" : <String>
}
```

Here's a sample of input.

```json
{
    "Id": "0k9R000000003KjIAI"
}
```

And here's a sample of input options.

```json
{
    "effectiveDate": "4/1/2021",
    "postDate" : "4/5/2021",
    "getCustomClassname" : "GetPolicyTransactionReversalFields",
    "postPolicyCustomClassName" : "PostInsurancePolicy",
    "postTxnCustomClassName" : "PostInsurancePolicyTransaction"
}
```

[](https://help.salesforce.com/s?language=en_US)

## Output JSON

Here's the format of output JSON.

```json
{
    "transactionIdForReversal": <transaction id>,
    "reversalCommissionId": <commission id>,
    "reversedCommissionAmount": <Decimal>
}
```

Here's a sample of output.

```json
{
    "transactionIdForReversal": "0k9R000000003KjIAI",
    "reversalCommissionId": "0k9R000000003KjIAI",
    "reversedCommissionAmount": 123.00
}
```

Did this article solve your issue?

Let us know so we can improve!

YesNo