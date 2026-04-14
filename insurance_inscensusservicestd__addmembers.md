---
title: "InsCensusServiceStd:addMembers"
source: "https://help.salesforce.com/s/articleView?id=ind.insurance_inscensusservicestd__addmembers.htm&language=en_US&type=5"
scraped: "2026-04-14"
filter: "ind.insurance_"
---# InsCensusServiceStd:addMembers

InsCensusServiceStd:addMembers[](https://help.salesforce.com/s?language=en_US)

You are here:

1.  [Salesforce Help](/s/?language=en_US)
2.  [Docs](/s/products?language=en_US)
3.  [Digital Insurance](https://help.salesforce.com/s/articleView?id=ind.insurance_admin_standard.htm&language=en_US&type=5)

# InsCensusServiceStd:addMembers

Use this service to add group census members to a group census using an input JSON.

Class: ​`InsCensusServiceStd`​​

Method: `addMembers`

[](https://help.salesforce.com/s?language=en_US)

## How It Works

The service takes the members in census input JSON and adds them to the given ​`censusId​​`. It returns a list of the Ids of the added members (​`censusMemberIds`​​).

1.  The service parses the member data.
    
    1.  Parses members' data with the fields provided in headers. Headers must contain all the fields' metadata used in the member list. ​ ​ ​
        
    2.  Separates primary members and dependent members based on `RelationshipToPrimaryMember`. If the member list contains primary members and dependents, the input must have `SourceSystemIdentifier` for all of the members. All the members must have unique `SourceSystemIdentifier`. Additionally, all the dependents must have `PrimaryMemberSource` or `PrimaryGroupCensusMemberId` (If the primary member is already present in the census). ​ ​ ​
        
    3.  Generates `MemberKey`.
        
    4.  Processes new `GroupClass`. If `GroupClass.Name` is given to service instead of `GroupClassId`, then the service fetches `GroupClass` with the name and creates a new `GroupClass` with the same name if not found. The header for `GroupClass.Nam`e is {"type":"STRING","label":"Group Class Name","fieldId":"","name":"GroupClass.Name"}. If the given `GroupClass.Name` is invalid, an error is returned. The service takes a new parameter `quoteEffectiveDate` to validate `GroupClass`. The `GroupClass` is considered valid if:
        
        Note If `GroupClass.Name` is provided, then also include `AccountId` in members' data.
        
        -   `GroupClass` is linked to member's group account.
            
        -   `quoteEffectiveDate` lies between `GroupClass` `StartDate` and `EndDate`. If `quoteEffectiveDate` is not given as a parameter to service, then this validation is skipped.
            
    5.  Processes `PrimaryMemberSource` for dependents with `PrimaryGroupCensusMemberId`. If both `PrimaryMemberSource` and `PrimaryGroupCensusMemberId` are provided in member data, then service consumes `PrimaryGroupCensusMemberId` as source and updates `PrimaryMemberSource` of dependent to contain `SourceSystemIdentifier` of primary.
        
2.  Saves all Primary Members. The service uses `MemberKey` to identify duplicates. If there is a duplicate member, the service updates the fields of that pre-existing member. The `MemberKey` must be a unique combination of strings.
    
3.  Parses dependents to identify Orphan dependents (Dependents without `PrimaryMemberSource`).
    
4.  Saves all valid dependents. The service uses `MemberKey` to identify duplicates. In there is a duplicate member record, the service updates the fields of that pre-existing member instead of creating a new record.
    
5.  Updates `DependentCount` of all primary members in the member list.
    

## Service Behavior

Understand how different inputs affect the service outputs.

| Input | Service Output |
| --- | --- |
| No `censusId` | The service returns an error: `Specify a censusId.` |
| No census input JSON | The service returns an error: `The census input is missing.` |
| `PrimaryMemberSource` value provided to primary member | The service returns an error: `The PrimaryMemberSource must be null for primary members.` |
| `headers` is missing in Input census | The service returns an error: `The header node is missing in the census input.` |
| `members` is missing in Input census | The service returns an error: `The members node is missing in the census input.` |
| For Orphan dependents (The dependents without `PrimaryMemberSource` or `PrimaryGroupCensusMemberId`) | The service returns an error: `Dependent has no primary member.` |

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

Id of the group census to add members to.

 |
| 

`census`

 | 

Required.

Input JSON of the members to be added.

census JSON consists of two lists - headers and members. headers is the list of fields' metadata comprising of fieldId, type, label, and name. Here name is field's API Name (with namespace for managed package and custom fields). members is the list of members to be added to the census.

 |
| `duplicateKey` | 

Optional.

List of fields to generate `MemberKey` and identify duplicates. If no value is provided, the default fields included in the list are: `FirstName`, `Lastname`, `Email`, `GroupCensusId`.

 |

[](https://help.salesforce.com/s?language=en_US)

## Input JSON

The input JSON consists of two lists - headers and members. headers is the list of fields' metadata comprising of fieldId, type, label, and name. Here name is field's API Name (with namespace for managed package and custom fields). members is the list of members to be added to the census.

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
                "type":"MULTIPICKLIST",
                "label":"Opt-Out Plan Types",
                "fieldId":"",
                "name":"OptOutPlanTypes"
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
                "Lastname": "Koffins",
                "FirstName": "Raj",
                "FullTimeEquivalent": 1,
                "Gender": "Male",
                "Birthdate": "1985-10-13",
                "SourceSystemIdentifier": "1.primary",
                "PrimaryMemberSource": null,
                "Email": "testraj@mail.com",
                "AccountId":"001B000001QOqJHIA1",
                "IsOptOutAllPlans":true,
                "OptOutPlanTypes":"Medical;Dental"
            },
            {
                "Lastname": "Koffins",
                "FirstName": "Rita",
                "Gender": "Female",
                "Birthdate": "1987-07-13",               
                "RelationshipToPrimaryMember": "Spouse",
                "SourceSystemIdentifier": "1.spouse",
                "PrimaryMemberSource": null,
                "Email": "testrita@mail.com",
                "AccountId":"001B000001QOqJHIA1",
                "IsOptOutAllPlans":true,
                "OptOutPlanTypes":"Medical;Dental"
            },
            {
                "Lastname": "Koffins",
                "FirstName": "Kris",
                "Gender": "Male",
                "Birthdate": "2016-05-13",
                "RelationshipToPrimaryMember": "Child",
                "SourceSystemIdentifier": "1.child",
                "PrimaryMemberSource": "1.primary",
                "Email": "testkris@mail.com",
                "AccountId":"001B000001QOqJHIA1",
                "IsOptOutAllPlans":true,
                "OptOutPlanTypes":"Medical;Dental"
            },
            {
                "Lastname": "Warner",
                "FirstName": "Christopher",
                "FullTimeEquivalent": 0.5,
                "Gender": "Male",
                "Birthdate": "1985-10-13",
                "SourceSystemIdentifier": "2.primary",
                "PrimaryMemberSource": null,
                "Email": "testchristopher@mail.com",
                "AccountId":"001B000001QOqJHIA1",
                "IsOptOutAllPlans":false,
                "OptOutPlanTypes":"Medical"
            },
            {
                "Lastname": "Warner",
                "FirstName": "Steph",
                "Gender": "Male",
                "Birthdate": "1985-10-13",
                "RelationshipToPrimaryMember": "Spouse",
                "SourceSystemIdentifier": "2.spouse",
                "PrimaryMemberSource": "2.primary",
                "Email": "teststeph@mail.com",
                "AccountId":"001B000001QOqJHIA1",
                "IsOptOutAllPlans":false,
                "OptOutPlanTypes":"Medical"
            },
            {
                "Lastname": "Jose",
                "FirstName": "Steve",
                "Gender": "Male",
                "Birthdate": "1989-10-13",
                "FullTimeEquivalent":10,
                "SourceSystemIdentifier": "3.primary",
                "Email": "teststeve@mail.com",
                "AccountId":"001B000001QOqJHIA1",
                "IsOptOutAllPlans":false,
                "OptOutPlanTypes":"Medical"
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
    
-   ​ ​ ​ `relatedFieldsUpdateErrorCount`: Number of primary members for whom the `DependentCount` update returns errors. ​ ​ ​
    
-   `relatedFieldsUpdateErrors`: The list of errors returned while updating `DependentCount` of primary members.
    

```
{
  "result": "success",
  "relatedFieldsUpdateErrors": [],
  "relatedFieldsUpdateErrorCount": 0,
  "relatedFieldsUpdateSuccessCount": 2,
  "errors": [
    {
      "error": "[FullTimeEquivalent]: NUMBER_OUTSIDE_VALID_RANGE - Full Time Equivalent: value outside of valid range on numeric field: 10",
      "Birthdate": "1989-10-13",
      "Gender": "Male",
      "IsOptOutAllPlans": false,
      "Lastname": "Jose",
      "SourceSystemIdentifier": "3.primary",
      "FullTimeEquivalent": 10,
      "FirstName": "Steve",
      "AccountId": "001B000001QOqJHIA1",
      "Email": "teststeve@mail.com",
      "OptOutPlanTypes": "Medical"
    },
    {
      "RelationshipToPrimaryMember": "Spouse",
      "SourceSystemIdentifier": "1.spouse",
      "OptOutPlanTypes": "Medical;Dental",
      "PrimaryMemberSource": null,
      "error": "Dependent has no primary member.",
      "Birthdate": "1987-07-13",
      "Gender": "Female",
      "IsOptOutAllPlans": true,
      "Lastname": "Koffins",
      "FirstName": "Rita",
      "AccountId": "001B000001QOqJHIA1",
      "Email": "testrita@mail.com"
    }
  ],
  "censusMemberIds": [
    "0r6B00000000ANcIAM",
    "0r6B00000000ANdIAM",
    "0r6B00000000ANeIAM",
    "0r6B00000000ANfIAM"
  ],
  "errorCode": "INVOKE-200",
  "error": "OK"
}
```

Did this article solve your issue?

Let us know so we can improve!

YesNo