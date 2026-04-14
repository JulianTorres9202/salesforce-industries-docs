---
title: "Enable or Disable the Insurance Industries Extension Data Model"
source: "https://help.salesforce.com/s/articleView?id=ind.insurance_enable_the_pre_existing_insurance_industries_extension_data_model_598317.htm&language=en_US&type=5"
scraped: "2026-04-14"
filter: "ind.insurance_"
---# Enable or Disable the Insurance Industries Extension Data Model

Enable or Disable the Insurance Industries Extension Data Model[](https://help.salesforce.com/s?language=en_US)

You are here:

1.  [Salesforce Help](/s/?language=en_US)
2.  [Docs](/s/products?language=en_US)
3.  [Digital Insurance](https://help.salesforce.com/s/articleView?id=ind.insurance_admin_standard.htm&language=en_US&type=5)

# Enable or Disable the Insurance Industries Extension Data Model

When you install or upgrade to the Insurance managed package and the Insurance Industries Extension package, the Insurance Policy core object model is automatically enabled. But if you're upgrading and you're not prepared to use the Insurance Policy core object model yet, use a custom setting to disable the use of the core object model until you're ready to make the switch.

Note You must have a **Salesforce FSC** license, a **Policy Administration** license, and a **Claims Management** license for the Insurance Policy core object model to enable automatically when you install or upgrade. In addition, Financial Services Cloud orgs must have the Insurance Contract and Enroll add-on license, and Health Cloud orgs must have the Benefits Sales & Administration - Group add-on license.

1.  From Setup, in the Quick Find box, enter Custom Settings, and then select **Custom Settings**.
2.  Click **I** in the alphabet menu:
3.  Next to `Insurance Configuration Setup`, click **Manage**.
4.  Next to `useVlocityPolicyModel`, click **Edit**.
5.  For **Setup Value**:
    
    -   To use the Insurance Policy core object model, enter False or false. This is the default value.
        
    -   To use the Asset data model, enter True or true. This is the recommended setting if you upgrade from an earlier release and you're not prepared to move to the Insurance Policy core object model yet.
        
    
6.  Click **Save**.

Did this article solve your issue?

Let us know so we can improve!

YesNo