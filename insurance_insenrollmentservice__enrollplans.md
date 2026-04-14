---
title: "InsEnrollmentService:enrollPlans"
source: "https://help.salesforce.com/s/articleView?id=ind.insurance_insenrollmentservice__enrollplans.htm&language=en_US&type=5"
scraped: "2026-04-14"
filter: "ind.insurance_"
---# InsEnrollmentService:enrollPlans

InsEnrollmentService:enrollPlans[](https://help.salesforce.com/s?language=en_US)

You are here:

1.  [Salesforce Help](/s/?language=en_US)
2.  [Docs](/s/products?language=en_US)
3.  [Digital Insurance](https://help.salesforce.com/s/articleView?id=ind.insurance_admin_standard.htm&language=en_US&type=5)

# InsEnrollmentService:enrollPlans

Use this service to create policy (Asset or Insurance Policy) records for enrollee selected medical, dental, vision, and other plans.

Important From Winter '23 onward, we have [InsEnrollmentServiceStd:enrollPlans](https://help.salesforce.com/s/articleView?id=ind.insurance_insenrollmentservicestd__enrollplans.htm&language=en_US&type=5 "Use this service to create insurance policy (InsurancePolicy) records for member's selected medical, dental, vision, and other plans.") service enabled to work with Salesforce Standard Data Model for Financial Services Cloud and Health Cloud. Existing customers can continue to use this service, but no further enhancements will be provided in the Insurance Managed Package.

[](https://help.salesforce.com/s?language=en_US)

Class: `InsEnrollmentService`

Method: `enrollPlans`

[](https://help.salesforce.com/s?language=en_US)

## How It Works for Insurance Policy Records

Enrollment services can either write to the Insurance Policy and related objects (Harmonized policy data model) or Asset objects (Vlocity model) , depending on the `isFsc` parameter, and the custom setting for `defaultIsFSCOption`. The service does the following:

[](https://help.salesforce.com/s?language=en_US)

1.  The service takes the input JSON and looks for the information to create the policies (Insurance Policy).
    
    | 
    defaultIsFSCOption
    
     | 
    
    isFsc parameter
    
     | 
    
    Policies Created
    
     |
    | --- | --- | --- |
    | 
    
    True
    
     | 
    
    NA
    
     | 
    
    Insurance Policy (`InsurancePolicy`) records
    
     |
    | 
    
    False
    
     | 
    
    True
    
     | 
    
    Insurance Policy (`InsurancePolicy`) records
    
     |
    | 
    
    False
    
     | 
    
    False
    
     | 
    
    Asset (`Asset`) records
    
     |
    | 
    
    NA
    
     | 
    
    True
    
     | 
    
    Insurance Policy (`InsurancePolicy`) records
    
     |
    | 
    
    NA
    
     | 
    
    False
    
     | 
    
    Asset (`Asset`) records
    
     |
    
2.  For Insurance Policy record, the member can be represented either as a Contact or a Person Account. When a member (primary or dependent) is represented as an account and contact both, the service uses the account representation.
    
3.  [](https://help.salesforce.com/s?language=en_US)
    
    Associates dependents to the policies as Insurance Policy Participants (`InsurancePolicyParticipants`). It creates another Insurance Policy Participant (`InsurancePolicyParticipant`) for the primary member.
    
    The records for `InsurancePolicyParticipants` are populated according to these rules:
    
    [](https://help.salesforce.com/s?language=en_US)Person Account Flow
    
    [](https://help.salesforce.com/s?language=en_US)You can [create Person Accounts](https://help.salesforce.com/s/articleView?id=ind.insurance_inscensusservice__createaccounts.htm&language=en_US&type=5 "Use this service to create Person Accounts for the members in the given census.") for the members in the given census. To support the Person Account flow:
    
    [](https://help.salesforce.com/s?language=en_US)
    
    -   If Primary Member is represented as a Person Account, then the member’s `Person Account Id` is set as the policy’s Account.
        
    -   If Primary Member is represented as a Person Account, then Primary Participant Account Id of primary’s `InsurancePolicyParticipant` record is Primary member’s person account Id and Primary Participant Contact Id is `personAccount.personContactId`.
        
    -   If Primary member of the dependent is represented as Person Account, then Primary Participant Account Id of dependent’s `InsurancePolicyParticipant` record is Primary member’s person account Id.
        
    -   Primary Participant Contact Id of dependent’s `InsurancePolicyParticipant` record is Primary member’s `personAccount.personContactId`.
        
    -   If dependent is represented as a Person Account, then Related Participant Account Id of dependent’s `InsurancePolicyParticipant` record is Related member’s person account Id.
        
    -   If dependent is represented as a Person Account, then Related Participant Contact Id of dependent’s `InsurancePolicyParticipant` record is Related member’s `personAccount.personContactId`.
        
    
    [](https://help.salesforce.com/s?language=en_US)Non-Person Account Flow
    
    [](https://help.salesforce.com/s?language=en_US)
    -   If Primary Member is represented as a Contact, then the member’s `Account.Id` is set as the policy’s Account.
        
    -   If Primary Member is represented as a Contact, then Primary Participant Contact Id of primary’s `InsurancePolicyParticipant` record is Primary member’s Contact Id.
        
    -   If Primary member of the dependent is represented as Contact, Primary Participant Contact Id of `InsurancePolicyParticipant` is Primary member’s contact ID.
        
    -   if dependent is represented as Contact, Related Participant Contact Id of `InsurancePolicyParticipant` is Primary member’s contact ID.
        
4.  Gets the `ProductId` from the plan and stamps `InsurancePolicy.ProductId` = `plan.Product2Id`.
    
5.  Creates these relationships:
    
    | 
    Insurance Policy
    
     |
    | --- |
    | 
    
    `InsurancePolicy.EffectiveDate`\= `Contract.StartDate` or the EffectiveStart in the input JSON.
    
     |
    | 
    
    `InsurancePolicy.ExpirationDate` = `Contract.EndDate` or the EffectiveEnd in the input JSON.
    
     |
    | 
    
    `InsurancePolicy.ContractLineItemId__c` = `Plan.Id`
    
     |
    
6.  The service calculates `InsurancePolicy.PolicyTerm` based on `Contract.ContractTerm`:
    
    | 
    Insurance Policy
    
     |
    | --- |
    | 
    
     ContractTerm = 12, InsurancePolicy.PolicyTerm= Annual.
    
     |
    | 
    
    ContractTerm = 6, InsurancePolicy.PolicyTerm= Semi-Annual
    
     |
    | 
    
    ContractTerm = 1, InsurancePolicy.PolicyTerm= Monthly
    
     |
    | 
    
    ContractTerm = Any other value, InsurancePolicy.PolicyTerm= Custom.
    
     |
    
7.  Gets the `Price` key from the input JSON and creates these relationships:
    
    | 
    Insurance Policy
    
     |
    | --- |
    | 
    
    `InsurancePolicy.PremiumAmount` = Price
    
     |
    | 
    
    `InsurancePolicy.TermPremiumAmount` = prorated price based on the effective dates specified in #5.
    
     |
    | 
    
    `InsurancePolicy.MonthlyPremium__c` = Price/ContractTerm
    
     |
    
8.  Creates Insurance Policy Coverages (`InsurancePolicyCoverages`) for the coverage items.
    

[](https://help.salesforce.com/s?language=en_US)

## How It Works for Assets

[](https://help.salesforce.com/s?language=en_US)

1.  The service takes the input JSON and looks for the information to create the policies (assets).
    
    | 
    defaultIsFSCOption
    
     | 
    
    isFsc parameter
    
     | 
    
    Policies Created
    
     |
    | --- | --- | --- |
    | 
    
    True
    
     | 
    
    NA
    
     | 
    
    Insurance Policy (`InsurancePolicy`) records
    
     |
    | 
    
    False
    
     | 
    
    True
    
     | 
    
    Insurance Policy (`InsurancePolicy`) records
    
     |
    | 
    
    False
    
     | 
    
    False
    
     | 
    
    Asset (`Asset`) records
    
     |
    | 
    
    NA
    
     | 
    
    True
    
     | 
    
    Insurance Policy (`InsurancePolicy`) records
    
     |
    | 
    
    NA
    
     | 
    
    False
    
     | 
    
    Asset (`Asset`) records
    
     |
    
2.  Associates the primary member’s `contactId` with the policy as a Contact.
    
3.  Stamps the enrollment contract’s `accountId` as the policy’s Account.
    
4.  Takes the `RawPriceData` key or the `RateBandTierPriceData` key from the input JSON and stamps it to the `Asset.PricingLogData__c` field.
    
5.  Gets the `ProductId` from the plan and stamps `Asset.Product2Id` = `plan.Product2Id__c`.
    
6.  Creates the following relationships:
    
    | 
    Assets
    
     |
    | --- |
    | 
    
    `Asset.EffectiveDate__c` = `Contract.StartDate` or the EffectiveStart in the input JSON.
    
     |
    | 
    
    `Asset.ExpirationDate__c` = `Contract.EndDate` or the EffectiveEnd in the input JSON.
    
     |
    | 
    
    `Asset.BenefitPlanId__c` = `Plan.Id`
    
     |
    
7.  The service calculates `Asset.Term__c` based on `Contract.ContractTerm`:
    
    | 
    Assets
    
     |
    | --- |
    | 
    
    ContractTerm = 12, Asset.Term\_\_c = Annual.
    
     |
    | 
    
    ContractTerm = 6, Asset.Term\_\_c = Semi-Annual
    
     |
    | 
    
    ContractTerm = 1, Asset.Term\_\_c = Monthly
    
     |
    | 
    
    ContractTerm = Any other value, Asset.Term\_\_c = Custom.
    
     |
    
8.  Gets the `Price` key from the input JSON and creates these relationships:
    
    | 
    Assets
    
     |
    | --- |
    | 
    
    `Asset.StandardPremium__c` = Price
    
     |
    | 
    
    `Asset.TotalPremiumTerm__c` = prorated price based on the effective dates specified in #7
    
     |
    | 
    
    `Asset.AnnualPremium__c` = Price/ContractTerm\*12
    
     |
    | 
    
    `Asset.MonthlyPremium__c` = Price/ContractTerm
    
     |
    
9.  Associates dependents to the policies as Held Product Relationships (`AssetPartyRelationship__c`). While creating asset party relationship for dependents, the partyId must be provided in the dependents node.
    
    Note
    
    Another Insurance Policy Participant (`InsurancePolicyParticipant`) is created for the primary member, but no record is created for the primary member in Held Product Relationship (AssetPartyRelationship\_\_c).
    
10.  Creates Policy Coverages (`AssetCoverage__c`) for the coverage items.
     

[](https://help.salesforce.com/s?language=en_US)

## Remote Options

| 
Option

 | 

Description

 |
| --- | --- |
| 

`inputKey`

 | 

Required.

The key to a pre-transformed JSON structure that contains information the service needs.

 |
| 

`memberPlanIntegrationProcedure`

 | 

Initiates a custom integration procedure based on the user configuration. When you use this option, it passes all options of the service to the custom integration procedure and all policy Ids as input to integrate with the object, for example the insurance policy object with the member plan.

 |

[](https://help.salesforce.com/s?language=en_US)

## Input JSON

The service takes the input JSON specified by the `inputKey`. In this example, `inputKey` = `enrollmentJson`.

The service requires:

-   `contractId`: <value\>
    
-   `Dependents`: <list of maps for contactId and relationshipType of the dependents>.
    
    Note
    
    While using enrollPlans service to generate Asset and AssetPartyRelationship, if dependents are passed in enrollmentJson, then corresponding partyId must be provided.
    
-   [Product JSON Structure Model](https://help.salesforce.com/s/articleView?id=ind.insurance_product_json_structure_model_609451.htm&language=en_US&type=5 "The product JSON object provides a portable product data object for runtime use between services and templates.") including attributes and child products
    

This input JSON can have either a list of objects or a map, because the service supports creating either one policy or multiple policies.

To support Person Account Id, `primaryMemberId` is a new node added to the `enrollmentJson`. It supports both Person Account Id and ContactId for backward compatibility. Based on the Id type of `primaryMemberId`, the services work as described in service description.

Similarly, for dependents, `memberId` node is added. It supports both Person Account Id and contact Id for backward compatibility. Based on the Id type of `memberId`, the services work as described in service description.

In this example, the JSON includes three policies.

[](https://help.salesforce.com/s?language=en_US)`{    "enrollmentJson":[       {          "primaryMemberContactId":"0035w00003HjCFcAAN",                   "primaryMemberId" : "0015e00000DvQ89AAF"          "contractId":"8005w000001mT4MAAU",          "dependents":{             "IsSpouse":false,             "contactId":"0035w00003HhfXPAAZ",             "memberId": "0015e00000RvO24IAJ"             "LastName":"Jones",             "FirstName":"Jean",             "relationshipType":"Child"          },          "Id":"01t5w00000EZUtMAAX",          "Name":"HMO 500",          "Family":"Other",          "ProductCode":"SG-HMO-500",          "Type__c":"Medical",          "SubType__c":"HMO",          "RecordTypeName__c":"Product",          "IsConfigurable__c":false,          "PricingFormula__c":"GroupPremium",          "productId":"01t5w00000EZUtMAAX",          "currencyCode":"USD",          "currencySymbol":"$",          "Price":300,          "planId":"a2S5w0000034B2cEAE",          "planRateType":"Age",          "attributeCategories":{             "totalSize":1,             "records":[                {                   "Code__c":"SG_Medical",                   "Name":"SG Medical",                   "id":"a085w00000uA9v6AAC",                   "productAttributes":{                      "totalSize":1,                      "records":[                         {                            "rulesCode":"SG-HMO-500.SG_annualDed_INN",                            "productCode":"SG-HMO-500",                            "code":"SG_annualDed_INN",                            "dataType":"text",                            "inputType":"text",                            "multiselect":false,                            "required":false,                            "readonly":true,                            "disabled":true,                            "filterable":true,                            "attributeId":"a095w000010zIYkAAM",                            "label":"Deductible",                            "hasRules":false,                            "hidden":false,                            "cloneable":true,                            "isNotTranslatable":false,                            "values":[                               {                                  "readonly":true,                                  "disabled":true                               }                            ],                            "userValues":"$500 / $1,000",                            "attributeGroupType":"In-Network"                         }                      ]                   }                }             ]          },          "childProducts":{             "totalSize":1,             "records":[                {                   "Id":"01t5w00000EZUA7AAP",                   "Name":"Emergency Services",                   "ProductCode":"SG_Emerg_Serv",                   "Type__c":"Medical",                   "IsRecommended__c":false,                   "RecordTypeName__c":"CoverageSpec",                   "IsConfigurable__c":true,                   "productId":"01t5w00000EZUA7AAP",                   "pciId":"a3A5w000000Ib6fEAC",                   "isOptional":false,                   "isSelected":true,                   "attributeCategories":{                      "totalSize":1,                      "records":[                         {                            "Code__c":"SG_Medical",                            "Name":"SG Medical",                            "id":"a085w00000uA9v6AAC",                            "productAttributes":{                               "totalSize":1,                               "records":[                                  {                                     "code":"SG_urgentCareFacility_OON",                                     "dataType":"text",                                     "inputType":"dropdown",                                     "multiselect":false,                                     "required":false,                                     "readonly":false,                                     "disabled":false,                                     "filterable":true,                                     "attributeId":"a095w000010zIZRAA2",                                     "label":"Urgent Care Facility",                                     "hasRules":false,                                     "hidden":false,                                     "cloneable":true,                                     "isNotTranslatable":false,                                     "values":[                                        {                                           "id":"0",                                           "label":"Not Covered",                                           "readonly":false,                                           "disabled":false,                                           "value":"Not Covered"                                        },                                        {                                           "id":"1",                                           "label":"40% Coins After Ded",                                           "readonly":false,                                           "disabled":false,                                           "value":"40% Coins After Ded"                                        },                                        {                                           "id":"2",                                           "label":"50% Coins After Ded",                                           "readonly":false,                                           "disabled":false,                                           "value":"50% Coins After Ded"                                        },                                        {                                           "id":"3",                                           "label":"30% Coins After Ded",                                           "readonly":false,                                           "disabled":false,                                           "value":"30% Coins After Ded"                                        }                                     ],                                     "userValues":"Not Covered",                                     "attributeGroupType":"Out-Of-Network"                                  }                               ]                            }                         }                      ]                   }                }             ]          }       }    ] }`

[](https://help.salesforce.com/s?language=en_US)

## Output JSON

The list of policies created by the service.

| 
assetIds

 | 

InsurancePolicy record IDs for Insurance Policy records.

Asset record IDs for Assets records.

 |
| --- | --- |
| 

policyIds

 | 

InsurancePolicy record IDs. Generated only for Insurance Policy records.

 |

[](https://help.salesforce.com/s?language=en_US)`{    "assetIds":[       {          "assetId":"0036F00002Q4wlSQAR"       },       {          "assetId":"0036F00002Q4wlSQAQ"       }    ],    "policyIds":[       "0036F00002Q4wlSQAR",       "0036F00002Q4wlSQAQ"    ] }`

Did this article solve your issue?

Let us know so we can improve!

YesNo