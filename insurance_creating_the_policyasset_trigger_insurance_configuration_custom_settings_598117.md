---
title: "Creating the PolicyAsset Trigger Insurance Configuration Custom Settings"
source: "https://help.salesforce.com/s/articleView?id=ind.insurance_creating_the_policyasset_trigger_insurance_configuration_custom_settings_598117.htm&language=en_US&type=5"
scraped: "2026-04-14"
filter: "ind.insurance_"
---# Creating the PolicyAsset Trigger Insurance Configuration Custom Settings

Creating the PolicyAsset Trigger Insurance Configuration Custom Settings[](https://help.salesforce.com/s?language=en_US)

You are here:

1.  [Salesforce Help](/s/?language=en_US)
2.  [Docs](/s/products?language=en_US)
3.  [Digital Insurance](https://help.salesforce.com/s/articleView?id=ind.insurance_admin_standard.htm&language=en_US&type=5)

# Creating the PolicyAsset Trigger Insurance Configuration Custom Settings

The PolicyAsset trigger supports the automatic creation of the policyholder relationship in a contact center use case. This trigger uses Insurance Configuration Custom Settings rather than a Trigger Setup Custom Setting to turn it on or off.

To enable the two Insurance Configuration Custom Settings for the PolicyAsset trigger:

1.  From **Setup**, in the **Quick Find** box, enter Custom Settings.
2.  Click **Custom Settings**.
3.  Click **Manage** next to **Insurance Configuration Settings**.
4.  Click **New**.
5.  Enter a **Name**.
6.  Enter a **Setup Value**.
7.  Click **Save**.
    
    Create the Insurance Configuration Custom Setting used to specify the Policy (Asset) record types with the following parameters:
    
    -   **Name**: PolicyRecordTypes+<number>
        
    -   **Setup Value**: Asset record type developerNames
        
        _Example_:
        
        **Name**: PolicyRecordTypes1
        
        **Setup Value**: Default,Investment,IndividualLife,PersonalLinesName
        
        You can add Setup Values as applicable, however, the field only allows up to 255 characters. If the values needed exceed 255 characters, you can add additional Insurance Configuration Custom Settings by following the above steps, and changing the number in the name.
        
        _Example_:
        
        **Name**: PolicyRecordTypes2
        
        **Setup Value**: IndividualAnnuity,CommercialLines,IndividualHealth
        
    
    [](https://help.salesforce.com/s?language=en_US)Create the Insurance Configuration Custom Setting used to specify the relationship type to the Account Master/Detail, lookup field or Contact lookup field with the following parameters:
    
    -   **Name**: AccountFieldPolicyRoles+<number> or ContactFieldPolicyRoles+<number>
        
    -   **Setup Value**: fieldName (including nameSpace):relationshipType
        
        _Example_:
        
        **Name**: AccountFieldPolicyRoles1
        
        **Setup Value**: AccountId:Policyholder
        
    

[](https://help.salesforce.com/s?language=en_US)

You've enabled the PolicyAsset trigger once both Insurance Configuration Custom Settings exist.

Did this article solve your issue?

Let us know so we can improve!

YesNo