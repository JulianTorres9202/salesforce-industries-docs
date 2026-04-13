---
title: "InsCensusServiceStd:deleteMembers"
source: "https://help.salesforce.com/s/articleView?id=ind.insurance_inscensusservicestd__deletemembers.htm&language=en_US&type=5"
scraped: "2026-04-13"
filter: "ind.insurance_ins"
---# InsCensusServiceStd:deleteMembers

InsCensusServiceStd:deleteMembers[](https://help.salesforce.com/s?language=en_US)

You are here:

1.  [Salesforce Help](/s/?language=en_US)
2.  [Docs](/s/products?language=en_US)
3.  [Digital Insurance](https://help.salesforce.com/s/articleView?id=ind.insurance_admin_standard.htm&language=en_US&type=5)

# InsCensusServiceStd:deleteMembers

Use this service to delete the group census members.

Class: ​`InsCensusServiceStd​​`

Method: `deleteMembers`

[](https://help.salesforce.com/s?language=en_US)

## How It Works

The service uses `censusMemberIds` as the input parameter to retrieve the list of `GroupCensusMember` records and delete these records from the given census Id. It first deletes all the dependent members and then deletes the primary members.

Note

Primary members with dependents are not deleted.

[](https://help.salesforce.com/s?language=en_US)

## Remote Options

| 
Option

 | 

Description

 |
| --- | --- |
| 

`censusMemberIds`

 | 

Required.

List of `GroupCensusMember` record Ids which must be deleted.

 |

[](https://help.salesforce.com/s?language=en_US)

## Input JSON

Here's the sample input JSON:

IDs of `GroupCensusMember` records

```json
{      
    "censusMemberIds": [
        "0r6RO0000000430YAA",
        "0r6RO000000042vYAA"
    ]
}
```

Ids of `Contact` records

```json
{    
    "accountIds": [
        "003RO000002yi8iYAA",
        "003RO000002yi8dYAA"
    ]
}
```

## Output JSON

The service doesn't returns an output JSON. It deletes the group census member records as per the specified input.

Did this article solve your issue?

Let us know so we can improve!

YesNo