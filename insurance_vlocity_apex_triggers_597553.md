---
title: "Learn About Apex Triggers"
source: "https://help.salesforce.com/s/articleView?id=ind.insurance_vlocity_apex_triggers_597553.htm&language=en_US&type=5"
scraped: "2026-04-14"
filter: "ind.insurance_"
---# Learn About Apex Triggers

Learn About Apex Triggers[](https://help.salesforce.com/s?language=en_US)

You are here:

1.  [Salesforce Help](/s/?language=en_US)
2.  [Docs](/s/products?language=en_US)
3.  [Digital Insurance](https://help.salesforce.com/s/articleView?id=ind.insurance_admin_standard.htm&language=en_US&type=5)

# Learn About Apex Triggers

A trigger is Apex code that runs before or after a specific data manipulation language (DML) event occurs, such as before the insertion or after the deletion of records in a database. Salesforce stores triggers as metadata. By modifying Salesforce custom settings, you can enable and disable Insurance Apex triggers as required by your implementation.

See [Enabling and Disabling Vlocity Apex Triggers](https://help.salesforce.com/s/articleView?id=ind.insurance_enabling_and_disabling_vlocity_apex_triggers_597899.htm&language=en_US&type=5 "You can use Salesforce Custom Settings to enable or disable Vlocity Apex triggers.") to learn how.

[](https://help.salesforce.com/s?language=en_US)

## Trigger Details

| 
Object

 | 

Trigger Name

 | 

Trigger Handler Name

 | 

Default On/Off

 |
| --- | --- | --- | --- |
| 

Account

 | 

[Account](https://help.salesforce.com/s/articleView?id=ind.insurance_vlocity_apex_triggers_597553.htm&language=en_US&type=5 "A trigger is Apex code that runs before or after a specific data manipulation language (DML) event occurs, such as before the insertion or after the deletion of records in a database. Salesforce stores triggers as metadata. By modifying Salesforce custom settings, you can enable and disable Insurance Apex triggers as required by your implementation.")

 | 

Party.EnablePartyModel

 | 

Off

 |
| 

Account.EnableTrigger

 | 

On

 |
| 

Attachment

 | 

[Attachment](https://help.salesforce.com/s/articleView?id=ind.insurance_vlocity_apex_triggers_597553.htm&language=en_US&type=5 "A trigger is Apex code that runs before or after a specific data manipulation language (DML) event occurs, such as before the insertion or after the deletion of records in a database. Salesforce stores triggers as metadata. By modifying Salesforce custom settings, you can enable and disable Insurance Apex triggers as required by your implementation.")

 | 

Attachment.EnableTrigger

 | 

On

 |
| 

[CmAttachment](https://help.salesforce.com/s/articleView?id=ind.insurance_vlocity_apex_triggers_597553.htm&language=en_US&type=5 "A trigger is Apex code that runs before or after a specific data manipulation language (DML) event occurs, such as before the insertion or after the deletion of records in a database. Salesforce stores triggers as metadata. By modifying Salesforce custom settings, you can enable and disable Insurance Apex triggers as required by your implementation.")

 | 

CmAttachment.EnableTrigger

 | 

On

 |
| 

CampaignMember

 | 

[CampaignActionMemberLog](https://help.salesforce.com/s/articleView?id=ind.insurance_vlocity_apex_triggers_597553.htm&language=en_US&type=5 "A trigger is Apex code that runs before or after a specific data manipulation language (DML) event occurs, such as before the insertion or after the deletion of records in a database. Salesforce stores triggers as metadata. By modifying Salesforce custom settings, you can enable and disable Insurance Apex triggers as required by your implementation.")

 | 

Enable.CampaignMemberActionLog

 | 

On

 |
| 

Contact

 | 

[Contact](https://help.salesforce.com/s/articleView?id=ind.insurance_vlocity_apex_triggers_597553.htm&language=en_US&type=5 "A trigger is Apex code that runs before or after a specific data manipulation language (DML) event occurs, such as before the insertion or after the deletion of records in a database. Salesforce stores triggers as metadata. By modifying Salesforce custom settings, you can enable and disable Insurance Apex triggers as required by your implementation.")

 | 

Party.EnablePartyModel

 | 

Off

 |
| 

Contact.EnableTrigger

 | 

On

 |
| 

ContentVersion

 | 

[ContentVersion](https://help.salesforce.com/s/articleView?id=ind.insurance_vlocity_apex_triggers_597553.htm&language=en_US&type=5 "A trigger is Apex code that runs before or after a specific data manipulation language (DML) event occurs, such as before the insertion or after the deletion of records in a database. Salesforce stores triggers as metadata. By modifying Salesforce custom settings, you can enable and disable Insurance Apex triggers as required by your implementation.")

 | 

ContentVersion.EnableTrigger

 | 

Off

 |
| 

Contract

 | 

[CmContract](https://help.salesforce.com/s/articleView?id=ind.insurance_vlocity_apex_triggers_597553.htm&language=en_US&type=5 "A trigger is Apex code that runs before or after a specific data manipulation language (DML) event occurs, such as before the insertion or after the deletion of records in a database. Salesforce stores triggers as metadata. By modifying Salesforce custom settings, you can enable and disable Insurance Apex triggers as required by your implementation.")

 | 

Contract.EnableTrigger

 | 

On

 |
| 

Contract.EnableStateModel

 | 

Off

 |
| 

Contract.EnableUpdateDocSections

 | 

Off

 |
| 

Opportunity

 | 

[Opportunity](https://help.salesforce.com/s/articleView?id=ind.insurance_vlocity_apex_triggers_597553.htm&language=en_US&type=5 "A trigger is Apex code that runs before or after a specific data manipulation language (DML) event occurs, such as before the insertion or after the deletion of records in a database. Salesforce stores triggers as metadata. By modifying Salesforce custom settings, you can enable and disable Insurance Apex triggers as required by your implementation.")

 | 

Opportunity.EnableTrigger

 | 

On

 |
| 

Order

 | 

[XOMOrderTrigger](https://help.salesforce.com/s/articleView?id=ind.insurance_vlocity_apex_triggers_597553.htm&language=en_US&type=5 "A trigger is Apex code that runs before or after a specific data manipulation language (DML) event occurs, such as before the insertion or after the deletion of records in a database. Salesforce stores triggers as metadata. By modifying Salesforce custom settings, you can enable and disable Insurance Apex triggers as required by your implementation.")

 | 

XOM.EnableXOMTriggers

 | 

Off

 |
| 

Order Item

 | 

[XOMTriggerOrderItem](https://help.salesforce.com/s/articleView?id=ind.insurance_vlocity_apex_triggers_597553.htm&language=en_US&type=5 "A trigger is Apex code that runs before or after a specific data manipulation language (DML) event occurs, such as before the insertion or after the deletion of records in a database. Salesforce stores triggers as metadata. By modifying Salesforce custom settings, you can enable and disable Insurance Apex triggers as required by your implementation.")

 | 

XOM.EnableXOMTriggers

 | 

Off

 |
| 

Product2

 | 

[EPCProduct](https://help.salesforce.com/s/articleView?id=ind.insurance_vlocity_apex_triggers_597553.htm&language=en_US&type=5 "A trigger is Apex code that runs before or after a specific data manipulation language (DML) event occurs, such as before the insertion or after the deletion of records in a database. Salesforce stores triggers as metadata. By modifying Salesforce custom settings, you can enable and disable Insurance Apex triggers as required by your implementation.")

 | 

EPCProductTrigger

 | 

On

 |
| 

[CpqProduct](https://help.salesforce.com/s/articleView?id=ind.insurance_vlocity_apex_triggers_597553.htm&language=en_US&type=5 "A trigger is Apex code that runs before or after a specific data manipulation language (DML) event occurs, such as before the insertion or after the deletion of records in a database. Salesforce stores triggers as metadata. By modifying Salesforce custom settings, you can enable and disable Insurance Apex triggers as required by your implementation.")

 | 

CpqProduct.EnableTrigger

 | 

On

 |
| 

[XOMProduct2Trigger](https://help.salesforce.com/s/articleView?id=ind.insurance_vlocity_apex_triggers_597553.htm&language=en_US&type=5 "A trigger is Apex code that runs before or after a specific data manipulation language (DML) event occurs, such as before the insertion or after the deletion of records in a database. Salesforce stores triggers as metadata. By modifying Salesforce custom settings, you can enable and disable Insurance Apex triggers as required by your implementation.")

 | 

XOM.EnableXOMTriggers

 | 

Off

 |
| 

User

 | 

[XOMUserTrigger](https://help.salesforce.com/s/articleView?id=ind.insurance_vlocity_apex_triggers_597553.htm&language=en_US&type=5 "A trigger is Apex code that runs before or after a specific data manipulation language (DML) event occurs, such as before the insertion or after the deletion of records in a database. Salesforce stores triggers as metadata. By modifying Salesforce custom settings, you can enable and disable Insurance Apex triggers as required by your implementation.")

 | 

XOM.EnableXOMTriggers

 | 

Off

 |
| 

[User](https://help.salesforce.com/s/articleView?id=ind.insurance_vlocity_apex_triggers_597553.htm&language=en_US&type=5 "A trigger is Apex code that runs before or after a specific data manipulation language (DML) event occurs, such as before the insertion or after the deletion of records in a database. Salesforce stores triggers as metadata. By modifying Salesforce custom settings, you can enable and disable Insurance Apex triggers as required by your implementation.")

 | 

Cards.UserTrigger

 | 

On

 |

[](https://help.salesforce.com/s?language=en_US)

## Account

The Account trigger supports TaxId format validation and Party record creation.

How it works:

When the Account is created or updated, the trigger creates or updates the Party record if the Party.EnablePartyModel trigger handler is set to On. If the value of the Account's TaxId field is changed or populated, the trigger validates the format of the TaxId.

[](https://help.salesforce.com/s?language=en_US)

## Attachment

The switch to control the Attachment trigger is available starting in Insurance Spring '20 release.

How it works:

On beforeUpdate and beforeInsert, if an Attachment's parent is a Product record, and the Attachment's name starts with 'TN' then set this product's ImageId\_\_c to this attachment's Id

[](https://help.salesforce.com/s?language=en_US)

## CmAttachment

The switch to control the CMAttachment trigger is available starting in the Insurance Spring '20 release. This trigger supports contract document links.

How it works:

After an Attachment is inserted, if the Attachment's parent is a ContractVersion\_\_c record, the trigger creates a ContractDocumentCollection\_\_c record.

[](https://help.salesforce.com/s?language=en_US)

## CampaignMemberActionLog

The CampaignMember trigger supports the Campaign Call List execution.

How it works:

When a campaign member is created, deleted, or the lastCallDate is changed, the trigger creates a CampaignMemberActionLog\_\_c record to log the change. If this trigger is off, campaign call list actions are not logged.

[](https://help.salesforce.com/s?language=en_US)

## Contact

The Contact trigger supports TaxId format validation and Party record creation. The party record is used in:

-   Held Party Relationship: used to capture the insured party in an insurance policy, and capture dependents enrolled in plans.
    
-   Claim Party Relationship: used to capture claimants.
    
-   Opportunity referrals.
    

How it works:

When the Contact is created or updated, the trigger creates or updates the Party record if the Party.EnablePartyModel trigger handler is set to On. If the value of the Contact's TaxId field is changed or populated, the trigger validates the format of the TaxId.

[](https://help.salesforce.com/s?language=en_US)

## ContentVersion

The ContentVersion trigger supports Content Profile Attributes.

How it works:

If a new version of a Content Document is created, the trigger copies the attribute assignments for the previous version to this new version.

[](https://help.salesforce.com/s?language=en_US)

## CmContract

The Contract Type trigger supports Contract documents (the automatic creation of the first version and automatically updating sections based on the selected changes), validation of the Contract startDate, endDate and term, and enforces the Contract StateModel.

How it works (in different record states):

-   BeforeInsert:  If the contractType exists in the org, populate the **Contract Type** field for the Contract record based on the record type/contract type configuration.
    
-   BeforeUpdate:
    
    -   If RenewalNotification\_\_c is set and the endDate is not null, the trigger updates the RenewalStartDate\_\_c field based on RenewalNotification\_\_c, RenewalNotificationTerm\_\_c, and EndDate.
        
    -   If the Contract.EnableStateModel setting is on when the Contract's Status field is updated, the triggers checks if the state transition is allowed by the State Model. If the Contract.EnableStateModel doesn't exist or is off, then the State Model is not checked.
        
    -   If the Contract's record type is changed, and if the contractType exists in the org, then check if the contractType needs to change.
        
-   AfterInsert: 
    
    -   Create a contractVersion\_\_c record.
        
    -   If the contract term is null, the trigger checks if the GetContractTerm interface has been overridden. If it is not overridden, the contract term stays as null, otherwise, it can be set according to the override class.
        
-   AfterUpdate: 
    
    -   If the previous startDate is null and the new startDate is not null, the trigger updates all contract lines using the new startDate and endDate.
        
    -   If the previous endDate is null and the new endDate is not null, then the trigger updates the RenewalStartDate\_\_c based on RenewalNotification\_\_c, RenewalNotificationTerm\_\_c, and EndDate.
        
    -   If the Contract.EnableUpdateDocSections setting is on, then the trigger updates the contract document sections of the active contractVersion\_\_c record.
        
    -   If this custom setting is not there or is off, this is not performed. If the contract term is null, the trigger checks if the GetContractTerm interface has been overridden. If it is not overridden, the contract term stays as null, otherwise, it can be set according to the override class.
        

[](https://help.salesforce.com/s?language=en_US)

## Opportunity

The Opportunity trigger supports opportunity referrals.

How it works:

If an Opportunity's Referral Source (PartyId\_\_c) is inserted or updated and the Referral Source is Contact, then the trigger creates Tasks for the Referral Source (PartyId\_r.ContactId).

[](https://help.salesforce.com/s?language=en_US)

## XOMOrderTrigger

The Order trigger supports features for Vlocity Order Management.

How it works:

-   Reset the following fields to default values: OrchestrationPlanId\_\_c, FilfilmentStatus\_\_c, OrchestrationPlanReferenceId\_\_c, ThorJeopardyStatus\_\_c and DueDate\_\_c.
    
-   Propagate the Order Status to downstream Fulfilment Requests and update the FulfilmentStatus\_\_c based on the Order Status.
    
-   Generate data in the RequestedCompletionDate\_\_c field.
    

[](https://help.salesforce.com/s?language=en_US)

## XOMTriggerOrderItem

How it works:

If the Order header field is empty on the Order Item object, then propagate that field based on the RequestedCompletionDate\_\_c.

[](https://help.salesforce.com/s?language=en_US)

## EPCProduct

The EPCProduct trigger supports the population of Global Keys and prevents the deletion of Products that have child Products.

How it works:

The trigger generates the GlobalKey and sets the Product2.GlobalKey\_\_c. Additionally, if you attempt to delete a product, the trigger does a validation check to see if the product has a ProductChildItem record. If a ProductChildItem record exists, the parent product cannot be deleted.

[](https://help.salesforce.com/s?language=en_US)

## CpqProduct

How it works (in different record states):

-   BeforeInsert:
    
    -   Populate the product2.GlobalKey\_\_c if it is empty.
        
    -   Use SellingStartDate\_\_c to set the EffectiveDate\_\_c, or use the EffectiveDate\_\_c to set the SellingStartDate\_\_c.
        
    -   Use SellingEndDate\_\_c to set the EndDate\_\_c, or use the EndDate\_\_c to set SellingEndDate\_\_c.
        
    -   If you are not using SellingStartDate\_\_c or SellingEndDate\_\_c then this logic will not trigger.
        
-   BeforeUpdate:
    
    -   Uses JSONAttribute\_\_c to set isConfigurable\_\_c. In insurance it is recommended that JSONAttribute\_\_c is turned off because AttributeMetadata\_\_c is used instead.
        
    -   Additionally, sync SellingStartDate\_\_c, SellingEndDate\_\_c, EffectiveDate\_\_c, and EndDate\_\_c.
        

[](https://help.salesforce.com/s?language=en_US)

## XOMProduct2Trigger

How it works:

The trigger generates a Global Key if one does not exist. If using Order Management Plus, it generates a Sync Delta Object record for any change made to a product.

[](https://help.salesforce.com/s?language=en_US)

## XOMUserTrigger

The XOMUserTrigger supports the synchronization of users between Salesforce and the Order Management Plus platforms.

How it works:

The trigger creates a SyncDeltaRecord for any changes made to a User object record.

[](https://help.salesforce.com/s?language=en_US)

## User

The User trigger caches the user information in the platform session cache to improve the performance of the getUserProfile call used by several Vlocity products.

How it works:

When a user is updated, the profile information is cached. When a user is deleted, this cached information is removed.

Did this article solve your issue?

Let us know so we can improve!

YesNo