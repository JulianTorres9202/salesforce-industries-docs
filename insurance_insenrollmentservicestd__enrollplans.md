---
title: "InsEnrollmentServiceStd:enrollPlans"
source: "https://help.salesforce.com/s/articleView?id=ind.insurance_insenrollmentservicestd__enrollplans.htm&language=en_US&type=5"
scraped: "2026-04-14"
filter: "ind.insurance_"
---# InsEnrollmentServiceStd:enrollPlans

InsEnrollmentServiceStd:enrollPlans[](https://help.salesforce.com/s?language=en_US)

You are here:

1.  [Salesforce Help](/s/?language=en_US)
2.  [Docs](/s/products?language=en_US)
3.  [Digital Insurance](https://help.salesforce.com/s/articleView?id=ind.insurance_admin_standard.htm&language=en_US&type=5)

# InsEnrollmentServiceStd:enrollPlans

Use this service to create insurance policy (`InsurancePolicy`) records for member's selected medical, dental, vision, and other plans.

Class: ​`InsEnrollmentServiceStd`​​

Method: `enrollPlans`

[](https://help.salesforce.com/s?language=en_US)

## How It Works

The service does the following:

[](https://help.salesforce.com/s?language=en_US)

1.  The service takes the input JSON and looks for the information to create the policies (Insurance Policy).
    
    | defaultIsFSCOption​ | ​isFsc parameter​ | ​Output​ |
    | --- | --- | --- |
    | ​True​ | ​False​ | ​Creates Insurance Policy (​​`InsurancePolicy`​​) records​ |
    | ​False​ | ​False​ | ​Returns error message - "FSC disabled; Use old enrollPlans method to create asset Object ". ​ |
    | ​True​ | ​True​ | ​Creates Insurance Policy (​​`InsurancePolicy`​​) records​ |
    | ​False​ | ​True​ | ​Creates Insurance Policy (​​`InsurancePolicy`​​) record |
    
    Note Enrollment services can either write to the Insurance Policy and related objects (Harmonized policy data model) or Asset objects (Vlocity model), depending on the ​isFsc​ parameter, and the custom setting for ​`defaultIsFSCOption` ​​. For creating asset records, use InsEnrollmentService:enrollPlans service
    
2.  For an Insurance Policy record, the member can be represented either as a Contact or a Person Account. If the member is represented as a contact, the `Account.Id` of the enrollment contract is set as the policy's Account. When a member is represented as a Person account, the Person Account Id of member is set as the policy's Account.
    
    When a member (primary or dependent) is represented as an account and a contact both, the service uses the account representation.
    
3.  [](https://help.salesforce.com/s?language=en_US)Associates dependents to the policies as Insurance Policy Participants (​​`InsurancePolicyParticipants`​​). It creates another Insurance Policy Participant (`​InsurancePolicyParticipant​​`) for the primary member.
4.  The records for ​​`InsurancePolicyParticipants​​` are populated according to these rules:
    
    | 
    Primary InsurancePolicyParticipant​
    
     | 
    
    Dependent InsurancePolicyParticipant​
    
     |
    | --- | --- |
    | 
    
    Primary Member Id = PersonAccount​
    
     | 
    
    PrimaryParticipant.PrimaryParticipantAccountId = PersonAccount​PrimaryParticipant.PrimaryParticipantContactId = PersonAccount.personContactId​
    
     | 
    
    DependentParticipant.PrimaryParticipantAccountId = PersonAccount​DependentParticipant.PrimaryParticipantContactId = PersonAccount.personContactId​
    
     |
    | 
    
    Primary Member Id = ContactId​
    
     | 
    
    PrimaryParticipant.PrimaryParticipantContactId = ContactId​
    
     | 
    
    ​DependentParticipant.PrimaryParticipantContactId = ContactId​
    
     |
    | 
    
    Dependent Member Id = ContactId/AccountId
    
     | 
    
    ​The population of Primary participant records happens based on the primary member Id​.
    
     | 
    
    ​The dependent member population follows the same logic as described above for primary members.​
    
     |
    
5.  Gets the ​`ProductId`​ from the plan and stamps ​`InsurancePolicy.ProductId`​​ to that Id.
    
6.  Creates these relationships:
    
    | 
    Insurance Policy
    
     |
    | --- |
    | 
    
    `InsurancePolicy.EffectiveDate`\= `Contract.StartDate` or the EffectiveStart in the input JSON.
    
     |
    | 
    
    `InsurancePolicy.ExpirationDate` = `Contract.EndDate` or the EffectiveEnd in the input JSON.
    
     |
    | 
    
    `InsurancePolicy.ContractGroupPlanId` = `ContractGroupPlan.Id​`
    
     |
    
7.  The service calculates `InsurancePolicy.PolicyTerm` based on `Contract.ContractTerm`:
    
    | 
    Insurance Policy
    
     |
    | --- |
    | 
    
    `InsurancePolicy.PolicyTerm` \= Annual.
    
     |
    | 
    
    `InsurancePolicy.PolicyTerm` \= Semi-Annual
    
     |
    | 
    
    `InsurancePolicy.PolicyTerm` \= Monthly
    
     |
    
8.  Gets the `Price` key from the input JSON and creates these relationships:
    
    | 
    Insurance Policy
    
     |
    | --- |
    | 
    
    `InsurancePolicy.StandardPremiumAmount` = Price
    
     |
    | 
    
    `InsurancePolicy.TermPremiumAmount​` = prorated price based on the effective dates.
    
     |
    
9.  Creates Insurance Policy Coverages (`InsurancePolicyCoverages`) for the coverage items.
    

[](https://help.salesforce.com/s?language=en_US)

## Remote Options

| 
Option

 | 

Description

 |
| --- | --- |
| 

`inputKey`

 | 

Required.

The key to a pre-transformed JSON structure that contains information the service needs.

 |

[](https://help.salesforce.com/s?language=en_US)

## Input JSON

The service takes the input JSON specified by the `inputKey`. In this example, `inputKey` = `enrollmentJson`.

The service requires:

-   `contractId`: <value\>
    
-   `Dependents`: <list of maps for contactId and relationshipType of the dependents>
    

This input JSON can have either a list of objects or a map because the service supports creating either one policy or multiple policies.

​​`primaryMemberId​​` can either be a person account ID or contact ID. Based on the ID type of `​primaryMemberId`​​, the service works as described earlier. ​

Similarly, for dependents, the service has ​`memberId`​ node to support both Person Account Id and Contact Id. Based on the Id type of ​`memberId`​​, the service works as described earlier.

Here's the sample input JSON:

[](https://help.salesforce.com/s?language=en_US)`{ 	"enrollmentJson": {     	"dependents": [       	{         	"IsSpouse": false,         	"memberId": "001RO000003NTBtYAO",         	"LastName": "Jones",         	"FirstName": "Jean",         	"relationshipType": "Child"       	}     	],     	"coverages": {       		"records": [         	{           		"Price": "13",           		"productcode": "CI"         	}       		]     	},     	"Price": 20,     	"planId": "0rgRO000000000zYAA",     	"primaryMemberId": "001RO000003Zr0AYAS",     	"contractId": "800RO000000TFXdYAO"   } }`

[](https://help.salesforce.com/s?language=en_US)

## Output JSON

The service creates a list of insurance policy records.

[](https://help.salesforce.com/s?language=en_US)`{   "policyIds": [     "0YTRO00000006Ar4AI"   ],   "errorMsg": "",   "assetIds": [],   "error": "OK" }`

Did this article solve your issue?

Let us know so we can improve!

YesNo