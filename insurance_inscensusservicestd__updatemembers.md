---
title: "InsCensusServiceStd:updateMembers"
source: "https://help.salesforce.com/s/articleView?id=ind.insurance_inscensusservicestd__updatemembers.htm&language=en_US&type=5"
scraped: "2026-04-14"
filter: "ind.insurance_"
---# InsCensusServiceStd:updateMembers

InsCensusServiceStd:updateMembers[](https://help.salesforce.com/s?language=en_US)

You are here:

1.  [Salesforce Help](/s/?language=en_US)
2.  [Docs](/s/products?language=en_US)
3.  [Digital Insurance](https://help.salesforce.com/s/articleView?id=ind.insurance_admin_standard.htm&language=en_US&type=5)

# InsCensusServiceStd:updateMembers

Use this service to update the values of existing members in a census.

Class: ​`InsCensusServiceStd`​​

Method: `updateMembers`

[](https://help.salesforce.com/s?language=en_US)

## How It Works

1.  This service takes the members from an input JSON and updates the census (as per the given `censusId`) with the new data.
    
2.  census JSON consists of two lists - `headers` and `members`.
    
    1.  `headers` is the list of fields' metadata comprising of `fieldId`, `type`, `label` and `name`. Here name is the field's API Name (with the namespace for managed package and custom fields).
        
    2.  `members` is the list of members to be updated in the census.
        
3.  The service looks for `updateById` field. It's a boolean field that decides the course of action for the service. The members can be updated in these two ways:
    
    1.  `updateMembers` by `MemberKey`
        
        This option is applicable when `updateById` is false. The members data must have a member key.
        
    2.  `updateMembers` by Id of `GroupCensusMember`
        
        This option is applicable when `updateById` is true. The members data must have a group census member Id.
        

## updateMembers by MemberKey

1.  The service parses the members' data with the fields provided in `headers`. `headers` must contain all the fields' metadata used in the members' list.
    
2.  The service separates primary members and dependent members based on `RelationshipToPrimaryMember`.
    
    1.  If the members list contains primary members and dependents, the input must have `SourceSystemIdentifier` for all of the members. All the members must have a unique `SourceSystemIdentifier`. Additionally, all the dependents must have `PrimaryMemberSource` or `PrimaryGroupCensusMemberId` (If the primary member is already present in the census).
        
    2.  If the list is a combination of primary and dependent members, then ensure every dependent member and primary member exists in members' list.
        
3.  The service processes new `GroupClass`. If the service has `GroupClass.Name` instead of `GroupClassId`, then it fetches `GroupClass` with the name and creates a new `GroupClass` with the same name if not found.
    
    1.  If the service has `GroupClass.Name`, then also include `AccountId` in the members' data.
    2.  `header` for `GroupClass.Name`: `{"type":"STRING","label":"Group Class Name","fieldId":"","name":"GroupClass.Name"}`.
        
    3.  If the given `GroupClass.Name` is invalid, an error is returned. The service takes a new parameter `quoteEffectiveDate` to validate `GroupClass`. The `GroupClass` is considered valid if:
        
        -   `GroupClass` is linked to member's group account.
            
        -   `quoteEffectiveDate` lies between `GroupClass` `StartDate` and `EndDate`. If `quoteEffectiveDate` is not provided as a parameter to the service, then this validation is skipped.
            
4.  The services processes `PrimaryMemberSource` for dependents with `PrimaryGroupCensusMemberId`.
    
    1.  If the service has both `PrimaryMemberSource` and `PrimaryGroupCensusMemberId`, then service considers `PrimaryGroupCensusMemberId` as source and updates `PrimaryMemberSource` of dependent to contain `SourceSystemIdentifier` of primary.
        
5.  The service saves all Primary Members first.
    
6.  It parses dependents to identify orphan dependents (Dependents without `PrimaryMemberSource`).
    
7.  It saves all valid dependents.
    
8.  The service updates `DependentCount` of all primary members in the members' list.
    

## updateMembers by Id

1.  The service parses the members' data with the fields provided in `headers`. `headers` must contain all the fields' metadata used in the members list.
    
2.  `members` data must have Id. If the Id is not found in member data, then the service throws an error.
    
3.  The service processes new `GroupClass`. If the service has `GroupClass.Name` instead of `GroupClassId`, then it fetches `GroupClass` with the name and creates a new `GroupClass` with the same name if not found.
    
    1.  If the service has `GroupClass.Name`, then also include `AccountId` in the members' data.
    2.  `header` for `GroupClass.Name`: `{"type":"STRING","label":"Group Class Name","fieldId":"","name":"GroupClass.Name"}`.
        
4.  The service processes `PrimaryGroupCensusMemberId` for dependents with `PrimaryMemberSource`.
    
    1.  If you provide `PrimaryMemberSource`, then the service also updates `PrimaryGroupCensusMemberId`.
5.  The services processes `PrimaryMemberSource` for dependents with `PrimaryGroupCensusMemberId`.
    
    1.  If the service has both `PrimaryMemberSource` and `PrimaryGroupCensusMemberId`, then service considers `PrimaryGroupCensusMemberId` as source and updates `PrimaryMemberSource` of dependent to contain `SourceSystemIdentifier` of primary.
        
6.  The service saves all members including dependents.
    
7.  The service doesn't identify orphan dependents.
    
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

Required.

Id of the census with members to update.

 |
| 

`census`

 | 

Required.

Input JSON with details for members to be updated.

 |
| `updateById` | 

Optional

If set true, then service follows `updateMembers` by Id flow.

The default value is false.

 |

## Service Behavior

Understand how different inputs affect the service outputs.

| Input | updateById | Service Output |
| --- | --- | --- |
| No `censusId` | true or false | 
The service returns an error: `Specify a censusId.`

 |
| No census input JSON | true or false | The service returns an error: `The census input is missing.` |
| The value of `PrimaryMemberSource` provided to primary member | false | The service returns an error: `The PrimaryMemberSource must be null for primary members.` |
| `headers` is missing in Input census | true or false | The service returns an error: `The header node is missing in the census input.` |
| `members` is missing in Input census | true or false | The service returns an error: `The members node is missing in the census input.` |
| For orphan dependents (The dependents with no PrimaryMemberSource or PrimaryGroupCensusMemberId) | false | The service returns an error: `Dependent has no primary member.` |
| Id is missing in members' data | true | The service returns an error: `Specify Id of the census member.` |

[](https://help.salesforce.com/s?language=en_US)

## Input JSON

The input JSON includes `headers`, which lists the fields to be updated; and `members`, which lists members with their corresponding field-value pairs, including `fieldId`.

**Sample Input JSON (updateMembers By MemberKey)**

```json
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
        "Email": "testrajUpdated@mail.com"
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
        "Email": "testkrisUpdated@mail.com"
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
        "Email": "testchristopherUpdated@mail.com"
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
        "Email": "teststephUpdated.com"
      }
    ]
  }
}
```

**Sample Input JSON (updateMembers By Id)**

[](https://help.salesforce.com/s?language=en_US)`{   "census": {     "headers": [       {         "type": "STRING",         "label": "Last Name",         "fieldId": "",         "name": "Lastname"       },       {         "type": "STRING",         "label": "First Name",         "fieldId": "",         "name": "FirstName"       },       {         "type": "DOUBLE",         "label": "FTE",         "fieldId": "",         "name": "FullTimeEquivalent"       },       {         "type": "PICKLIST",         "label": "Gender",         "fieldId": "",         "name": "Gender"       },       {         "type": "DATE",         "label": "Birthday",         "fieldId": "",         "name": "Birthdate"       },       {         "type": "PICKLIST",         "label": "Relationship To Primary",         "fieldId": "",         "name": "RelationshipToPrimaryMember"       },       {         "type": "BOOLEAN",         "label": "Is Opt-out All Plans",         "fieldId": "",         "name": "IsOptOutAllPlans"       },       {         "type": "MULTIPICKLIST",         "label": "Opt-Out Plan Types",         "fieldId": "",         "name": "OptOutPlanTypes"       },       {         "type": "ENTITYID",         "label": "Account",         "fieldId": "",         "name": "AccountId"       },       {         "type": "EMAIL",         "label": "Email",         "fieldId": "",         "name": "Email"       },       {         "type": "STRING",         "label": "Primary Member Identifier",         "fieldId": "",         "name": "PrimaryMemberSource"       },       {         "type": "STRING",         "label": "Member Identifier",         "fieldId": "",         "name": "SourceSystemIdentifier"       }     ],     "members": [       {         "Id":"0r6RO00000005pZYAQ",         "Lastname": "KoffinsUpdatedById",         "FirstName": "RajUpdatedById",         "Birthdate": "1965-10-13",         "Email": "testrajUpdated@mail.com"       },       {         "Id":"0r6RO00000005pbYAA",         "Lastname": "Koffins",         "FirstName": "KrisUpdatedById",         "Gender": "Male",         "Birthdate": "2010-05-13",         "RelationshipToPrimaryMember": "Child",         "Email": "testkrisUpdatedById@mail.com"       },       {         "Id":"0r6RO00000005paYAA",         "Lastname": "WarnerUpdatedById",         "FirstName": "Christopher",         "FullTimeEquivalent": 0.75,         "Gender": "Male",         "Birthdate": "1985-10-13",         "Email": "testchristopherUpdatedById@mail.com"       },       {         "Lastname": "WarnerUpdatedById",         "FirstName": "Steph",         "Birthdate": "1985-10-13",         "Email": "teststephUpdated.com"       }     ]   } }`

[](https://help.salesforce.com/s?language=en_US)

## Output JSON

The service returns success message if the flow is completed, else it returns the error in case of any exceptions.

-   `censusMemberIds`: The list of `GroupCensusMemberIds` of saved members. ​ ​ ​
    
-   errors: The list of members with errors. Each list item consists of input member data and error.
    
-   `​ ​ ​ relatedFieldsUpdateSuccessCount`: Number of primary members for whom the `DependentCount` is updated by service.
    
-   ​ ​ ​ `relatedFieldsUpdateErrorCount`: Number of primary members for whom the `DependentCount` update returns errors. ​ ​ ​
    
-   `relatedFieldsUpdateErrors`: The list of errors returned while updating `DependentCount` of primary members.
    

**Sample Output JSON (updateMembers By MemberKey**)

```json
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
      "PrimaryMemberSource": "2.primary"
    }
  ],
  "censusMemberIds": [
    "0r6RO00000005pZYAQ",
    "0r6RO00000005paYAA",
    "0r6RO00000005pbYAA"
  ],
  "deletedCensusMemberIds": [],
  "errorCode": "INVOKE-200",
  "error": "OK"
}
```

**Sample Output JSON - (updateMembers By Id**)

[](https://help.salesforce.com/s?language=en_US)`{   "result": "success",   "relatedFieldsUpdateErrors": [],   "relatedFieldsUpdateErrorCount": 0,   "relatedFieldsUpdateSuccessCount": 2,   "errors": [     {       "error": "Specify Id of the census member.",       "Birthdate": "1985-10-13",       "Lastname": "WarnerUpdatedById",       "FirstName": "Steph",       "Email": "teststephUpdated.com"     }   ],   "censusMemberIds": [     "0r6RO00000005pZYAQ",     "0r6RO00000005pbYAA",     "0r6RO00000005paYAA"   ],   "errorCode": "INVOKE-200",   "error": "OK" }`

Did this article solve your issue?

Let us know so we can improve!

YesNo