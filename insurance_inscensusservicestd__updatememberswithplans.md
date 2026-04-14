---
title: "InsCensusServiceStd:updateMembersWithPlans"
source: "https://help.salesforce.com/s/articleView?id=ind.insurance_inscensusservicestd__updatememberswithplans.htm&language=en_US&type=5"
scraped: "2026-04-14"
filter: "ind.insurance_"
---# InsCensusServiceStd:updateMembersWithPlans

InsCensusServiceStd:updateMembersWithPlans[](https://help.salesforce.com/s?language=en_US)

You are here:

1.  [Salesforce Help](/s/?language=en_US)
2.  [Docs](/s/products?language=en_US)
3.  [Digital Insurance](https://help.salesforce.com/s/articleView?id=ind.insurance_admin_standard.htm&language=en_US&type=5)

# InsCensusServiceStd:updateMembersWithPlans

Use this service to populate a group census with primary members, their dependents, and their pre-enrolled plan. This service updates existing _`GroupCensusMember`_ by `memberKey` and creates _`GroupCensusMemberPlan`_ records for existing _`GroupCensusMember`_ records. It uses the _`ContractGroupPlans`_ specified in the input JSON to update plans for each _`GroupCensusMember`_.

Class: ​`InsCensusService​​Std`

Method: `updateMembersWithPlans`

[](https://help.salesforce.com/s?language=en_US)

## How It Works

1.  The service passes censusId and census input JSON to update members with plans.
    
2.  census JSON consists of two lists - `headers` and `members`.
    
    1.  `headers` is the list of fields' metadata comprising of `fieldId`, `type`, `label` and `name`. Here name is the field's API Name (with the namespace for managed package and custom fields). The `headers` must contain `ContactGroupPlanId.`
        
    2.  `members` is the list of members to be updated in the census. The `members` must contain `ContactGroupPlanId` separated by semicolon(;) for multiple plans.
        
3.  The service calls `updateMembers` by MemberKey to save data about the members, parsing through the members in the JSON object.
    
4.  The service adds `isNewMember` as true for all new members. It also populates Id for each GroupCensusMember.
    
5.  The service then calls `InsCensusServiceStd: addPlanSelections` to create `GroupCensusMemberPlan` for each member. It also accepts optional coverages per member so that primary members and dependents are enrolled into different coverages under the same plan.
    

## updateMembers by MemberKey

1.  The service parses the members' data with the fields provided in `headers`. `headers` must contain all the fields' metadata used in the members' list.
    
2.  The service separates primary members and dependent members based on `RelationshipToPrimaryMember`.
    
    1.  If the members list contains primary members and dependents, the input must have `SourceSystemIdentifier` for all of the members. All the members must have a unique `SourceSystemIdentifier`. Additionally, all the dependents must have `PrimaryMemberSource` or `PrimaryGroupCensusMemberId` (If the primary member is already present in the census).
        
    2.  If the list is a combination of primary and dependent members, then ensure every dependent member and primary member exists in members' list.
        
3.  The service processes new `GroupClass`. If the service has `GroupClass.Name` instead of `GroupClassId`, then it fetches `GroupClass` with the name and creates a new `GroupClass` with the same name if not found.
    
    1.  If the service has `GroupClass.Name`, then also include `AccountId` in the members' data.
    2.  `header` for `GroupClass.Name`: `{"type":"STRING","label":"Group Class Name","fieldId":"","name":"GroupClass.Name"}`.
        
    3.  If the provided `GroupClass` is invalid, an error is returned. The `GroupClass` is considered valid if:
        
        -   `GroupClass` is linked to member's group account.
            
        -   The contract's effective period is between `StartDate` and `EndDate` of `GroupClass`.
            
        -   The contract's `StartDate` and `EndDate` is fetched using `ContractId` provided as an input to service
            
4.  The services processes `PrimaryMemberSource` for dependents with `PrimaryGroupCensusMemberId`.
    
    1.  If the service has both `PrimaryMemberSource` and `PrimaryGroupCensusMemberId`, then service considers `PrimaryGroupCensusMemberId` as source and updates `PrimaryMemberSource` of dependent to contain `SourceSystemIdentifier` of primary.
        
5.  The service saves all Primary Members first.
    
6.  It parses dependents to identify orphan dependents (Dependents without `PrimaryMemberSource`).
    
7.  It saves all valid dependents.
    
8.  The service updates `DependentCount` of all primary members in the members' list.
    

[](https://help.salesforce.com/s?language=en_US)

## Remote Options

| 
Option

 | 

Description

 |
| --- | --- |
| 

`censusId` 

 | 

Required

Id of the census with members to update.

Validates that the `contractId` belongs to the account/census.

 |
| 

`census`

 | 

Required.

Input JSON with details for members to be updated.

 |
| 

`contractId` 

 | 

Required

Id of Account's current contract.

Validates that the plans of each member is part of the contract.

 |
| 

`onlySaveMembersWithValidProducts`

 | 

Boolean

If true, new members without entries in `GroupCensusMemberPlan` are deleted.

 |
| 

`duplicateKeys`

 | 

Optional

List of fields for `MemberKey` generation to identify existing members.

Default fields in the list: `FirstName`, `Lastname`, `Email`, `GroupCensusId`.

 |

| Input | Service Output |
| --- | --- |
| No `censusId` | The service returns an error: `Specify a censusId.` |
| 
No census input JSON

 | 

The service returns an error: `The census input is missing.`

 |
| `PrimaryMemberSource` value provided to primary member | The service returns an error: `The PrimaryMemberSource must be null for primary members.` |
| `headers` is missing in Input census | The service returns an error: `The header node is missing in the census input.` |
| `members` is missing in Input census | The service returns an error: `The members node is missing in the census input.` |
| For Orphan dependents (The dependents without `PrimaryMemberSource` or `PrimaryGroupCensusMemberId`) | The service returns an error: `Dependent has no primary member.` |
| 

No contractId or invalid contractId

 | 

The service updates no member plan.

 |
| Invalid `ContractGroupPlanId` for the contract specified | 

The service creates no member plan.

If `onlySaveMembersWithValidProducts` is true and the member is new, the service does the following:

-   Deletes the member with no valid plans.
-   Creates a member if it has at least one valid plan.

 |
| Invalid `ContractGroupPlanId` for the member (due to opt-out) | 

Member plan is not created

If `onlySaveMembersWithValidProducts` is true and the member is new, the service does the following:

-   Deletes the member with no valid plans.
-   Creates a member if it has at least one valid plan.

 |
| The primary member opts out of a product type | 

`IsOptOutAllPlans` takes precedence, followed by `OptOutPlanTypes`

-   If `IsOptOutAllPlans` = true, the service doesn't create a member plan even if you specify a product for enrollment.
-   If `IsOptOutAllPlans` = false and a product is specified for member enrollment, but its product type is the same as the opt-out entry, then the service doesn't creates a member plan.

If the primary member opts out of a product type, the dependents also opt out of that product type.

 |
| Dependent member opts out of a product type | 

`IsOptOutAllPlans` takes precedence, followed by `OptOutPlanTypes`

-   If `IsOptOutAllPlans` = true, the service doesn't create a member plan even if you specify a product for enrollment.
-   If `IsOptOutAllPlans` = false and a product is specified for member enrollment, but if its product type is the same as the opt-out entry, the service doesn't create a member plan.

If the primary member opts out of a product type, the dependents also opt out of that product type.

If `IsOptOutAllPlans` = true for a primary member, the same output is applicable for the associated dependents.

 |

[](https://help.salesforce.com/s?language=en_US)

## Input JSON

Here's what the format looks like for the input JSON:

```
{
  "census": {
    "headers": [
      {
        "type": "STRING",
        "label": "Last Name",
        "fieldId": "",
        "name": "Lastname"
      },
      {
        "type": "STRING",
        "label": "First Name",
        "fieldId": "",
        "name": "FirstName"
      },
      {
        "type": "DOUBLE",
        "label": "FTE",
        "fieldId": "",
        "name": "FullTimeEquivalent"
      },
      {
        "type": "PICKLIST",
        "label": "Gender",
        "fieldId": "",
        "name": "Gender"
      },
      {
        "type": "DATE",
        "label": "Birthday",
        "fieldId": "",
        "name": "Birthdate"
      },
      {
        "type": "PICKLIST",
        "label": "Relationship To Primary",
        "fieldId": "",
        "name": "RelationshipToPrimaryMember"
      },
      {
        "type": "BOOLEAN",
        "label": "Is Opt-out All Plans",
        "fieldId": "",
        "name": "IsOptOutAllPlans"
      },
      {
        "type": "MULTIPICKLIST",
        "label": "Opt-Out Plan Types",
        "fieldId": "",
        "name": "OptOutPlanTypes"
      },
      {
        "type": "ENTITYID",
        "label": "Account",
        "fieldId": "",
        "name": "AccountId"
      },
      {
        "type": "EMAIL",
        "label": "Email",
        "fieldId": "",
        "name": "Email"
      },
      {
        "type": "STRING",
        "label": "Primary Member Identifier",
        "fieldId": "",
        "name": "PrimaryMemberSource"
      },
      {
        "type": "STRING",
        "label": "Member Identifier",
        "fieldId": "",
        "name": "SourceSystemIdentifier"
      },
      {
        "type": "ENTITYID",
        "label": "Contract Group Plan",
        "fieldId": "",
        "name": "ContractGroupPlanId"
      }    
    ],
    "members": [
      {
        "MemberKey": "cd64a62573825ee11b87ce91110aa576",
        "Lastname": "KoffinsUpdated",
        "FirstName": "RajUpdated",
        "FullTimeEquivalent": 1,
        "Gender": "Male",
        "Birthdate": "1965-10-13",
        "SourceSystemIdentifier": "1.primary",
        "PrimaryMemberSource": null,
        "Email": "testrajUpdated@mail.com",
        "ContractGroupPlanId":"a4D4P000000hbjSUAQ;a4D4P000000hbjSUAQ"      
      },
      {
        "MemberKey": "f2f8735bbb66b3f7d7b2bae794c00650",
        "Lastname": "Koffins",
        "FirstName": "KrisUpdated",
        "Gender": "Male",
        "Birthdate": "2010-05-13",
        "RelationshipToPrimaryMember": "Child",
        "SourceSystemIdentifier": "1.child",
        "PrimaryMemberSource": "1.primary",
        "Email": "testkrisUpdated@mail.com",
        "ContractGroupPlanId":"a4D4P000000hbjSUAQ;a4D4P000000hbjSUAQ"      
      },
      {
        "Lastname": "WarnerUpdated",
        "MemberKey": "5a5bc4e3c05cf461a65a2d7fdc0ab8e0",
        "FirstName": "Christopher",
        "FullTimeEquivalent": 0.75,
        "Gender": "Male",
        "Birthdate": "1985-10-13",
        "SourceSystemIdentifier": "2.primary",
        "PrimaryMemberSource": null,
        "Email": "testchristopherUpdated@mail.com",
        "ContractGroupPlanId":"a4D4P000000hbjSUAQ;a4D4P000000hbjSUAQ"
      },
      {
        "Lastname": "WarnerUpdated",
        "MemberKey": "157b2052fc732d8261984c2922a3261b",
        "FirstName": "Steph",
        "Gender": "Male",
        "Birthdate": "1985-10-13",
        "RelationshipToPrimaryMember": "Spouse",
        "SourceSystemIdentifier": "2.spouse",
        "PrimaryMemberSource": "2.primary",
        "Email": "teststephUpdated.com",
        "ContractGroupPlanId":"a4D4P000000hbjSUAQ;a4D4P000000hbjSUAQ"
      }
    ]
  }
}
```

[](https://help.salesforce.com/s?language=en_US)

## Output JSON

The service returns success message if the flow is completed, else it returns the error in case of any exceptions.

-   `censusMemberIds`: The list of `GroupCensusMemberIds` of saved members. ​ ​ ​
    
-   errors: The list of members with errors. Each list item consists of input member data and error.
    
-   `​ ​ ​ relatedFieldsUpdateSuccessCount`: Number of primary members for whom the `DependentCount` is updated by service.
    
-   ​ ​ ​ `relatedFieldsUpdateErrorCount`: Number of primary members for whom the `DependentCount` updation returns errors. ​ ​ ​
    
-   `relatedFieldsUpdateErrors`: The list of errors returned while updating `DependentCount` of primary members.
    
-   `memberPlanIds`: The list of successfully inserted `GroupCensusMemberPlanIds`.
    

```
{
  "result": "success",
  "relatedFieldsUpdateErrors": [],
  "relatedFieldsUpdateErrorCount": 0,
  "relatedFieldsUpdateSuccessCount": 2,
  "errors": [
    {
      "error": "[Email]: INVALID_EMAIL_ADDRESS - Email: invalid email address: teststephUpdated.com",
      "Birthdate": "1985-10-13",
      "Gender": "Male",
      "Lastname": "WarnerUpdated",
      "RelationshipToPrimaryMember": "Spouse",
      "MemberKey": "157b2052fc732d8261984c2922a3261b",
      "SourceSystemIdentifier": "2.spouse",
      "FirstName": "Steph",
      "Email": "teststephUpdated.com",
      "PrimaryMemberSource": "2.primary",
      "ContractGroupPlanId":"a4D4P000000hbjSUAQ;a4D4P000000hbjSUAQ"
    }
  ],
  "censusMemberIds": [
    "0r6RO00000005pZYAQ",
    "0r6RO00000005paYAA",
    "0r6RO00000005pbYAA"
  ],
  "memberPlanIds":[
    "a4B4P000006jKsMUAU",
    "a4B4P000006jKsNUAU",
    "a4B4P000006jKsOUAU",
    "a4B4P000006jKsPUAU",
    "a4B4P000006jKsQUAU",
    "a4B4P000006jKsRUAU"
  ],
  "errorCode": "INVOKE-200",
  "error": "OK"
}
```

Did this article solve your issue?

Let us know so we can improve!

YesNo