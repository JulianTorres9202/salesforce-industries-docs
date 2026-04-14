---
title: "InsEnrollmentServiceStd:enrollMembers"
source: "https://help.salesforce.com/s/articleView?id=ind.insurance_insenrollmentservicestd__enrollmembers.htm&language=en_US&type=5"
scraped: "2026-04-14"
filter: "ind.insurance_"
---# InsEnrollmentServiceStd:enrollMembers

InsEnrollmentServiceStd:enrollMembers[](https://help.salesforce.com/s?language=en_US)

You are here:

1.  [Salesforce Help](/s/?language=en_US)
2.  [Docs](/s/products?language=en_US)
3.  [Digital Insurance](https://help.salesforce.com/s/articleView?id=ind.insurance_admin_standard.htm&language=en_US&type=5)

# InsEnrollmentServiceStd:enrollMembers

Use this service to enroll census members into their selected plans.

Class: ​`InsEnrollmentServiceStd`​​ ​

Method: `enrollMembers`

## How It Works

1.  The service first queries for Group Census Members either a) using all members for a given ​`groupCensusId​` or b) using only the members specified in the ​`groupCensusMembersIds`​​ list.
2.  It then searches for pre-enrolled plans linked to each member in the ​`GroupCensusMemberPlan`​​. ​
3.  The product plans for each member are returned.
    
4.  If the product is a part of `contract` and `contractGroupPlans`, the service creates an `InsurancePolicy`, and the `InsurancePolicyCoverages` for the coverage items specified in the plan.
    
5.  You can create ​Person Accounts​​ for the group census members in the given group census. To support the Person Account flow: ​
    
    1.  If `accountIds` (retrieved from the `GroupCensusMember`) are available, then the service uses `AccountId` as `InsurancePolicy.NameInsured` and creates `InsurancePolicyParticipants`, `PrimaryParticipantAccountId` and `RelatedParticipantAccountId`.
        
    2.  ​ If ​`accountI`d​ is null, the service uses ​`groupAccountId`​ as ​I`nsurancePolicy.NameInsured​` and `​contactId`​ as `​InsurancePolicyParticipants`​​, ​`PrimaryParticipantContactId`​, and ​`RelatedParticipantContactId​​`. ​ ​ ​
        
6.  The service creates an Insurance Policy only for primary members and not their dependents. It creates the dependent information in a separate object called ​`InsurancePolicyParticipants​​`. A record is also created for the Primary member. The service associates these records to the Insurance Policies. `InsurancePolicyParticipant`, `primaryParticipantAccountId` and `relatedParticipantAccountId` fields are also populated using the `AccountId` field of the group census member and similarly Contact fields when `AccountId` is null.
    
7.  Insurance Policy Coverages
    
    1.  If a member is enrolled for an optional coverage during member enrollment, the service creates a separate
        
        `InsurancePolicyCoverage` record corresponding to each enrolled optional coverage. The `InsurancePolicyCoverage` record stores the enrolled `InsuredPolicyParticipantId`.
    2.  For mandatory coverages, there is a single `InsurancePolicyCoverage` record for a family per product. ​
8.  Insurance Policy Premium
    1.  If `saveMemberPremium` is True, the `InsurancePolicyParticipant` records include the `StandardPremiumAmount` value of a policy.
        
        Note
        
        The calculation procedure must be configured to set the **memberPremium** amount field with the **Include in Calculation Output** checked.
        

## Remote Options

| Option​ | ​Description​ |
| --- | --- |
| ​​​`groupCensusMemberIds`​​​ | 
​Required if ​​`groupCensusId`​​ isn't used.​

IDs (comma-separated) of the specific group census members to be enrolled.​

 |
| ​​​`groupCensusId​​​` | 

Required if ​​`groupCensusMemberIds`​​ isn't used.​

The ID of the group census containing all census members to be enrolled.​

 |
| ​​​`contractId​​​` | 

Required.​

The ID of the contract that the members belong to and the plans that they are enrolled in.

 |
| `​​​dependentRoleName​​​` | 

The ​Role​ field in ​`InsurancePolicyParticipant`​ sets with this value for all dependents. For this scenario, the field value of ​`RelationshipToInsured`​​ is based on what is passed from the `GroupCensusMember`, for example - Spouse, Child, Parent. ​

The default value is ​Member​​. ​

 |
| `isBatchMode` | 

Used to create policies asynchronously.

Default value is `true`.

 |
| `​​​primaryRoleName`​​​ | 

The ​Role​ field in `​InsurancePolicyParticipant​​` sets with this value for primary members. The field value of ​`RelationshipToInsured`​​ is Self in this scenario.​

 |
| `saveMemberPremium` | 

Indicates if the policy premium amount must be set for all `InsurancePolicyParticipant` records.

If the value is true, the policy member premium is stored in the field `TotalStandardAmount` of the object `InsurancePolicyParticipant` for all the associated Insurance Policy Participants of a policy.

The default value is false.

 |

## Output JSON

The service returns the list of policies. ​

<table class="slds-table slds-table_bordered slds-m-bottom_small" lwc-3eigj2skqo3=""><colgroup lwc-3eigj2skqo3=""><col style="width:50%" lwc-3eigj2skqo3=""><col style="width:50%" lwc-3eigj2skqo3=""></colgroup><tbody lwc-3eigj2skqo3=""><tr class="" lwc-3eigj2skqo3=""><td style="vertical-align:top;" class="slds-cell-wrap" lwc-3eigj2skqo3=""><code lwc-3eigj2skqo3="">​​​policyIds​​​</code></td><td style="vertical-align:top;" class="slds-cell-wrap" lwc-3eigj2skqo3="">​​​InsurancePolicy​​ record ID.</td></tr></tbody></table>

```
{
   "policyIds":[
      "0036F00002Q4wlSQAR",
      "0036F00002Q4wlSQAQ"
   ]
}
```

Did this article solve your issue?

Let us know so we can improve!

YesNo