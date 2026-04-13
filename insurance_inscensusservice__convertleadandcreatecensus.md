---
title: "InsCensusService:convertLeadAndCreateCensus"
source: "https://help.salesforce.com/s/articleView?id=ind.insurance_inscensusservice__convertleadandcreatecensus.htm&language=en_US&type=5"
scraped: "2026-04-13"
filter: "ind.insurance_ins"
---# InsCensusService:convertLeadAndCreateCensus

InsCensusService:convertLeadAndCreateCensus[](https://help.salesforce.com/s?language=en_US)

You are here:

1.  [Salesforce Help](/s/?language=en_US)
2.  [Docs](/s/products?language=en_US)
3.  [Digital Insurance](https://help.salesforce.com/s/articleView?id=ind.insurance_admin_standard.htm&language=en_US&type=5)

# InsCensusService:convertLeadAndCreateCensus

Use this service to extend the Lead Conversion Salesforce feature, allowing users to include Lead census information and map this data to the Vlocity Group Account Census objects while converting the Lead.

[](https://help.salesforce.com/s?language=en_US)

Class: `InsCensusService`

Method: `convertLeadAndCreateCensus`

[](https://help.salesforce.com/s?language=en_US)

## How It Works

When the `convertLeadtoAccount` option is used to convert a lead, the service converts `InsuredGroupCensus__c` to `GroupCensus__c` and `InsuredGroupCensusMembers` to `GroupCensusMembers__c`.

This service uses two objects:

-   InsuredGroupCensus\_\_c—This object captures the census at the lead stage. The census provides a statistical snapshot of eligible members of a group (such as employees) and their dependents. This census data is used to score leads in a marketing context.
    
    If the Lead is converted to an Account (using the Salesforce Lead to Account conversion process), the census can then be converted to the Account Census Vlocity objects as well and be used in quote ratings.
    
-   InsuredGroupCensusMember\_\_c—This object captures census members at the lead stage. It contains specific personal information about a census member (such as an employee) or dependent that is used by the insurance company to estimate the health care costs for the group.
    
    This object is the master-detail child object of the Insured Group Census object, above. This census data is only used for healthcare cost estimation after the corresponding `GroupCensus__c` and `GroupCensusMember__c` data is created from these sources (that is, `InsuredGroupCensus__c` and `InsuredGroupCensusMember__c`.
    

So here's how the service works:

1.  The service takes the `insuredCensusId` as an Input and uses it to retrieve the `InsuredGroupCensus__`c object.
    
2.  If the `convertLeadToAccount` remote option is true, it converts the attached `LeadId__c` into an Account; otherwise, it requires the `accountId` as an input.
    
3.  The service then creates a `GroupCensus__c`, with a type Group, using the `InsuredGroupCensus__c`.
    
    Vlocity fieldMappers are used here. There are two maps for this service: a map for `InsuredGroupCensus__c` to `GroupCensus__c`; and a map for `InsuredGroupCensusMember__c` to `GroupCensusMember__c`.
    
    If the mapping configuration is not present, the `GroupCensus__c` record is created based on specific fields from the `InsuredGroupCensus__c` object.
    
    Mapping for `InsuredGroupCensusMember__c` to `GroupCensusMember__c` is as follows:
    
    | 
    InsuredGroupCensusMember\_\_c
    
     | 
    
    GroupCensusMember\_\_c
    
     |
    | --- | --- |
    | 
    
    Name
    
     | 
    
    Name
    
     |
    | 
    
    FirstName\_\_c
    
     | 
    
    FirstName\_\_c
    
     |
    | 
    
    LastName\_\_c
    
     | 
    
    LastName\_\_c
    
     |
    | 
    
    BirthDate\_\_c
    
     | 
    
    BirthDate\_\_c
    
     |
    | 
    
    isPrimaryMember\_\_c
    
     | 
    
    isPrimaryMember\_\_c
    
     |
    | 
    
    NumberOfDependents\_\_c
    
     | 
    
    NumberOfDependents\_\_c
    
     |
    | 
    
    Gender\_\_c
    
     | 
    
    Gender\_\_c
    
     |
    | 
    
    Id
    
     | 
    
    MemberIdentifier\_\_c
    
     |
    | 
    
    RelatedInsuredCensusMemberId\_\_c
    
     | 
    
    PrimaryMemberIdentifier\_\_c
    
     |
    
    Mapping for `InsuredGroupCensus__c` to `GroupCensus__c` is as follows:
    
    | 
    InsuredGroupCensus\_\_c
    
     | 
    
    GroupCensus\_\_c
    
     |
    | --- | --- |
    | 
    
    Name
    
     | 
    
    Name
    
     |
    | 
    
    EffectiveStartDate\_\_c
    
     | 
    
    EffectiveStartDate\_\_c
    
     |
    | 
    
    EffectiveEndDate\_\_c
    
     | 
    
    EffectiveEndDate\_\_c
    
     |
    | 
    
    CensusSource\_\_c
    
     | 
    
    CensusSource\_\_c
    
     |
    | 
    
    AccountId From Inputs Or Converted From Lead
    
     | 
    
    GroupId\_\_c
    
     |
    | 
    
    CensusType\_\_c
    
     | 
    
    Group
    
     |
    | 
    
    RecordTypeName of InsuredGroupCensus\_\_c to get RecordTypeId of GroupCensus\_\_c then map that ID as RecordTypeId in GroupCensus\_\_c.
    
     |
    
4.  The service then uses the `GroupCensus__c` ID, as generated in the previous step, to create `GroupCensusMember__c` records from the source `InsuredGroupCensusMember__c` records. The `GroupCensusMember__c` records are created as children of the `GroupCensus__c` record, as created in the previous step.
    
    Note
    
    The `RelatedInsuredGroupCensusMemberId__c` field must be properly set in the `InsuredGroupCensusMember__c` records. This ensures that the mapping from dependent to primary works as expected.
    
    For every dependent, this must be set to the ID of the `InsuredGroupCensusMember__c` record which represents the corresponding primary member.
    
5.  The service then maps the dependents using the aforementioned fields.
    

If the following custom field mappings do not exist, they're mapped explicitly in the code:

| 
InsuredGroupCensusMember\_c

 | 

GroupCensusMember\_c

 |
| --- | --- |
| 

Id

 | 

MemberIdentifier\_\_c

 |
| 

IsPrimaryMember\_c

 | 

IsPrimaryMember\_c

 |
| 

RelatedInsuredCensusMemberId\_c

 | 

PrimaryMemberIdentifier\_c

 |
| 

NumberOfDependents\_c

 | 

NumberOfDependents\_c

 |

[](https://help.salesforce.com/s?language=en_US)

## Inputs

| 
Option

 | 

Description

 |
| --- | --- |
| 

`insuredGroupCensusId`

 | 

Required.

Id of the `InsuredGroupCensus__c` to be converted.

 |
| 

`accountId`

 | 

Optional.

Id of the Account the Census will be attached to.

This is ignored if the boolean value of `convertLeadToAccount`is true. In such a case, the new Census records are attached to the new Account created in the process.

 |

[](https://help.salesforce.com/s?language=en_US)

## Remote Options

| 
Option

 | 

Description

 |
| --- | --- |
| 

`convertLeadToAccount`

 | 

Boolean value.

If true, convert the lead attached to the `InsuredGroupCensus__c` into an Account.

 |
| 

`recordTypeName`

 | 

String.

String name of the Account Record type.

 |

[](https://help.salesforce.com/s?language=en_US)

## Input JSON

Here's a sample input JSON using `accountId` and `insuredCensusId`.

```
{
  "ContextId": "",
  "timeStamp": "2020-03-25T07:42:51.868Z",
  "userId": "0056g000003cVLZAA2",
  "userName": "ins-test09@vlocity.com",
  "userProfile": "System Administrator",
  "userTimeZone": -420,
  "userCurrencyCode": "USD",
  "sfdcIFrameOrigin": "https://ins-test09-dev-ed--instest09.visualforce.com",
  "sfdcIFrameHost": "web",
  "layout": "lightning",
  "isdtp": "p1",
  "id": "a236g000000NAibAAG",
  "vlcPersistentComponent": {},
  "accountId": "0016g00000Ir5LsAAJ",
  "insuredCensusId": "a5l6g000000RYasAAG"
}
```

[](https://help.salesforce.com/s?language=en_US)

## Output JSON

Here is a sample output JSON, with the `GroupCensus__c` information and the `GroupCensusMember__c` list with its information.

```
{
  "ContextId": "",
  "timeStamp": "2020-03-25T07:42:51.868Z",
  "userId": "0056g000003cVLZAA2",
  "userName": "ins-test09@vlocity.com",
  "userProfile": "System Administrator",
  "userTimeZone": -420,
  "userCurrencyCode": "USD",
  "sfdcIFrameOrigin": "https://ins-test09-dev-ed--instest09.visualforce.com",
  "sfdcIFrameHost": "web",
  "layout": "lightning",
  "isdtp": "p1",
  "id": "a236g000000NAibAAG",
  "vlcPersistentComponent": {},
  "accountId": "0016g00000Ir5LsAAJ",
  "insuredCensusId": "a5l6g000000RYasAAG",
  "censusMembers": [
    {
      "attributes": {
        "type": "instest09__GroupCensusMember__c",
        "url": "/services/data/v48.0/sobjects/instest09__GroupCensusMember__c/a4N6g0000013CP4EAM"
      },
      "Name": "Primary 1",
      "instest09__CensusId__c": "a4O6g000000AuJBEA0",
      "instest09__FirstName__c": "Primary",
      "instest09__LastName__c": "Primary",
      "instest09__Birthdate__c": "2020-03-03",
      "instest09__IsPrimaryMember__c": true,
      "instest09__MemberType__c": "Full Time",
      "instest09__NumberOfDependents__c": 0,
      "instest09__Gender__c": "Male",
      "instest09__MemberIdentifier__c": "a5k6g000000T7REAA0",
      "instest09__PrimaryMemberIdentifier__c": null,
      "Id": "a4N6g0000013CP4EAM"
    },
    {
      "attributes": {
        "type": "instest09__GroupCensusMember__c",
        "url": "/services/data/v48.0/sobjects/instest09__GroupCensusMember__c/a4N6g0000013CP5EAM"
      },
      "Name": "Dependent Child",
      "instest09__CensusId__c": "a4O6g000000AuJBEA0",
      "instest09__FirstName__c": "Child 1",
      "instest09__LastName__c": "Chila 1",
      "instest09__Birthdate__c": "2020-03-12",
      "instest09__IsPrimaryMember__c": true,
      "instest09__MemberType__c": null,
      "instest09__NumberOfDependents__c": 0,
      "instest09__Gender__c": "Male",
      "instest09__MemberIdentifier__c": "a5k6g000000T7RTAA0",
      "instest09__PrimaryMemberIdentifier__c": "a5k6g000000T7REAA0",
      "Id": "a4N6g0000013CP5EAM"
    },
    {
      "attributes": {
        "type": "instest09__GroupCensusMember__c",
        "url": "/services/data/v48.0/sobjects/instest09__GroupCensusMember__c/a4N6g0000013CP6EAM"
      },
      "Name": "Primary 2",
      "instest09__CensusId__c": "a4O6g000000AuJBEA0",
      "instest09__FirstName__c": "Primary 2",
      "instest09__LastName__c": "Primary 2",
      "instest09__Birthdate__c": "2020-03-04",
      "instest09__IsPrimaryMember__c": true,
      "instest09__MemberType__c": null,
      "instest09__NumberOfDependents__c": 0,
      "instest09__Gender__c": "Male",
      "instest09__MemberIdentifier__c": "a5k6g000000T7RJAA0",
      "instest09__PrimaryMemberIdentifier__c": null,
      "Id": "a4N6g0000013CP6EAM"
    },
    {
      "attributes": {
        "type": "instest09__GroupCensusMember__c",
        "url": "/services/data/v48.0/sobjects/instest09__GroupCensusMember__c/a4N6g0000013CP7EAM"
      },
      "Name": "Dependent Spouse",
      "instest09__CensusId__c": "a4O6g000000AuJBEA0",
      "instest09__FirstName__c": "Spouse 1",
      "instest09__LastName__c": "Spouse 1",
      "instest09__Birthdate__c": "2020-03-12",
      "instest09__IsPrimaryMember__c": true,
      "instest09__IsSpouse__c": true,
      "instest09__MemberType__c": null,
      "instest09__NumberOfDependents__c": 0,
      "instest09__Gender__c": "Female",
      "instest09__MemberIdentifier__c": "a5k6g000000T7ROAA0",
      "instest09__PrimaryMemberIdentifier__c": "a5k6g000000T7REAA0",
      "Id": "a4N6g0000013CP7EAM"
    }
  ],
  "censusMemberCount": 4,
  "census": {
    "attributes": {
      "type": "instest09__GroupCensus__c",
      "url": "/services/data/v48.0/sobjects/instest09__GroupCensus__c/a4O6g000000AuJBEA0"
    },
    "Name": "Test Insured Census",
    "instest09__EffectiveStartDate__c": "2020-03-26",
    "instest09__EffectiveEndDate__c": "2020-03-26",
    "instest09__CensusSource__c": "External",
    "instest09__GroupId__c": "0016g00000Ir5LsAAJ",
    "instest09__CensusType__c": "Group",
    "Id": "a4O6g000000AuJBEA0"
  },
  "error": "OK"
}
```

Did this article solve your issue?

Let us know so we can improve!

YesNo