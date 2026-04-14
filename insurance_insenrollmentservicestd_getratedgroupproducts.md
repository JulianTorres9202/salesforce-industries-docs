---
title: "InsEnrollmentServiceStd:getRatedGroupProducts"
source: "https://help.salesforce.com/s/articleView?id=ind.insurance_insenrollmentservicestd_getratedgroupproducts.htm&language=en_US&type=5"
scraped: "2026-04-14"
filter: "ind.insurance_"
---# InsEnrollmentServiceStd:getRatedGroupProducts

InsEnrollmentServiceStd:getRatedGroupProducts[](https://help.salesforce.com/s?language=en_US)

You are here:

1.  [Salesforce Help](/s/?language=en_US)
2.  [Docs](/s/products?language=en_US)
3.  [Digital Insurance](https://help.salesforce.com/s/articleView?id=ind.insurance_admin_standard.htm&language=en_US&type=5)

# InsEnrollmentServiceStd:getRatedGroupProducts

Use this service to calculate price to opt for a root plan with coverages for a family. The service also provides employee and employer contributions for a policy before enrollment, and supports proration for new hires.

Class: `InsEnrollmentServiceStd`

Method: `getRatedGroupProducts`

## How it Works

1.  The service first validates input data to verify:
    1.  A `flowName` is provided. The provided `flowName` and its version are valid and active.
        
    2.  The `memberPlans` node is present and a valid `censusMemberId` is provided for the node.
        
    3.  The provided `contractId` or `rootPlanId` is valid or if the `contractGroupPlan` of the `rootPlanId` provided is associated with the provided `contractId`.
        
    4.  Only one `memberPlans` node is specified for each `censusMemberId`. At least one primary member is specified in the `memberPlans` node, and only one primary member is specified in the `memberPlans` node.
        
    5.  The member specified belongs to the family and the provided `censusId`.
        
    6.  The specified `rootPlanId` belongs to the provided `contractId`.
        
    7.  The specified `planIds` are valid.
        
    8.  Verifies that the expression set is configured to set the member level premium amount to the `memberPremium` field when `isSaveMemberPremium` input parameter is set to `true`.
        
2.  If the input data is valid, the service calls the rating flow that's provided as `flowName`parameter in the input.
    
3.  The rating flow creates `InsuranceRatingInput`, executes the rating process, and then saves the rating output in `InsuranceRatingOutput`.
    
4.  The service returns rating output, which is the price, after applying employer and employee contribution. The service also applies proration if `IsProrated` flag is set to `true`.
    
5.  The service returns errors with error details in case of any validation or rating flow execution errors.
    

## Remote Options

| OPTION | DESCRIPTION |
| --- | --- |
| `flowName` | 
Required

Name of the rating flow used for individual enrollment

 |
| `censusId` | 

Required

The ID of the group census that contains all census members of the family that need to enroll

 |
| `contractId` | 

Required

Id of the contract that the members belong to and the plans that they enroll in.

 |
| `rootPlanId` | 

Required

ID of the root contract group plan of the product for which enrollment is requested

 |
| `isProrated` | 

Optional.

If `true`, premium calculation for the member is prorated based on the policy start date of the group census member.

 |
| `isSaveMemberPremium` | 

Optional

Indicates if the member-level premium amount has to be calculated and returned to output in members node. The default is `false`.

Note You must configure the expression set to populate the member-level premium amount in the **memberPremium** field, and select the **Include in Output** checkbox.





 |
| `memberPlans` | 

Required

List of family members and their opted optional coverages

 |
| `userInputs` | 

Optional

The set of input data the rating procedure uses to get the price of the product

 |
| `additionalInputs` | 

Optional

Serialised key-value map of additional inputs used for product rating

 |
| `inputKeysList` | 

Optional

A comma-delimited list of input keys from the rating inputs used to include in the individual rating results

 |

## Input JSON

Here's the sample input JSON:

```json
{
  "flowName": "Rating_Flow",
  "contractId": "800RN000000jyCRYAY",
  "censusId": "0r6RN0000006HOJYA2",
  "rootPlanId": "0rgRN0000000320YAA",
  "memberPlans": [
    {
      "censusMemberId": "0r6RN0000006HNkYAM",
      "planIds": [
        "0rgRN0000000320YAA",
        "0rgRN000000031xYAA"
      ]
    },
    {
      "censusMemberId": "0r6RN0000006HNuYAM",
      "planIds": [
        "0rgRN0000000320YAA",
        "0rgRN000000031xYAA"
      ]
    },
    {
      "censusMemberId": "0r6RN0000006HNuYAM"
    }
  ]
}
```

[](https://help.salesforce.com/s?language=en_US)

## Output JSON

Here's the sample output JSON:

[](https://help.salesforce.com/s?language=en_US)`{   "rootPlanId": "0rgRN0000000320YAA",   "standardPremium": 1000,   "termPremium": 750,   "employerContribution": 550,   "employeeContribution": 450,   "members": [     {       "censusMemberId": "0r6RN0000006HNkYAM",       "termPremium": 550,       "standardPremium": 600,       "employerContribution": 350,       "employeeContribution": 200,       "contributionType": "amount"     },     {       "censusMemberId": "0r6RN0000006HNuYAM",       "termPremium": 450,       "standardPremium": 400,       "employerContribution": 200,       "employeeContribution": 250,       "contributionType": "amount"     }   ] }`

Here's the sample output JSON for errors:

```json
{
  "errors": [
    {
      "error": "Specify a member that belongs to this family.",
      "planIds": ["0rgRN0000000320YAA", "0rgRN000000031xYAA"],
      "censusMemberId": "0r6RN0000006HOJYA2"
    }
  ]
}
```

Did this article solve your issue?

Let us know so we can improve!

YesNo