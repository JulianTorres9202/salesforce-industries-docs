---
title: "Apex Triggers for Insurance"
source: "https://help.salesforce.com/s/articleView?id=ind.insurance_vlocity_apex_triggers_for_insurance_597956.htm&language=en_US&type=5"
scraped: "2026-04-14"
filter: "ind.insurance_"
---# Apex Triggers for Insurance

Apex Triggers for Insurance[](https://help.salesforce.com/s?language=en_US)

You are here:

1.  [Salesforce Help](/s/?language=en_US)
2.  [Docs](/s/products?language=en_US)
3.  [Digital Insurance](https://help.salesforce.com/s/articleView?id=ind.insurance_admin_standard.htm&language=en_US&type=5)

# Apex Triggers for Insurance

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

Contact

 | 

[InsuranceContact](https://help.salesforce.com/s/articleView?id=ind.insurance_vlocity_apex_triggers_for_insurance_597956.htm&language=en_US&type=5 "A trigger is Apex code that runs before or after a specific data manipulation language (DML) event occurs, such as before the insertion or after the deletion of records in a database. Salesforce stores triggers as metadata. By modifying Salesforce custom settings, you can enable and disable Insurance Apex triggers as required by your implementation.")

 | 

Party.EnablePartyModel

 | 

Off

 |
| 

Producer.EnableAutoRelationship

 | 

Off

 |
| 

ContentDocumentLink

 | 

[ContentDocumentLink](https://help.salesforce.com/s/articleView?id=ind.insurance_vlocity_apex_triggers_for_insurance_597956.htm&language=en_US&type=5 "A trigger is Apex code that runs before or after a specific data manipulation language (DML) event occurs, such as before the insertion or after the deletion of records in a database. Salesforce stores triggers as metadata. By modifying Salesforce custom settings, you can enable and disable Insurance Apex triggers as required by your implementation.")

 | 

ContentDocumentLink.ShareProductImage

 | 

Off

 |
| 

Policy (Asset)

 | 

[PolicyAsset](https://help.salesforce.com/s/articleView?id=ind.insurance_vlocity_apex_triggers_for_insurance_597956.htm&language=en_US&type=5 "A trigger is Apex code that runs before or after a specific data manipulation language (DML) event occurs, such as before the insertion or after the deletion of records in a database. Salesforce stores triggers as metadata. By modifying Salesforce custom settings, you can enable and disable Insurance Apex triggers as required by your implementation.")

 | 

N/A: This trigger uses Insurance Configuration Custom Settings.

 | 

N/A

 |
| 

Product2

 | 

[InsuranceProduct](https://help.salesforce.com/s/articleView?id=ind.insurance_vlocity_apex_triggers_for_insurance_597956.htm&language=en_US&type=5 "A trigger is Apex code that runs before or after a specific data manipulation language (DML) event occurs, such as before the insertion or after the deletion of records in a database. Salesforce stores triggers as metadata. By modifying Salesforce custom settings, you can enable and disable Insurance Apex triggers as required by your implementation.")

 | 

InsuranceProductTrigger

 | 

On

 |

[](https://help.salesforce.com/s?language=en_US)

## InsuranceContact

The InsuranceContact trigger supports Party Model relationships.

How it works:

If an Account has the record type of AgencyBrokerage, and this Contact has the Producer record type, then a Party relationship is automatically created.

Note

The Party.EnablePartyModel and Producer.EnableAutoRelationship trigger handlers are off by default. The InsuranceContact trigger is only on when both trigger handlers are on.

[](https://help.salesforce.com/s?language=en_US)

## ContentDocumentLink

The ContentDocumentLink trigger supports product image sharing.

How it works:

If you upload a content document for a product, and the document title starts with “prodImage\_” and its visibility is not set to **AllUsers**, then automatically set it to **AllUsers**.

[](https://help.salesforce.com/s?language=en_US)

## PolicyAsset

The PolicyAsset trigger supports the automatic creation of the policyholder relationship in a contact center use case. This trigger uses Insurance Configuration Custom Settings rather than a Trigger Setup Custom Setting to turn it on or off.

How it works:

When an Asset is inserted, you automatically create an AssetPartyRelationship record for it if it meets the following criteria:

-   The Asset's Record Type matches one of the Types specified in the PolicyRecordTypes custom setting.
    
-   A field specified in either AccountFieldPolicyRoles or ContactFieldPolicyRoles is populated
    
-   The Relationship Type is available.
    

If an Asset is updated, you automatically create an AssetPartyRelationship record for it if it meets the following criteria:

-   The Asset's Record Type matches one of the Types specified in the PolicyRecordTypes custom setting.
    
-   A field specified in either AccountFieldPolicyRoles or ContactFieldPolicyRoles is populated that was null previously.
    
-   The Relationship Type is available.
    

See [Creating the PolicyAsset Trigger Insurance Configuration Custom Settings](https://help.salesforce.com/s/articleView?id=ind.insurance_creating_the_policyasset_trigger_insurance_configuration_custom_settings_598117.htm&language=en_US&type=5 "The PolicyAsset trigger supports the automatic creation of the policyholder relationship in a contact center use case. This trigger uses Insurance Configuration Custom Settings rather than a Trigger Setup Custom Setting to turn it on or off.") to learn how to enable the Insurance Configuration Custom Settings required for this trigger.

[](https://help.salesforce.com/s?language=en_US)

## InsuranceProduct

The InsuranceProduct trigger supports Product Class Plan Renewal (to ensure that the replacementProductId is set when you retire a product), and Benefit Catalog Change tracking.

How it works:

Create/update PriceBookEntry based on StandardPremium\_\_c.

RatingCalcProcedureName\_\_c is populated from the parent product's Product Class if it is empty.

ReplacementProductId\_\_c is required if EnrollmentStatus\_\_c is set to Retired or Inactive.

If the EligibilityCriteria\_\_c, EligibilityCriteriaComments\_\_c, or HelpText\_\_c fields are changed, creates a new ProductConfigurationChangeLog\_\_c record to capture the change.

In addition to the InsuranceProductTrigger, you also need to enable an Insurance Configuration Setup Custom Setting to turn on this trigger. See [Creating the InsuranceProduct Trigger Insurance Configuration Custom Setting](https://help.salesforce.com/s/articleView?id=ind.insurance_creating_the_insuranceproduct_trigger_insurance_configuration_customsetting_598077.htm&language=en_US&type=5 "In addition to the InsuranceProductTrigger, you also need to enable an Insurance Configuration Setup Custom Setting to turn on the trigger.") to learn how.

Did this article solve your issue?

Let us know so we can improve!

YesNo