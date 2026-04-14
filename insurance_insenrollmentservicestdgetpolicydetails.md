---
title: "InsEnrollmentServiceStd:getPolicyDetails"
source: "https://help.salesforce.com/s/articleView?id=ind.insurance_insenrollmentservicestdgetpolicydetails.htm&language=en_US&type=5"
scraped: "2026-04-14"
filter: "ind.insurance_"
---# InsEnrollmentServiceStd:getPolicyDetails

InsEnrollmentServiceStd:getPolicyDetails[](https://help.salesforce.com/s?language=en_US)

You are here:

1.  [Salesforce Help](/s/?language=en_US)
2.  [Docs](/s/products?language=en_US)
3.  [Digital Insurance](https://help.salesforce.com/s/articleView?id=ind.insurance_admin_standard.htm&language=en_US&type=5)

# InsEnrollmentServiceStd:getPolicyDetails

Retrieve Insurance Policy records for Primary Group Census Members.

Class: `InsEnrollmentServiceStd`

Method: `getPolicyDetails`

**Scenario**

| accountId | members | isPersonAccountEnabled |
| --- | --- | --- |
| c10001 | 
{

"FirstName": "Allan",

"LastName": "Border"

}

 | true |

## How It Works

1.  If member information is provided, the service parses the member data for Contact or PersonAccount Ids.
    
    1.  If isPersonAccountEnabled is true, the service calls the findAccounts service using the PersonAccount Ids.
        
    2.  If isPersonAccountEnabled is false, the service calls the findContacts service using the Contact Ids.
        
2.  If Contact Ids are provided, the service uses the Contact Ids to match on the ContactId field in the InsurancePolicyParticipant entity.
    
3.  If Account Ids are provided, the service uses the Account Ids to match on the AccountId field in the InsurancePolicyParticipant entity.
    
4.  The service returns Insurance Policy records whose Status field is not set to "Canceled" or "Cancelled".
    

## Service Behavior

Understand how different inputs affect the service outputs.

| Input | Service Output |
| --- | --- |
| No members and no contactsIds and no accountIds | Specify a valid value for either groupAccountId or members or accountIds or contactIds. |

## Inputs

| Input | Description |
| --- | --- |
| `groupAccountId` | 
Required.

Id of the group account

 |
| `members or contactIds or accountId` | 

Required.

array of members containing at least one of these three fields: FirstName, LastName, Email

or

array of Contact Ids of the Primary Census Members

or

array of.PersonAccount Ids of the Primary Census Members

 |
| `isPersonAccountEnabled` | 

Optional.

Indicates if PersonAccounts are enabled in the org.

 |

## Input JSON

Here's the sample input JSON:

```json
{
    "accountId": "001RN0000035v63YAA",
    "members": [
        {
            "FirstName": "Allan",
            "LastName": "Border"
        }
    ]
} 
```

## Output JSON

Here's the sample output JSON:

```json
{
  "response": {
    "StatusMessage": "success",
    "StatusCode": "Success",
    "members": [
      {
        "seqId": null,
        "policies": [
          {
            "participants": [
              {
                "Name": "Laura Border",
                "Id": "0aoRN0000000Hs0YAE",
                "RelationshipToInsured": "Spouse"
              },
              {
                "Name": "Allan Border",
                "Id": "0aoRN0000000Hs1YAE",
                "RelationshipToInsured": "Self"
              }
            ],
            "EffectiveDate": "2023-08-07",
            "Name": "Dental Premium Enrollment",
            "coverages": [
              {
                "Id": "0cYRN0000000OAe2AM",
                "CoverageName": "Dental Premium Enrollment",
                "InsurancePolicyParticipantId": "0aoRN0000000Hs1YAE"
              },
              {
                "Id": "0cYRN0000000OAf2AM",
                "CoverageName": "Dental Premium Enrollment",
                "InsurancePolicyParticipantId": "0aoRN0000000Hs1YAE"
              }
            ],
            "Id": "0YTRN0000000LS84AM",
            "ExpirationDate": "2024-05-15"
          },
          {
            "participants": [
              {
                "Name": "Laura Border",
                "Id": "0aoRN0000000HsAYAU",
                "RelationshipToInsured": "Spouse"
              },
              {
                "Name": "Allan Border",
                "Id": "0aoRN0000000HsBYAU",
                "RelationshipToInsured": "Self"
              }
            ],
            "EffectiveDate": "2023-08-07",
            "Name": "VSP Premium Enrollment",
            "coverages": [
              {
                "Id": "0cYRN0000000OAo2AM",
                "CoverageName": "VSP Premium Enrollment",
                "InsurancePolicyParticipantId": "0aoRN0000000HsBYAU"
              },
              {
                "Id": "0cYRN0000000OAp2AM",
                "CoverageName": "VSP Premium Enrollment",
                "InsurancePolicyParticipantId": "0aoRN0000000HsBYAU"
              }
            ],
            "Id": "0YTRN0000000LSD4A2",
            "ExpirationDate": "2024-05-15"
          },
          {
            "participants": [
              {
                "Name": "Laura Border",
                "Id": "0aoRN0000000HsKYAU",
                "RelationshipToInsured": "Spouse"
              },
              {
                "Name": "Allan Border",
                "Id": "0aoRN0000000HsLYAU",
                "RelationshipToInsured": "Self"
              }
            ],
            "EffectiveDate": "2023-08-07",
            "Name": "Dental Premium Enrollment",
            "coverages": [
              {
                "Id": "0cYRN0000000OAy2AM",
                "CoverageName": "Dental Premium Enrollment",
                "InsurancePolicyParticipantId": "0aoRN0000000HsLYAU"
              },
              {
                "Id": "0cYRN0000000OAz2AM",
                "CoverageName": "Dental Premium Enrollment",
                "InsurancePolicyParticipantId": "0aoRN0000000HsLYAU"
              }
            ],
            "Id": "0YTRN0000000LSI4A2",
            "ExpirationDate": "2024-05-15"
          },
          {
            "participants": [
              {
                "Name": "Laura Border",
                "Id": "0aoRN0000000HsUYAU",
                "RelationshipToInsured": "Spouse"
              },
              {
                "Name": "Allan Border",
                "Id": "0aoRN0000000HsVYAU",
                "RelationshipToInsured": "Self"
              }
            ],
            "EffectiveDate": "2023-08-07",
            "Name": "VSP Premium Enrollment",
            "coverages": [
              {
                "Id": "0cYRN0000000OB82AM",
                "CoverageName": "VSP Premium Enrollment",
                "InsurancePolicyParticipantId": "0aoRN0000000HsVYAU"
              },
              {
                "Id": "0cYRN0000000OB92AM",
                "CoverageName": "VSP Premium Enrollment",
                "InsurancePolicyParticipantId": "0aoRN0000000HsVYAU"
              }
            ],
            "Id": "0YTRN0000000LSN4A2",
            "ExpirationDate": "2024-05-15"
          },
          {
            "participants": [
              {
                "Name": "Laura Border",
                "Id": "0aoRN0000000HseYAE",
                "RelationshipToInsured": "Spouse"
              },
              {
                "Name": "Allan Border",
                "Id": "0aoRN0000000HsfYAE",
                "RelationshipToInsured": "Self"
              }
            ],
            "EffectiveDate": "2023-08-07",
            "Name": "Dental Premium Enrollment",
            "coverages": [
              {
                "Id": "0cYRN0000000OBI2A2",
                "CoverageName": "Dental Premium Enrollment",
                "InsurancePolicyParticipantId": "0aoRN0000000HsfYAE"
              },
              {
                "Id": "0cYRN0000000OBJ2A2",
                "CoverageName": "Dental Premium Enrollment",
                "InsurancePolicyParticipantId": "0aoRN0000000HsfYAE"
              }
            ],
            "Id": "0YTRN0000000LSS4A2",
            "ExpirationDate": "2024-05-15"
          },
          {
            "participants": [
              {
                "Name": "Laura Border",
                "Id": "0aoRN0000000HsyYAE",
                "RelationshipToInsured": "Spouse"
              },
              {
                "Name": "Allan Border",
                "Id": "0aoRN0000000HszYAE",
                "RelationshipToInsured": "Self"
              }
            ],
            "EffectiveDate": "2023-08-07",
            "Name": "VSP Premium Enrollment",
            "coverages": [
              {
                "Id": "0cYRN0000000OBc2AM",
                "CoverageName": "VSP Premium Enrollment",
                "InsurancePolicyParticipantId": "0aoRN0000000HszYAE"
              },
              {
                "Id": "0cYRN0000000OBd2AM",
                "CoverageName": "VSP Premium Enrollment",
                "InsurancePolicyParticipantId": "0aoRN0000000HszYAE"
              }
            ],
            "Id": "0YTRN0000000LSc4AM",
            "ExpirationDate": "2024-05-15"
          },
          {
            "participants": [
              {
                "Name": "Laura Border",
                "Id": "0aoRN0000000HtIYAU",
                "RelationshipToInsured": "Spouse"
              },
              {
                "Name": "Allan Border",
                "Id": "0aoRN0000000HtJYAU",
                "RelationshipToInsured": "Self"
              }
            ],
            "EffectiveDate": "2023-08-07",
            "Name": "Dental Premium Enrollment",
            "coverages": [
              {
                "Id": "0cYRN0000000OBw2AM",
                "CoverageName": "Dental Premium Enrollment",
                "InsurancePolicyParticipantId": "0aoRN0000000HtJYAU"
              },
              {
                "Id": "0cYRN0000000OBx2AM",
                "CoverageName": "Dental Premium Enrollment",
                "InsurancePolicyParticipantId": "0aoRN0000000HtJYAU"
              }
            ],
            "Id": "0YTRN0000000LSm4AM",
            "ExpirationDate": "2024-05-15"
          },
          {
            "participants": [
              {
                "Name": "Laura Border",
                "Id": "0aoRN0000000HtSYAU",
                "RelationshipToInsured": "Spouse"
              },
              {
                "Name": "Allan Border",
                "Id": "0aoRN0000000HtTYAU",
                "RelationshipToInsured": "Self"
              }
            ],
            "EffectiveDate": "2023-08-07",
            "Name": "VSP Premium Enrollment",
            "coverages": [
              {
                "Id": "0cYRN0000000OC62AM",
                "CoverageName": "VSP Premium Enrollment",
                "InsurancePolicyParticipantId": "0aoRN0000000HtTYAU"
              },
              {
                "Id": "0cYRN0000000OC72AM",
                "CoverageName": "VSP Premium Enrollment",
                "InsurancePolicyParticipantId": "0aoRN0000000HtTYAU"
              }
            ],
            "Id": "0YTRN0000000LSr4AM",
            "ExpirationDate": "2024-05-15"
          }
        ],
        "accountId": "001RN000003IYMBYA4"
      }
    ]
  },
  "errorCode": "INVOKE-200",
  "error": "OK"
}
```

Did this article solve your issue?

Let us know so we can improve!

YesNo