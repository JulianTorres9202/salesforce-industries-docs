---
title: "InsCensusServiceStd:deleteAllMembers"
source: "https://help.salesforce.com/s/articleView?id=ind.insurance_inscensusservicestddeleteallmembers.htm&language=en_US&type=5"
scraped: "2026-04-14"
filter: "ind.insurance_"
---# InsCensusServiceStd:deleteAllMembers

InsCensusServiceStd:deleteAllMembers[](https://help.salesforce.com/s?language=en_US)

You are here:

1.  [Salesforce Help](/s/?language=en_US)
2.  [Docs](/s/products?language=en_US)
3.  [Digital Insurance](https://help.salesforce.com/s/articleView?id=ind.insurance_admin_standard.htm&language=en_US&type=5)

# InsCensusServiceStd:deleteAllMembers

Use this service to delete all group census members of the group census passed as input into the service. This service supports small and medium groups with a maximum of 1,000 members (including primary members and dependents). The maximum number of records an org can have in the Group Census Member entity is 150,000.

Class: `InsCensusServiceStd`

Method: `deleteAllMembers`

## How It Works

1.  The service fetches all primary `GroupCensusMembers` of the provided `censusId`.
2.  The service deletes all the primary `GroupCensusMembers`, their dependents, and associated plans.
3.  In case of any failure, the service rollbacks the group census member or group census member plan records without any deletion.

## Service Behavior

Understand how different inputs affect the service outputs.

| Input | Service Output |
| --- | --- |
| No `censusId` or empty `censusId` | Specify a censusId. |
| Invalid `censusId` | Census ID is not valid. |
| Valid `censusId` | Successfully deleted Group Census Members. |

Understand the recommended batch size for quoting and enrollment.

| Process | Total Number of Members | Number of Primary Members | Recommended Batch Size |
| --- | --- | --- | --- |
| Quoting | 150,000 | Up to 30,000 | 15,000 |
| Quoting | 150,000 | 30,000 - 50,000 | 25,000 |
| Enrollment | 150,000 | NA | 500 |

## Inputs

| Input | Description |
| --- | --- |
| `censusId` | 
Required.

The ID of the associated census.

 |
| `batchSize` | 

Optional

The size of the batch.

 |

## Input JSON

```json
{      
    "censusId": "0rfxx000000001dAAA"
    "batchSize":500
}
```

## Output JSON

Complete delete:

```json
{    
    "StatusCode": "Success",
    "StatusMessage": "Successfully deleted Group Census Members.",
}
```

Did this article solve your issue?

Let us know so we can improve!

YesNo