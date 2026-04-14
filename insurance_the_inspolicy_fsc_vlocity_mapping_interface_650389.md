---
title: "The InsPolicy FSC-Vlocity Mapping Interface"
source: "https://help.salesforce.com/s/articleView?id=ind.insurance_the_inspolicy_fsc_vlocity_mapping_interface_650389.htm&language=en_US&type=5"
scraped: "2026-04-14"
filter: "ind.insurance_"
---# The InsPolicy FSC-Vlocity Mapping Interface

The InsPolicy FSC-Vlocity Mapping Interface[](https://help.salesforce.com/s?language=en_US)

You are here:

1.  [Salesforce Help](/s/?language=en_US)
2.  [Docs](/s/products?language=en_US)
3.  [Digital Insurance](https://help.salesforce.com/s/articleView?id=ind.insurance_admin_standard.htm&language=en_US&type=5)

# The InsPolicy FSC-Vlocity Mapping Interface

The InsPolicy interface is a generic service interface that lets Vlocity policy services work with any policy data model, including the Salesforce FSC Insurance Policy data model.

The InsPolicyService and InsPolicyRevenueScheduleService services perform their business logic on the InsPolicy interface instead of on the Vlocity policy data model directly.

Beginning with Winter '20, Vlocity Insurance policy services no longer interact with database objects and fields directly. Instead, they rely on the caller to fetch or post data to database objects and fields using Omnistudio Data Mappers or Apex classes. The `Get` Data Mapper or Apex class needs to fetch data, and conform that data to the InsPolicy interface for policy services. The `Post` Data Mapper or Apex class needs to accept the InsPolicy interface from policy services, and post the data to the database.

[](https://help.salesforce.com/s?language=en_US)

## Vlocity Insurance Policy to Salesforce FSC Policy Data Model Mapping

Here's how Vlocity objects map to Salesforce FSC objects.

| 
Vlocity Object

 | 

FSC Object

 | 

Notes

 |
| --- | --- | --- |
| 

`Asset`

 | 

`InsurancePolicy`

 |  |
| 

`AssetCoverage__c`

 | 

`InsurancePolicyCoverage`

 |  |
| 

`AssetInsuredItem__c`

 | 

`InsurancePolicyAsset`

 | 

For InsurancePolicyAsset, an associated CustomerProperty record is required via the CustomerPropertyId field on the InsurancePolicyAsset. This is a Salesforce FSC-specific object.

 |
| 

`AssetPartyRelationship__c`

 | 

`InsurancePolicyParticipant`

 | 

For InsurancePolicyParticipant, an associated Contact record is required via the PrimaryParticipantContactId on the InsurancePolicyParticipant.

 |
| 

`InsuredItemPartyRelationship__c`

 | 

`InsurancePolicyMemberAsset`

 |  |
| 

`AssetTransaction__c`

 | 

`InsurancePolicyTransaction__c`

 |  |
| 

`AssetPricingAdjustment__c`

 | 

`InsurancePolicyPricingAdjustment__c`

 |  |
| 

`AssetRevenueScheduleEntry__c`

 | 

`InsurancePolicyRevenueScheduleEntry__c`

 |  |

[](https://help.salesforce.com/s?language=en_US)

## Data Mappers and Custom Classes

The Insurance Industries Extension package comes with Data Mappers and custom classes that you can use in conjunction with InsPolicyService and InsPolicyRevenueScheduleService services.

Note

You can change the contents of these Data Mappers to fit your business needs.

For example, you can use the `additionalFields` key to query your own custom fields and add them to the Data Mappers we provide.

These fields won't show up on the Vlocity policy UI, but you can map attribute values to these custom fields using the InsPolicyService:createUpdatePolicy and InsPolicyService:createPolicyVersion services.

These Data Mappers and custom classes let you use these services with the Salesforce FSC data model without having to write your own Data Mappers or custom classes.

-   getFSCPolicyDetail
    
    Retrieves FSC data model and converts it to InsPolicy interface
    
-   postFSCPolicyDetailGeneric
    
    Takes in InsPolicy interface, converts it to FSC data model, and inserts the records
    
-   postVersionFSCPolicyDetail
    
    Takes in InsPolicy interface, converts it to FSC data model, and inserts the records. The main difference from postFSCPolicyDetailGeneric is that any transaction and revenue schedule records are linked to the original policy version instead of the newly created policy
    
-   updateFSCPolicyDetailGeneric
    
    Takes in InsPolicy interface, converts it to FSC data model, and updates the target records
    
-   postFSCPolicyTransaction
    
    Takes in InsPolicy interface, specifically `InsTransaction`, converts it to an `InsurancePolicyTransaction__c` record, and inserts the record
    
-   getFSCPolicyRevenue
    
    Retrieves the FSC data model, specifically the InsurancePolicyTransaction\_\_c and InsurancePolicyRevenueSchedule\_\_c records, and converts it to the InsPolicy interface
    
-   updateFSCPolicyRevenue
    
    Takes in InsPolicy interface, specifically the InsRevenue, converts it to InsurancePolicyRevenueScheulde\_\_c records, and updates the target records
    
-   postFSCPolicyRevenue
    
    Takes in InsPolicy interface, specifically the InsRevenue, converts it to InsurancePolicyRevenueScheulde\_\_c records, and inserts the records
    

The custom classes included with the Insurance Industries Extension package are:

-   CancelPolicyRevenue
    
    Takes in InsPolicy interface, specifically the InsRevenue, and deletes/updates the associated InsurancePolicyRevenueSchedule\_\_c records
    
-   GetInsurancePolicy
    
    Retrieves FSC data model and converts it to InsPolicy interface
    

To add these Data Mappers and custom classes to your org, see [Add Insurance Industries Extension Data Mappers and Custom Classes to Your Org](https://help.salesforce.com/s/articleView?id=ind.insurance_add_iie_data_mappers_and_custom_classes_to_your_org.htm&language=en_US&type=5 "The Insurance Industries Extension package comes with Omnistudio Data Mappers and custom classes that you can use in conjunction with InsPolicyService and InsPolicyRevenueScheduleService services. Add these Data Mappers and custom classes to your org, and change the contents of the Data Mappers to fit your business needs.").

## Policy Service to Data Mapper and Custom Class Mapping

Here's a list of Policy services and the Data Mappers or Custom Classes they use for Insurance Industries Extension.

| 
Vlocity Insurance Service

 | 

Related Service Option: Data Raptor or Custom Class

 |
| --- | --- |
| 

[InsPolicyService:createUpdatePolicy](https://help.salesforce.com/s/articleView?id=ind.insurance_inspolicyservice__createupdatepolicy.htm&language=en_US&type=5 "Use this service to create a new insurance policy or to update an existing policy with new information.")

 | 

`postDataDRBundleName: postFSCPolicyDetailGeneric`

 |
| 

[InsPolicyService:createPolicyVersion](https://help.salesforce.com/s/articleView?id=ind.insurance_inspolicyservice__createpolicyversion.htm&language=en_US&type=5 "Use this service to create a new version of an existing policy, while maintaining the existing policy record as-is.")

 | 

-   `getDataDRBundleName: getFSCPolicyDetail`
    
-   `updateDataDRBundleName: updateFSCPolicyDetailGeneric`
    
-   `postDataDRBundleName: postVersionFSCPolicyDetailGeneric`
    

 |
| 

[InsPolicyService:getModifiedPolicy](https://help.salesforce.com/s/articleView?id=ind.insurance_inspolicyservice__getmodifiedpolicy.htm&language=en_US&type=5 "Use this service when a user makes changes to the insured items or insured parties in an existing policy. The service takes the changes the user makes and returns modified policy data, including the recalculated price.")

 | 

`getDataDRBundleName: getFSCPolicyDetail`

 |
| 

[InsPolicyService:getInsuredItems](https://help.salesforce.com/s/articleView?id=ind.insurance_inspolicyservice__getinsureditems.htm&language=en_US&type=5 "Use this service to find and return insured items and insured parties from a policy (asset).")

 | 

`getDataDRBunldeName: getFSCPolicyDetail`

 |
| 

[InsPolicyService:removeInsuredItem](https://help.salesforce.com/s/articleView?id=ind.insurance_inspolicyservice__removeinsureditem.htm&language=en_US&type=5 "Use this service to remove an insured item from an existing policy.")

 | 

`getDataDRBundleName: getFSCPolicyDetail`

 |
| 

[InsPolicyService:prepareToCancelPolicy](https://help.salesforce.com/s/articleView?id=ind.insurance_inspolicyservice__preparetocancelpolicy.htm&language=en_US&type=5 "Use this service to calculate the premium price difference before canceling a policy. The service prorates the premium, fee, and tax amounts, and calculates the premium, fee, and tax refund.")

 | 

`getDataDRBundleName: getFSCPolicyDetail`

 |
| 

[InsPolicyService:cancelPolicy](https://help.salesforce.com/s/articleView?id=ind.insurance_inspolicyservice__cancelpolicy.htm&language=en_US&type=5 "Use this service to cancel an existing insurance policy.")

 | 

-   `getDataDRBundleName: getFSCPolicyDetail`
    
-   `updateDataDRBundleName: updateFSCPolicyDetailGeneric`
    

 |
| 

[InsPolicyService:createTransaction](https://help.salesforce.com/s/articleView?id=ind.insurance_inspolicyservice__createtransaction.htm&language=en_US&type=5 "Use this service to create a transaction on a target policy.")

 | 

`postDataDRBundleName: postFSCPolicyTransaction`

 |
| 

[InsPolicyService:getPolicyDetails](https://help.salesforce.com/s/articleView?id=ind.insurance_inspolicyservice__getpolicydetails.htm&language=en_US&type=5 "Use this service to get the coverages, insured items, pricing, and other information for an existing insurance policy, including optional coverages that weren't selected.")

 | 

`getDataDRBundleName: getFSCPolicyDetail`

 |
| 

[InsPolicyRevenueScheduleService:createRevenueSchedule](https://help.salesforce.com/s/articleView?id=ind.insurance_inspolicyrevenuescheduleservice__createrevenueschedule.htm&language=en_US&type=5 "This service creates a monthly revenue schedule for a policy, starting on the effective date of the policy and ending on the expiration date of the policy term.")

 | 

-   `getDataDRBundleName: getFSCPolicyRevenue`
    
-   `postDataDRBundleName: postFSCPolicyRevenue`
    

 |
| 

[InsPolicyRevenueScheduleService:modifyRevenueSchedule](https://help.salesforce.com/s/articleView?id=ind.insurance_inspolicyrevenuescheduleservice__modifyrevenueschedule.htm&language=en_US&type=5 "This service takes in the modifications done to the policy. Based on the changes to total policy premium and the modification date, it recalculates the revenue schedule to adjust the unpaid monthly premiums (unearned revenue).")

 | 

-   `getDataDRBundleName: getFSCPolicyRevenue`
    
-   `updateDataDRBundleName: updateFSCPolicyRevenue`
    

 |
| 

[InsPolicyRevenueScheduleService:cancelRevenueSchedule](https://help.salesforce.com/s/articleView?id=ind.insurance_inspolicyrevenuescheduleservice__cancelrevenueschedule.htm&language=en_US&type=5 "When a policy is canceled, this service adjusts the revenue schedule to calculate revenue until the cancellation date.")

 | 

-   `getDataDRBundleName: getFSCPolicyRevenue`
    
-   `cancelRevenueCustomClassName: CancelPolicyRevenue`
    

 |

[](https://help.salesforce.com/s?language=en_US)

## Creating Your Own Custom Classes

If the Data Mappers and custom classes included with the Insurance Industries Extension package don't work for your business needs, you can write your own custom classes to work with the InsPolicy interface to get or post data in the Salesforce FSC policy object. See [Create Custom Classes for the InsPolicy Interface](https://help.salesforce.com/s/articleView?id=ind.insurance_create_custom_classes_for_the_inspolicy_interface_650699.htm&language=en_US&type=5 "If the Omnistudio Data Mappers and custom classes included with the Insurance Industries Extension package don't work for your business needs, you can write your own custom classes to work with the InsPolicy interface to get or post data in the Salesforce FSC policy object.").

-   **[Add Insurance Industries Extension Data Mappers and Custom Classes to Your Org](https://help.salesforce.com/s/articleView?id=ind.insurance_add_iie_data_mappers_and_custom_classes_to_your_org.htm&language=en_US&type=5)**  
    The Insurance Industries Extension package comes with Omnistudio Data Mappers and custom classes that you can use in conjunction with InsPolicyService and InsPolicyRevenueScheduleService services. Add these Data Mappers and custom classes to your org, and change the contents of the Data Mappers to fit your business needs.
-   **[Create Custom Classes for the InsPolicy Interface](https://help.salesforce.com/s/articleView?id=ind.insurance_create_custom_classes_for_the_inspolicy_interface_650699.htm&language=en_US&type=5)**  
    If the Omnistudio Data Mappers and custom classes included with the Insurance Industries Extension package don't work for your business needs, you can write your own custom classes to work with the InsPolicy interface to get or post data in the Salesforce FSC policy object.

Did this article solve your issue?

Let us know so we can improve!

YesNo