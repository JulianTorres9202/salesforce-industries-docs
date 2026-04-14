---
title: "InsEnrollmentServiceStd:getMemberEnrollments"
source: "https://help.salesforce.com/s/articleView?id=ind.insurance_insenrollmentservicegetmemberenrollmentsstd_632876.htm&language=en_US&type=5"
scraped: "2026-04-14"
filter: "ind.insurance_"
---# InsEnrollmentServiceStd:getMemberEnrollments

InsEnrollmentServiceStd:getMemberEnrollments[](https://help.salesforce.com/s?language=en_US)

You are here:

1.  [Salesforce Help](/s/?language=en_US)
2.  [Docs](/s/products?language=en_US)
3.  [Digital Insurance](https://help.salesforce.com/s/articleView?id=ind.insurance_admin_standard.htm&language=en_US&type=5)

# InsEnrollmentServiceStd:getMemberEnrollments

Use this service to retrieve current enrollments for a member. This service takes one or more census member Ids and returns enrolled plans for the member and associated dependents.

Class: ​`InsEnrollmentServiceStd`​​ ​

Method: ​`getMemberEnrollments`​​

## How It Works

The Insurance Policy flow is applicable when the value of `​isFsc`​​ is true:

1.  If no ​​`effectiveDate`​​ is provided in the input, the service uses the ​`contractId​​` parameter to retrieve the contract enrollment start date. See ​`effectiveDate`​​ and `​contractId`​​ parameters in the Remote Options section for more information.
    
2.  Returns the policies as ​`InsurancePolicy`​​ records. For Insurance Policy, the service supports both the Person Accounts flow and the Non-Person Accounts flow explained as:
    
    1.  ​​**Person Accounts Flow**​​
        
        This flow is applicable when census members are associated with person accounts.
        
        1.  If ​​`groupAccountId`​​ is the input, the service uses ACR to retrieve the ​`personAccountIds`​ of the census members associated with the `​groupAccountId​​`. It returns all Insurance Policies where ​`nameInsuredId​` matches the given ​`personAccountIds`​ and `​effectiveDate`​​ matches the ​`effectiveDate​​` provided in the input.
            
        2.  If ​​`censusMemberIds​​` is the input, the service retrieves the ​`GroupCensusMember`​​ records. See ​`censusMemberIds`​​ parameter in the Remote Options section for more information. If the ​`AccountId​​` field of the census members is populated, then we use these ​`personAccountIds`​ (`GroupCensusMember.AccountId`). It returns all Insurance Policies where ​`nameInsuredId​​` matches ​`personAccountIds​` and ​`effectiveDate`​​ matches the `​effectiveDate`​​ provided in the input.
            
    2.  **Non-Person Accounts Flow**​​
        
        This flow is applicable when census members are associated with contacts. ​
        
        1.  The service uses ​`accountId`​ to retrieve the `​InsurancePolicy`​​ object for the census members. It's a mandatory parameter for non-person accounts flow.
            
        2.  If ​​`censusMemberIds​​` is provided in the input, the service retrieves the ​`GroupCensusMember​` records. If the ​`AccountId`​ field of the census members isn't populated, then the service retrieves the policies of the members using the ​`GroupCensusMember.ContactId`​​, ​`accountId​​`, and ​`effectiveDate`​​.
            
3.  The service retrieves the parties and ​`InsurancePolicyParticipant`​ of the ​`InsurancePolicy`​​ records. ​`InsurancePolicyParticipant`​​ has records for both the primary members and their dependents.
    
4.  If ​​`omitChildProducts`​​ field is ​false​​, then the service retrieves the coverages (​`InsurancePolicyCoverage`​​) of the policies and their corresponding product metadata. See ​`omitChildProducts`​​ parameter in Remote Options section for more information.
    
5.  Each policy is then grouped by the primary member.
    

## Remote Options

The service uses either the ​`contractId`​ to get the `​effectiveDate`​ from ​`enrollmentStartDate`​ or it uses ​`effectiveDate​` directly, which takes precedence over `​contractId`​​ if both are used.​

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

The group Id of the census members whose policies are to be retrieved.

 |
| 

`effectiveDate`

 | 

Required if `contractId` isn't used.

The effective date of the policy.

This date must always be the GMT date of the policy's effective date.

 |
| 

`contractId`

 | 

Required if `effectiveDate` isn't used.

Retrieves the enrollment start date as the effective date of the policy.

 |
| 

`includeOptionalCoverages`

 | 

If true, the service retrieves optional coverage of the enrollments.

 |
| 

`omitChildProducts`

 | 

If false, the service retrieves coverage of the enrollments.

 |

## Input JSON

This service doesn't take an input JSON.

## Output JSON

The output JSON is a list of census members, with First Name, Last Name, Census Member Id, and Contact Id, with its enrollments. ​ ​ ​

The ​Enrollments​ node has product details and ​Dependents​​ nodes when there are dependents. It also includes child products and coverage details. ​ ​ ​

The ​Dependents​ node consists of ​First Name​​, ​Last Name​​, ​Id​​, ​Relationship Type​​, ​Contact Id​​, and ​Party Id​​.

Here's the format of the output JSON:

```json
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

Did this article solve your issue?

Let us know so we can improve!

YesNo