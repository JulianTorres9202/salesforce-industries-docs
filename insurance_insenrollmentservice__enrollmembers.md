---
title: "InsEnrollmentService:enrollMembers"
source: "https://help.salesforce.com/s/articleView?id=ind.insurance_insenrollmentservice__enrollmembers.htm&language=en_US&type=5"
scraped: "2026-04-14"
filter: "ind.insurance_"
---# InsEnrollmentService:enrollMembers

InsEnrollmentService:enrollMembers[](https://help.salesforce.com/s?language=en_US)

You are here:

1.  [Salesforce Help](/s/?language=en_US)
2.  [Docs](/s/products?language=en_US)
3.  [Digital Insurance](https://help.salesforce.com/s/articleView?id=ind.insurance_admin_standard.htm&language=en_US&type=5)

# InsEnrollmentService:enrollMembers

Use this service to enroll census members into their selected plans.

Important From Winter '23 onward, we have [InsEnrollmentServiceStd:enrollMembers](https://help.salesforce.com/s/articleView?id=ind.insurance_insenrollmentservicestd__enrollmembers.htm&language=en_US&type=5 "Use this service to enroll census members into their selected plans.") service enabled to work with Salesforce Standard Data Model for Financial Services Cloud and Health Cloud. Existing customers can continue to use this service, but no further enhancements will be provided in the Insurance Managed Package.

[](https://help.salesforce.com/s?language=en_US)Note

Enrollment services can either write to the Insurance Policy and related objects (Harmonized policy data model) or Asset objects (Vlocity model), depending on the `isFsc` parameter, and the custom setting for `defaultIsFSCOption`.

From the Vlocity Health and Insurance Summer '21 release onward, the service also supports the Person Account flow.

If you're using Vlocity Package Data Model, we don't support enrollment for products that are inactive or that have a future date set as the effective date.

[](https://help.salesforce.com/s?language=en_US)

Class: `InsEnrollmentService`

Method: `enrollMembers`

[](https://help.salesforce.com/s?language=en_US)

## How It Works

1.  The service first queries for Group Census Members either a) via all members for a given `censusId` or b) via only those members specified in the `censusMembersIds` list.  
    
2.  It then searches for pre-enrolled plans linked to each member by the Group Census Member Plan (`GroupCensusMemberPlan__c`). 
    
3.  The plans products for each member are returned. 
    
4.  If the product is part of the contract, then a policy record (Insurance Policy or Asset) is created. The type of policy that gets created, depends on the `isFsc` parameter, and the custom setting for `defaultIsFSCOption` as is described in this table.
    
    | 
    Custom Settings > Insurance Configuration Setup>defaultIsFSCOption
    
     | 
    
    IsFsc Parameter
    
     | 
    
    Policies Created
    
     |
    | --- | --- | --- |
    | 
    
    True
    
     | 
    
    NA
    
     | 
    
    InsurancePolicy
    
     |
    | 
    
    False
    
     | 
    
    True
    
     | 
    
    InsurancePolicy
    
     |
    | 
    
    False
    
     | 
    
    False
    
     | 
    
    Asset
    
     |
    | 
    
    NA
    
     | 
    
    True
    
     | 
    
    InsurancePolicy
    
     |
    | 
    
    NA
    
     | 
    
    False
    
     | 
    
    Asset
    
     |
    
5.  You can [create Person Accounts](https://help.salesforce.com/s/articleView?id=ind.insurance_inscensusservice__createaccounts.htm&language=en_US&type=5 "Use this service to create Person Accounts for the members in the given census.") for the members in the given census. To support the Person Account flow:
    
    This flow goes through census members.
    
    If `accountId` is not null, the service uses accountId as `Policy.NameInsured` and creates `InsurancePolicyParticipants`’ `PrimaryParticipantAccountId` and `RelatedParticipantAccountId`.
    
    If `accountId` is null, the service uses `groupAccountId` as `NameInsured` and `contactId` as `InsurancePolicyParticipants`’ `PrimaryParticipantContactId` and `RelatedParticipantContactId`.
    
    Note
    
    The Person Account is only enabled for Insurance Policy objects, not for Asset.
    
6.  Insurance Policy or Asset is created only for primary member and not its dependent. In order to specify the dependent details in the policies:
    
    1.  For Insurance Policy: The dependent information is created in a separate object called `InsurancePolicyParticipants`. A record is created for the Primary member as well.
        
    2.  For Assets: Dependents who are enrolled into the Asset are maintained in the `AssetPartyRelationship__c`. No record is created for Primary member in `AssetPartyRelationship__c`.
        
7.  For coverage items:
    
    1.  Insurance Policy: Service creates Insurance Policy Coverages (`InsurancePolicyCoverages`).
        
    2.  Asset: Service creates Policy Coverages (`AssetCoverage__c`).
        

[](https://help.salesforce.com/s?language=en_US)

## Remote Options

| 
Option

 | 

Description

 |
| --- | --- |
| 

`isFsc`

 | 

Determines whether to create the policies as Asset records or as InsurancePolicy records. The value of the parameter is honored:

-   If the `Custom Settings` > `Insurance Configuration Setup` has the `defaultIsFSCOption` set to `false`.
    
-   Or, if there’s no `defaultIsFSCOption`, the value of this parameter is taken.
    

 |
| 

`censusMemberIds`

 | 

Required if `censusId` isn’t used.

Id of the specific census members to be enrolled.

 |
| 

`censusId`

 | 

Required if `censusMemberIds` isn’t used.

Id of the census containing all census members to be enrolled.

 |
| 

`contractId`

 | 

Required.

Id of the contract that the members belong to and the plans that they’ll be enrolled in.

 |
| 

`dependentRoleName`

 | 

This option is only applicable to FSC policies. The default value is `Member`. The `Role` field in `InsurancePolicyParticipant` sets with this value, for all dependents.

 |
| 

`primaryRoleName`

 | 

This option is only applicable to FSC policies.

The default value is `Policyholder.`

The `Role` field in `InsurancePolicyParticipant` follows this value for primary members.

 |
| 

`spousalRelationshipName`

 | 

This option is only applicable to FSC policies.

The default value is `Dependent.`

The `RelationshipToInsured` field in `InsurancePolicyParticipant` follows this value for dependents who are tagged as spouses.

 |
| 

`memberPlanIntegrationProcedure`

 | 

[](https://help.salesforce.com/s?language=en_US)Initiates a custom integration procedure based on the user configuration. When you use this option, it passes all options of the service to the custom integration procedure and all policy Ids as input to integrate with the object, for example the insurance policy object with the member plan.

 |

[](https://help.salesforce.com/s?language=en_US)

## Output JSON

The list of policies created by the service.

| 
`assetIds`

 | 

`InsurancePolicy` record IDs if the service is creating FSC records, otherwise, these are Asset record IDs

 |
| --- | --- |
| 

`policyIds`

 | 

`InsurancePolicy` record IDs. This option doesn’t appear in Non-FSC records.

 |

```
{
   "assetIds":[
      {
         "assetId":"0036F00002Q4wlSQAR"
      },
      {
         "assetId":"0036F00002Q4wlSQAQ"
      }
   ],
   "policyIds":[
      "0036F00002Q4wlSQAR",
      "0036F00002Q4wlSQAQ"
   ]
}
```

Did this article solve your issue?

Let us know so we can improve!

YesNo