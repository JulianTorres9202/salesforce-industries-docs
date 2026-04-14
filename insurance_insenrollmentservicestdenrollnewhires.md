---
title: "InsEnrollmentServiceStd:enrollNewHires"
source: "https://help.salesforce.com/s/articleView?id=ind.insurance_insenrollmentservicestdenrollnewhires.htm&language=en_US&type=5"
scraped: "2026-04-14"
filter: "ind.insurance_"
---# InsEnrollmentServiceStd:enrollNewHires

InsEnrollmentServiceStd:enrollNewHires[](https://help.salesforce.com/s?language=en_US)

You are here:

1.  [Salesforce Help](/s/?language=en_US)
2.  [Docs](/s/products?language=en_US)
3.  [Digital Insurance](https://help.salesforce.com/s/articleView?id=ind.insurance_admin_standard.htm&language=en_US&type=5)

# InsEnrollmentServiceStd:enrollNewHires

Enroll new census members into their selected plans in the middle of a contract term.

Class: `InsEnrollmentServiceStd`

Method: `enrollNewHires`

**Scenario**

| groupCensusID | contractID | groupCensusMemberIds | primaryRoleName | dependentRoleName |
| --- | --- | --- | --- | --- |
| groupCensusID1 | ctrlD1 | censusMemberPrimary1 | PolicyHolder |   |
| censusMemberDependent1 |   | Member |
| censusMemberDependent2 |   | Member |

| policyID | coverage | PolicyParticipant | policyParticipant.role |
| --- | --- | --- | --- |
| policyID101 | coverage1, coverage2 | censusMemberPrimary1 | self |
| censusMemberDependent1 | spouse |
| censusMemberDependent2 | child |

## How It Works

1.  The service searches for Group Census Members:
    1.  Either all members for a given `groupCensusId` or
    2.  Only those members specified in the `groupCensusMemberIds` list.
2.  Each primary `groupCensusMemberIds` of the group census should have the `PolicyStartDate` field mapped. The `PolicyStartDate` should fall in between the Contract Start Date and Contract End Date.
    1.  If any of the primary `groupCensusMemberIds` doesn't have the `PolicyStartDate` populated the service throws an error with a list of `groupCensusMemberIds` and a message: "Specify a valid date for `PolicyStartDate`."
    2.  If any of the primary `groupCensusMemberIds` has a `PolicyStartDate` that doesn't fall between the Contract Start Date and Contract End Date the service throws an error with a list of `groupCensusMemberIds` and a message: '"Specify a `PolicyStartDate` that's within the ContractStartDate and ContractEndDate."
3.  Once the service verifies all primary census members have the `PolicyStartDate` information it searches for the pre-enrolled plans linked to each member in the `GroupCensusMemberPlan`.
4.  The plan's products for each member are returned.
5.  If the product is eligible (it's a part of a `Contract` and `ContractGroupPlans`), an Insurance Policy is created.
6.  Insurance Policy Coverages (`InsurancePolicyCoverages`) are created for the coverage items specified in the plan.
7.  Person accounts can be created for the group census members in the group census. To support the Person Account flow, this service goes through group census members to do below things:
    1.  If `AccountIds` (retrieved from the `GroupCensusMember`) are available the service uses `AccountId` as `InsurancePolicy.NameInsured` and creates `InsurancePolicyParticipants' PrimaryParticipantAccountId` and `RelatedParticipantAccountId`.
    2.  If `AccountId` is null, the service uses the `groupAccountId` as `InsurancePolicy.NameInsured` and `contactId` as `InsurancePolicyParticipants' PrimaryParticipantContactId` and `RelatedParticipantContactId`.
8.  An Insurance Policy is created only for a primary member, not their dependent. The dependent details in the Insurance Policies are stored as:
    1.  The dependent information is created in a separate object called `InsurancePolicyParticipants`. A record is also created for the primary member. The service associates these records to the Insurance Policies.
    2.  Insurance Policy Participant's (`InsurancePolicyParticipant`) `primaryParticipantAccountId` and `relatedParticipantAccountId` fields are also populated using the `AccountId` field of the group census member and Contact fields when `AccountId` is null.
9.  The Insurance Policy's effective date will be same as the `PolicyStartDate` of the primary member.
10.  The Insurance Premium will be prorated based on the number of days the member is enrolled for within the contract term. For example: the total premium from the rating :16.00. Contract duration: 365 days (Start date: 10-jan-2023 to End date: 9-jan-2024)Member's policy start date : 28-Feb-2023Total days for the new hire in the contract: 316Prorated premium: 16\* (316/365) = 13.85
11.  Insurance Policy Coverages:
     1.  If a family member enrolls for an optional coverage during member enrollment, a separate `InsurancePolicyCoverage` record corresponds to each and every enrolled optional coverage. Each `InsurancePolicyCoverage` record corresponding to optional coverages stores the enrolled Insurance Policy Participant in the `vlocity_ins_fsc__InsurancePolicyParticipantId__c` field on the `InsurancePolicyCoverage` object.
     2.  There's a single `InsurancePolicyCoverage` record for mandatory coverages for a family per product.
12.  Insurance Policy Premium: If `saveMemberPremium` is set to `true`, the `InsurancePolicyParticipant` records contain the `StandardPremiumAmount` value of the policy. This amount is prorated (and is calculated the same way as the Insurance Premium in step 10).
     
     Note Configure the expression set or calculation procedure to set the member level premium amount to a `memberPremium` field the Include in Calculation output option set to true.
     

Configure the rating procedure to pass the effective dates as options into the expression set or calculation procedure.

-   Key for the expression set or calculation procedure remote option : `effectiveDate`
-   Value for the expression set or calculation procedure remote option: `%options:effectiveDate%`
-   What it does: This value is passed in as an option to the `InsProductService:getRatedProduct` service by this Integration Procedure. This data is used to pull the correct versions of the expression set or calculation procedure and matrices the Integration Procedure uses for rating.

## Remote Options

| Option | Description |
| --- | --- |
| `contractId` | 
Required.

The ID of the contract that the members belong to and the plans that they will be enrolled in `contractId`.

 |
| `dependentRoleName` | 

Optional.

Default value is `Member`.

The `Role` field in `InsurancePolicyParticipant` will follow this value for dependents. The `RelationshipToInsured` field will be Spouse, Child, Parent, etc based on what is passed from the `GroupCensusMember`

 |
| `groupCensusId` | 

Required if not using `groupCensusMembersIds`.

The ID of the census that contains all census members for enrollment.

 |
| `groupCensusMemberIds` | 

Required if not using `groupCensusId`.

A list of IDs of specific census members for enrollment, separated by commas.

 |
| `isBatchMode` | 

Optional.

Default value is `true`.

Creates policies asynchronously.

 |
| `primaryRoleName` | 

Optional.

Default value is `PolicyHolder`. The `Role` field in `InsurancePolicyParticipant` follows this value for primary members. The `RelationshipToInsured` field is Self for this case.

 |
| `saveMemberPremium` | 

Optional.

Default Value is `false`.

The value indicates the policy premium amount to be set for all `InsurancePolicyParticipant` records.

If the value is `true`, the policy member premium is stored in the T`otalStandardAmount` field of the `InsurancePolicyParticipant` object for all the associated Insurance Policy Participants of a policy.

 |

## Input JSON

Here's the sample input JSON:

```json
{
   "Input": {
    "groupCensusId": "0rfRO00000005OUYAY",
    "contractId": "800RO000000WG4mYAG"
  },
  "Options":{
    "isBatchMode":false
  }
 }
```

## Output JSON

Here's the sample output JSON:

```json
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