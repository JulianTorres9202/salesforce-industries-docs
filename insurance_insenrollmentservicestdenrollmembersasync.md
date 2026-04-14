---
title: "InsEnrollmentServiceStd:enrollMembersAsync"
source: "https://help.salesforce.com/s/articleView?id=ind.insurance_insenrollmentservicestdenrollmembersasync.htm&language=en_US&type=5"
scraped: "2026-04-14"
filter: "ind.insurance_"
---# InsEnrollmentServiceStd:enrollMembersAsync

InsEnrollmentServiceStd:enrollMembersAsync[](https://help.salesforce.com/s?language=en_US)

You are here:

1.  [Salesforce Help](/s/?language=en_US)
2.  [Docs](/s/products?language=en_US)
3.  [Digital Insurance](https://help.salesforce.com/s/articleView?id=ind.insurance_admin_standard.htm&language=en_US&type=5)

# InsEnrollmentServiceStd:enrollMembersAsync

Use this service to enroll large groups of members.

Class: `InsEnrollmentServiceStd`

Method: `enrollMembersAsync`

## How It Works

1.  This service determines the unique plans that members are subscribed to, using the groupCensusID and contractId that are provided as inputs.
    
2.  The service creates batch jobs for each unique plan and runs the flow configured in the batch to create the policies.
    
3.  The service creates person accounts, contacts, or portal users depending on the flow configuration and data included in GroupCensusMember:
    
    1.  If GroupCensusMember includes AccountIds and the flow contains **Create Person Accounts from Group Census Members**, the service:
        
        1.  creates person accounts for InsurancePolicyParticipant.PrimaryParticipantAccountId and RelatedParticipantAccountId.
            
        2.  fills in InsurancePolicy.NameInsured with the AccountId
            
    2.  If GroupCensusMember does not include AccountIds and the flow contains **Create Contacts from Group Census Members**, the service:
        
        1.  creates contacts for InsurancePolicyParticipant.PrimaryParticipantContactId and RelatedParticipantContactId.
            
        2.  fills in InsurancePolicy.NameInsured with the groupAccountId
            
    3.  If the flow contains **Create Users from Group Census Members**, the service:
        
        1.  creates portal users for InsurancePolicyParticipant.PrimaryParticipantContactId and RelatedParticipantContactId
            
        2.  fills in InsurancePolicy.NameInsured with the groupAccountId
            
4.  The service creates Insurance Policy Coverages (_InsurancePolicyCoverages_) for the coverage items specified in the plan, for the primary member only.
    
5.  The service creates Insurance Policy Participant records for the primary member and each dependent, attaching them to the related Insurance Policy Coverage records.
    
6.  Insurance Policy Coverages:
    
    1.  The service creates one InsurancePolicyCoverage record for mandatory coverage for a family per product.
        
    2.  The service creates an InsurancePolicyCoverage record for each enrolled optional coverage per family member. Each of these InsurancePolicyCoverage records stores the enrolled Insurance Policy Participant in InsurancePolicyCoverage.InsurancePolicyParticipantId.
        
7.  Insurance Policy Premium:
    
    1.  If saveMemberPremium is True, the InsurancePolicyParticipant records contain the
        
        **StandardPremiumAmount** value of a policy**.**
8.  If isNewHire is true, the Insurance Premium is prorated based on the number of days the member is enrolled within the contract term.
    1.  Example:
        
        1.  Total premium from the rating:16.00
            
        2.  Contract duration: 365 days (Start date: 10-Jan-2023 to End date: 9-Jan-2024)
            
        3.  Member's policy start date : 28-Feb-2023
            
        4.  Total days for the new hire in the contract: 316
            
        5.  Prorated premium: 16\* (316/365) = 13.85
            
    2.  The effective date of the policy will be equal to the 'PolicyStartDate' of the primary member.
        
9.  If the rating type in the products is expression sets:
    
    1.  The Contract Start Date is used to determine the correct expression sets and decision matrix for rating.
        
10.  Once the enrollment process completes, the user receives a success or failure notification.
     

## Inputs

| Input | Description |
| --- | --- |
| `userInputs` | 
Optional.

The set of input data the rating procedure uses to get the price of the product.

 |
| `additionalInputs` | 

Optional.

Serialised key-value map of additional inputs used for product rating.

 |
| `flowVariables` | 

Optional.

Key-value map of any additional inputs to be send to the flow.

 |

## Remote Options

| Option | Description |
| --- | --- |
| `groupCensusId` | 
Required.

The Id of the Group Census containing the members to the enrolled.

 |
| `contractId` | 

Required.

The Id of the Contract that the members belong to and the plans that they will be enrolled in.

 |
| `batchName` | 

Optional.

The name of the batch configuration. The default value is Insurance Enrollment.

 |
| `saveMemberPremium` | 

Optional.

Indicates if the policy premium amount should be set for all InsurancePolicyParticipant records. If true, the policy member premium is stored in InsurancePolicyParticipant.TotalStandardAmount for all Insurance Policy Participants of a policy. The default is false.

 |
| `isNewHire` | 

Optional.

If true, prorates the premium based on the number of days the member is enrolled in the contract term. The default is false.

 |
| `matchingKeysList` | 

Required if create account or create contact invocable action is used.

 |
| `recordTypeName` | 

Optional.

The name of the record type to use when creating person accounts. Used for create account invocable action.

 |
| `profileId` | 

Required if create portal user invocable action is used.

The ID of the profile to use to create the user records.

 |
| `timezoneSidKey` | 

Required if create portal user invocable action is used.

The time zone SID key to use to create the user records.

 |
| `localeSidKey` | 

Required if create portal user invocable action is used.

The SID key of the locale to use to create user records.

 |
| `emailEncodingKey` | 

Required if create portal user invocable action is used.

The email encoding key to use to create the user records. For example, ISO-8859-1 or UTF-8.

 |
| `languageLocaleKey` | 

Required if create portal user invocable action is used.

The email encoding key to use to create the user records. For example, ISO-8859-1 or UTF-8.

 |
| `inputKeysList` | 

Optional.

A comma-delimited list of input keys from the rating inputs to use to include in the individual rating results.

 |

## Input JSON

Here's the sample input JSON:

```json
{
  "userInputs": {"ratingType": "Enrollment"},
}
```

## Output JSON

Here's the sample output JSON:

```json
{  
  "asyncBulkRequestId": "8zk9f00000Q5jUEHNS"
}
```

Did this article solve your issue?

Let us know so we can improve!

YesNo