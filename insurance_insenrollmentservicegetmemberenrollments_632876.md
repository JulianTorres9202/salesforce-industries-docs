---
title: "InsEnrollmentService:getMemberEnrollments"
source: "https://help.salesforce.com/s/articleView?id=ind.insurance_insenrollmentservicegetmemberenrollments_632876.htm&language=en_US&type=5"
scraped: "2026-04-14"
filter: "ind.insurance_"
---# InsEnrollmentService:getMemberEnrollments

InsEnrollmentService:getMemberEnrollments[](https://help.salesforce.com/s?language=en_US)

You are here:

1.  [Salesforce Help](/s/?language=en_US)
2.  [Docs](/s/products?language=en_US)
3.  [Digital Insurance](https://help.salesforce.com/s/articleView?id=ind.insurance_admin_standard.htm&language=en_US&type=5)

# InsEnrollmentService:getMemberEnrollments

Use this service to retrieve current enrollments for a member so they can edit the benefits. This service also takes one or more census member Ids and returns enrolled plans for the member and their dependents.

Important From Winter '23 onward, we have [InsEnrollmentServiceStd:getMemberEnrollments](https://help.salesforce.com/s/articleView?id=ind.insurance_insenrollmentservicegetmemberenrollmentsstd_632876.htm&language=en_US&type=5 "Use this service to retrieve current enrollments for a member. This service takes one or more census member Ids and returns enrolled plans for the member and associated dependents.") service enabled to work with Salesforce Standard Data Model for Financial Services Cloud and Health Cloud. Existing customers can continue to use this service, but no further enhancements will be provided in the Insurance Managed Package.

[](https://help.salesforce.com/s?language=en_US)

Class: `InsEnrollmentService`

[](https://help.salesforce.com/s?language=en_US)

Method: `getMemberEnrollments`

[](https://help.salesforce.com/s?language=en_US)

There are two flows to invoke the getMemberEnrollments service:

-   Insurance Policy Flow: It’s triggered when the value of `isFsc` is true.
    
    -   Person Accounts flow is triggered when `isFsc` is true and `GroupCensusMember__c.AccountId__c` field is populated.
        
    -   Non-Person Accounts flow is triggered when `GroupCensusMember__c.AccountId__c` field isn’t populated.
        
-   Asset Flow: It’s triggered when the value of `IsFsc` is false.
    

[](https://help.salesforce.com/s?language=en_US)

## How It Works When Using Insurance Policy Records

The Insurance Policy flow is applicable when the value of `isFsc` is true. The service does the following:

1.  If no `effectiveDate` is provided in the input, the service uses the `contractId` parameter to retrieve `Contract.EnrollmentStartDate__c`. See `effectiveDate` and `contractId` parameters in the Remote Options section for more information.
    
2.  Returns the policies as `InsurancePolicy` records. For Insurance Policy, the service supports both the Person Accounts flow and the Non-Person Accounts flow explained as:
    
    Person Accounts Flow
    
    This flow is applicable when census members are associated to person accounts.
    
    1.  If `groupAccountId` is the input, the service uses ACR to retrieve the `personAccountIds` of the census members associated with the `groupAccountId`. It returns all Insurance Policies where `nameInsuredId` matches these `personAccountIds` and `effectiveDate` match the `effectiveDate` provided in the input.
        
    2.  If `censusMemberIds` is the input, the service retrieves the `GroupCensusMember__c` records. See `censusMemberIds` parameter in Remote Options section for more information. If the `AccountId__c` field of the census members is populated, then we use these `personAccountIds` (GroupCensusMember\_\_c.AccountId\_\_c). It returns all Insurance Policies where `nameInsuredId` matches `personAccountIds` and `effectiveDate` match the `effectiveDate` provided in the input.
        
    
    Non-Person Accounts Flow
    
    This flow is applicable when census members are associated to contacts.
    
    1.  The service uses `accountId` to retrieve the `InsurancePolicy` object for the census members. It’s a mandatory parameter for non-person accounts flow.
        
    2.  If `censusMemberIds` field is provided in the input, the service retrieves the `GroupCensusMember__c` records. If the `AccountId__c` field of the census members isn’t populated, then the service retrieves the policies of the members using the `GroupCensusMember__c.ContactId__c`, `accountId`, and `effectiveDate`. The type of policy that gets retrieved depends on the `isFsc` parameter, and the custom setting for `defaultIsFSCOption` as is described in this table:
        
        | 
        Custom Settings > Insurance Configuration Setup>defaultIsFSCOption
        
         | 
        
        IsFsc Parameter
        
         | 
        
        Policies Retrieved
        
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
        
        NA
        
         | 
        
        True
        
         | 
        
        InsurancePolicy
        
         |
        
3.  The service retrieves the parties, `InsurancePolicyParticipant` or `AssetPartyRelationship__c` of the `InsurancePolicy` or `Asset` records, respectively. For FSC, `AssetPartyRelationship__c` only has records for the primary members' dependents. `InsurancePolicyParticipant` has records for both the primary members and their dependents.
    
4.  If `omitChildProducts` field is `false`, then the service retrieves the coverages (`AssetCoverage__c`) of the policies and their corresponding product metadata. See `omitChildProducts` parameter in Remote Options section for more information.
    
5.  Each policy is then grouped by the primary member.
    

[](https://help.salesforce.com/s?language=en_US)

## How It Works for Assets

Assets flow is applicable when the value of `isFsc` is false. For assets records, we don't support Person Account.

The service does the following:

1.  If no `effectiveDate` is provided in the input, the service uses the `contractId` parameter to retrieve `Contract.EnrollmentStartDate__c`. See `effectiveDate` and `contractId` parameters in the Remote Options section for more information.
    
2.  The service uses `accountId` to retrieve the Asset object for the census members. It’s a mandatory parameter for Non-FSC accounts flow.
    
3.  The service uses `censusMemberIds` to retrieve the `GroupCensusMember__c` records. See `censusMemberIds` parameter in the Remote Options section for more information.
    
4.  If `AccountId__c` field of the census members isn’t populated, the service retrieves the policies of the members using the `GroupCensusMember__c.ContactId__c`, `accountId`, and `effectiveDate` fields. The type of policy that gets retrieved depends on the `isFsc` parameter, and the custom setting for `defaultIsFSCOption` as is described in this table.
    
    | 
    Custom Settings > Insurance Configuration Setup>defaultIsFSCOption
    
     | 
    
    IsFsc Parameter
    
     | 
    
    Policies Retrieved
    
     |
    | --- | --- | --- |
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
    
    False
    
     | 
    
    Asset
    
     |
    
5.  The service retrieves the parties. For Non-FSC, it retrieves `InsurancePolicyParticipant` or `AssetPartyRelationship__c`, of the `InsurancePolicy` or `Asset` records.
    
    -   `AssetPartyRelationship__c` only has records for the primary members' dependents.
        
    -   `InsurancePolicyParticipant` has records for both the primary members and their dependents.
        
6.  If `omitChildProducts` field is `false`, the service retrieves the coverages (`InsurancePolicyCoverage` or `AssetCoverage__c`) of the policies and their corresponding product metadata. See `omitChildProducts` parameter in Remote Options section for more information.
    
7.  Each policy is then grouped by the primary member.
    

[](https://help.salesforce.com/s?language=en_US)

## Remote Options

The service uses either the `contractId` to get the `effectiveDate` from `enrollmentStartDate` or it uses `effectiveDate` directly, which takes precedence over `contractId` if both are used.

| 
Option

 | 

Description

 |
| --- | --- |
| 

`censusMemberIds`

 | 

List of primary census member ids.

 |
| 

`accountId`

 | 

The group Id this member belongs to.

 |
| 

`groupAccountId`

 | 

The group Id of the census members whose policies are to be retrieved. This parameter is applicable for FSC flow only.

 |
| 

`effectiveDate`

 | 

Required if contractId isn’t used

Effective date of the policy.

This date must always be the GMT date of the policy's effective date.

 |
| 

`contractId`

 | 

Required if effectiveDate isn’t used.

Can be used instead of `effectiveDate` to retrieve enrollment start date as the effective date of the policy.

 |
| 

`includeOptionalCoverages`

 | 

If true, service retrieves optional coverages of the enrollments.

 |
| 

`omitChildProducts`

 | 

If false, service retrieves coverages of the enrollments.

 |
| 

`isFsc`

 | 

-   Determines whether to retrieve the policies from the Asset records or the InsurancePolicy records.
    
-   If the `Custom Settings` > `Insurance Configuration Setup` has the `defaultIsFSCOption` set to `false` or if there’s no `defaultIsFSCOption`, the value of this parameter is honored.
    

 |

[](https://help.salesforce.com/s?language=en_US)

## Input JSON

This service doesn’t take an input JSON.

[](https://help.salesforce.com/s?language=en_US)

## Output JSON

Here's the format of the output JSON:

-   The output JSON is a list of census members, with First Name, Last Name, Census Member Id, and Contact Id, with its enrollments.
    
-   The `Enrollments` node has product details and `Dependents` nodes if there are dependents. It also includes child Products and coverage details.
    
-   The `Dependents` node consists of `First Name`, `Last Name`, `Id`, `RelationshipType`, `ContactId`, and `PartyId`.
    

```
{
  "totalSize": numberOfPrimaryMembersRetrievedWithEnrollments,
  "records": [
    {
      "FirstName": "primaryMemberFirstName",
      "LastName": "primaryMemberLastName",
      "Id": "primaryMemberGroupCensusMemberId",
      "contactId": "primaryMemberContactId",
      "enrollments": {
        "totalSize": primary member's number of enrollments,
        "records": [
          {
            "policyNumber": "policy number",
            "Id": "policy Id",
            "productId": "policy's product id",
            "accountId": "policy's account id",
            "primaryMemberContactId": "primaryMemberContactId",
            "productName": "policy's product name",
            "Name": "policy's product name",
            "EffectiveStart": "policy effective date",
            "EffectiveEnd": "policy expiration date",
            "Price": 0,
            "planId": "policy product's plan id",
            "contractId": "contract id",
            "ProductCode": "product code",
            "RecordTypeName__c": "Product",
            "attributeCategories": {},
            "Term": "policy term",
            "attributeSelectedValues": "{}",
            "childProducts": {
              "totalSize": numberOfChildProductsOfThePolicyProduct,
              "records": [
                {
                  "productId": "productIdOfTheChildProduct",
                  "productName": "productNameOfTheChildProduct",
                  "ProductCode": "productCodeOfTheChildProduct",
                  "Name": "productNameOfTheChildProduct",
                  "pciId": "productChildItemIdOfTheChildProduct",
                  "isOptional": ifThisIsAnOptionalCoverage,
                  "attributeSelectedValues": "{}",
                  "isSelected": true,
                  "Id": "coverageId",
                  "PricingSource": "pricingSource",
                  "attributeCategories": {}
                }
              ]
            },
            "dependents": {
              "totalSize": primary member's number of dependents,
              "records": [
                {
                  "Id": "record id",
                  "FirstName": "dependentsFirstName",
                  "LastName": "dependentsLastName",
                  "relationshipType": "relationshipType",
                  "partyId": "contact's party id",
                  "contactId": "dependent's contact Id"
                }
              ]
            }
          }
        ]
      }
    }
  ]
}
```

Here's an example of output JSON:

```
{
  "totalSize": 1,
  "records": [
    {
      "FirstName": "Scott",
      "LastName": "Matthews",
      "Id": "a386F000000yq5LQAQ",
      "contactId": "0036F00002Q4wlSQAR",
      "enrollments": {
        "totalSize": 1,
        "records": [
          {
            "policyNumber": "AA232SDTJ",
            "Id": "02i6F000004XE2jQAG",
            "productId": "01t6F000007sLsaQAE",
            "accountId": "0016F00002GIY4mQAH",
            "primaryMemberContactId": "0036F00002Q4wlSQAR",
            "productName": "BoMedicalProduct",
            "Name": "BoMedicalProduct",
            "EffectiveStart": "2018-04-12",
            "EffectiveEnd": "2019-02-09",
            "Price": 0,
            "planId": "a1u6F0000035QYxQAM",
            "contractId": "8006F000001GhodQAC",
            "ProductCode": "BMP",
            "RecordTypeName__c": "Product",
            "attributeCategories": {
              "totalSize": 1,
              "records": [
                {
                  "productAttributes": {
                    "records": [
                      {
                        "userValues": null,
                        "values": [
                          {
                            "disabled": true,
                            "readonly": true
                          }
                        ],
                        "isNotTranslatable": false,
                        "cloneable": true,
                        "hidden": false,
                        "hasRules": false,
                        "displaySequence": 0,
                        "label": "TestAttribute_2.2",
                        "attributeId": "a1R6F00000FNrpDUAT",
                        "filterable": true,
                        "disabled": true,
                        "readonly": true,
                        "required": false,
                        "multiselect": false,
                        "inputType": "number",
                        "dataType": "currency",
                        "code": "bfb83baa-662e-674e-9c04-2bad2dc545e1"
                      }
                    ],
                    "totalSize": 1
                  },
                  "id": "a1Q6F000009rHU0UAM",
                  "Name": "AlvinProdCattegory2",
                  "Code__c": "d7539648-3485-0218-802c-c493e727fa67"
                }
              ]
            },
            "Term": "Custom",
            "attributeSelectedValues": "{}",
            "childProducts": {
              "totalSize": 1,
              "records": [
                {
                  "productId": "01t6F00000Akx48QAB",
                  "productName": "Serious Illness",
                  "ProductCode": "SERILL",
                  "Name": "Serious Illness",
                  "pciId": "a2Q6F000001JiqHUAS",
                  "isOptional": false,
                  "attributeSelectedValues": "{}",
                  "isSelected": true,
                  "Id": "01t6F00000Akx48QAU",
                  "PricingSource": "SIPremSelected",
                  "attributeCategories": {
                    "totalSize": 1,
                    "records": [
                      {
                        "productAttributes": {
                          "records": [
                            {
                              "userValues": null,
                              "values": [
                                {
                                  "disabled": false,
                                  "readonly": false
                                }
                              ],
                              "isNotTranslatable": false,
                              "cloneable": true,
                              "hidden": false,
                              "hasRules": false,
                              "displaySequence": 1,
                              "label": "SI Amount Override",
                              "attributeId": "a1R6F00000LE7ESUA1",
                              "filterable": true,
                              "disabled": false,
                              "readonly": false,
                              "required": false,
                              "multiselect": false,
                              "inputType": "number",
                              "dataType": "currency",
                              "code": "SIOVER"
                            },
                            {
                              "rules": [
                                {
                                  "actions": {
                                    "Hide": {
                                      "client": {
                                        "params": {}
                                      },
                                      "remote": {
                                        "params": {}
                                      },
                                      "rest": {
                                        "link": null,
                                        "method": null,
                                        "params": {}
                                      }
                                    }
                                  },
                                  "expression": "%SERILL.SIOVER% > 0",
                                  "ruleType": "Hide"
                                }
                              ],
                              "userValues": null,
                              "values": [
                                {
                                  "disabled": false,
                                  "readonly": false
                                }
                              ],
                              "isNotTranslatable": false,
                              "cloneable": true,
                              "hidden": false,
                              "hasRules": true,
                              "displaySequence": 9,
                              "label": "SIB Multiplier",
                              "attributeId": "a1R6F00000LE7ERUA1",
                              "filterable": true,
                              "disabled": false,
                              "readonly": false,
                              "required": false,
                              "multiselect": false,
                              "inputType": "number",
                              "dataType": "number",
                              "code": "SIB"
                            },
                            {
                              "rules": [
                                {
                                  "actions": {
                                    "Hide": {
                                      "client": {
                                        "params": {}
                                      },
                                      "remote": {
                                        "params": {}
                                      },
                                      "rest": {
                                        "link": null,
                                        "method": null,
                                        "params": {}
                                      }
                                    }
                                  },
                                  "expression": "%SERILL.SIOVER% > 0",
                                  "ruleType": "Hide"
                                }
                              ],
                              "userValues": null,
                              "values": [
                                {
                                  "disabled": false,
                                  "readonly": false
                                }
                              ],
                              "isNotTranslatable": false,
                              "cloneable": true,
                              "hidden": false,
                              "hasRules": true,
                              "displaySequence": 10,
                              "label": "SIB Max",
                              "attributeId": "a1R6F00000LE7EQUA1",
                              "filterable": true,
                              "disabled": false,
                              "readonly": false,
                              "required": false,
                              "multiselect": false,
                              "inputType": "number",
                              "dataType": "currency",
                              "code": "SI"
                            }
                          ],
                          "totalSize": 3
                        },
                        "id": "a1Q6F00000ATYVIUA5",
                        "Name": "Benefit Calculation",
                        "Code__c": "11c2dcbf-500e-1180-4581-ff5000cb0ca6",
                        "displaySequence": 12
                      }
                    ]
                  }
                }
              ]
            },
            "dependents": {
              "totalSize": 2,
              "records": [
                {
                  "Id": "a0o6F00000WsgPtQAJ",
                  "FirstName": "Joan",
                  "LastName": "Robbins",
                  "relationshipType": "Child",
                  "partyId": "a376F000008BJIvQAJ",
                  "contactId": "a376F000008BJIvQAO"
                },
                {
                  "partyId": "a0o6F00000Wsh8QQAF",
                  "Id": "a0o6F00000Wsh8QQAR",
                  "First Name": "Max",
                  "Last Name": "Robbins",
                  "relationshipType": "Spouse",
                  "contactId": "a376F000008BJIwQAO"
                }
              ]
            }
          }
        ]
      }
    }
  ]
}
```

Did this article solve your issue?

Let us know so we can improve!

YesNo