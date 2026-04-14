---
title: "InsEnrollmentServiceStd:enrollFamily"
source: "https://help.salesforce.com/s/articleView?id=ind.insurance_insenrollmentservicestd_enrollfamily.htm&language=en_US&type=5"
scraped: "2026-04-14"
filter: "ind.insurance_"
---# InsEnrollmentServiceStd:enrollFamily

InsEnrollmentServiceStd:enrollFamily[](https://help.salesforce.com/s?language=en_US)

You are here:

1.  [Salesforce Help](/s/?language=en_US)
2.  [Docs](/s/products?language=en_US)
3.  [Digital Insurance](https://help.salesforce.com/s/articleView?id=ind.insurance_admin_standard.htm&language=en_US&type=5)

# InsEnrollmentServiceStd:enrollFamily

​Use this service to enroll one family within one root plan that includes a primary member and associated dependents with coverages.

Note Employees or customer community users are not expected to create portal users for their respective dependents. Hence, don’t include Create User invocable action in the flow that's provided as input.

Class: `InsEnrollmentServiceStd`

Method: `enrollFamily`

## How it Works

1.  The service first validates input data to verify:
    1.  Required request data is provided.
        
    2.  The provided `flowName` and its version are valid and active.
        
    3.  The provided `primaryMemberId` is valid and there is a record matching for a given `primaryMemberId` and `censusId`.
        
    4.  The provided `contractId` or `rootPlanId` is valid or the `contractGroupPlan` of the provided `rootPlanId` is associated with the provided `contractId`.
        
    5.  The enrollment status is completed for the provided `rootPlanId` and `primaryMemberId` in the `GroupCensusMemberPlan` table.
        
    6.  There's a record associated with the specified `rootPlanId` and `primaryCensusMemberId`.
        
2.  If the input data is valid, the service calls the enrollment flow.
    
3.  The enrollment flow creates Insurance Policies, Insurance Policy Participants, and Insurance Policy Coverages.
    
4.  The service returns Policy ID in case of successful execution.
    
5.  The service returns errors with error details in case of any validation or enrollment flow execution errors.
    

## Remote Options

| OPTION | DESCRIPTION |
| --- | --- |
| `flowName` | 
Required

Name of the enrollment flow used for individual enrollment.

 |
| `groupCensusId` | 

Required

The ID of the group census that contains all census members of the family to be enrolled..

 |
| `contractId` | 

Required

Id of the contract that the members belong to and the plans that they'll be enrolled in.

 |
| `primaryMemberId` | 

Required

Id of the primary member to be enrolled.

 |
| `rootPlanId` | 

Required

​ID of the root contract group plan of the enrollment product.

 |
| `isProrated` | 

Optional.

If `true`, premium calculation for the member is prorated.

 |
| `isSaveMemberPremium` | 

Optional

Indicates if the policy premium amount must be set for all InsurancePolicyParticipant records. If `true`, the policy member premium is stored in InsurancePolicyParticipant.TotalStandardAmount for all Insurance Policy Participants of a policy. The default is `false`.

 |
| `userInputs` | 

Optional

The set of input data the rating procedure uses to get the price of the product.

 |
| `additionalInputs` | 

Optional

Serialised key-value map of additional inputs used for product rating.

 |
| `matchingKeysList` | 

Required

A comma-separated fields of Account object to use for duplicate detection against existing Account records if personAccount is enabled in an org.

A comma-separated fields of Contact object to use for duplicate detection against existing Contact records if personAccount is not enabled in an org.

 |
| `inputKeysList` | 

Optional

A comma-delimited list of input keys from the rating inputs to use to include in the individual rating results.

 |
| `emailEncodingKey` | 

Required if create portal user invocable action is used.

The email encoding key to use to create the user records. For example, ISO-8859-1 or UTF-8.

 |
| `languageLocaleKey` | 

Optional

Required if create portal user invocable action is used.

 |
| `localeSidKey` | 

Required if create portal user invocable action is used.

The SID key of the locale to use to create user records.

 |
| `timezoneSidKey` | 

Required if create portal user invocable action is used.

The time zone SID key to use to create the user records.

 |
| `profileId` | 

Optional

The Id of the Profile record that should be associated with the User record.

 |

## Input JSON

Here's the sample input JSON:

```json
{

'flowName': 'Individual_Enrollment',
'groupCensusId':'0rfSG00000003fRYAQ',
'contractId':'800RN000000jyCRYAY',
'primaryMemberId':'0r6SG0000000j1xYAA',
'rootPlanId':'0rgRN0000000320YAA',
'isProrated': true,

'isSaveMemberPremium':true,
'emailEncodingKey':'ISO-8859-1',
'languageLocaleKey':'en_US',
'localeSidKey':'en_US',
'timezoneSidKey':'America/Los_Angeles',
'profileId':'00eSG00000120ug',

'userInputs':{"ratingType": "Enrollment"},

'additionalInputs':{"mergeList": "true", "includeOptionalCovSelectFlag":true}

'matchingKeysList':'FirstName,LastName',

'inputKeysList':'aggByKey,primaryMember,groupCensusMemberId'

}
```

[](https://help.salesforce.com/s?language=en_US)

## Output JSON

Here's the sample output JSON:

[](https://help.salesforce.com/s?language=en_US)`{        policyId:'0YTB00000000hrfOAA'  }`

## Output JSON for Errors

Here's the sample error output JSON:

```json
{
     "errors":[
                        {
                             "error":"already enrolled",
                             "rootPlanId":"0rgRN0000000320YAA",
                             "censusMemberId":"0r6RN0000006HOJYA2"
                        },
                   ]
}
```

Did this article solve your issue?

Let us know so we can improve!

YesNo