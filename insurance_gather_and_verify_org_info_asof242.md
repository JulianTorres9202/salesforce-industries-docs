---
title: "Gather and Verify Info About Your Insurance Org"
source: "https://help.salesforce.com/s/articleView?id=ind.insurance_gather_and_verify_org_info_asof242.htm&language=en_US&type=5"
scraped: "2026-04-14"
filter: "ind.insurance_"
---# Gather and Verify Info About Your Insurance Org

Gather and Verify Info About Your Insurance Org[](https://help.salesforce.com/s?language=en_US)

You are here:

1.  [Salesforce Help](/s/?language=en_US)
2.  [Docs](/s/products?language=en_US)
3.  [Digital Insurance](https://help.salesforce.com/s/articleView?id=ind.insurance_admin_standard.htm&language=en_US&type=5)

# Gather and Verify Info About Your Insurance Org

Before you upgrade, do some preliminary work in your current org. These tasks inform your decision about an upgrade path, and prepare you for extra steps that can apply to your upgrade.

[](https://help.salesforce.com/s?language=en_US)

1.  Confirm which version of packages you're using.
    
    In **Setup**, find and select Installed Packages, then note the **Version Number** of the following packages:
    
    [](https://help.salesforce.com/s?language=en_US)
    -   Vlocity Insurance
    -   Vlocity Installation Assistant INS
    -   vlocity\_ins\_unmanaged
2.  Answer essential questions about your org.[](https://help.salesforce.com/s?language=en_US)
    -   What type of org do you have?
        -   Dev sandbox (Dev, early QA)
            
            Doesn't have Vlocity specifics such as custom objects, fieldsets, and templates
            
        -   Partial sandbox (QA org)
            
            Includes some Vlocity specifics such as custom objects, fieldsets, and templates
            
        -   Full sandbox (UAT, possibly QA org)
            
            Includes all Vlocity specifics from Production without any setup required
            
        -   Production
            
            Includes all Vlocity specifics from the previous installation
            
    -   Is Vlocity Contract Lifecycle Management in use?
3.  Find out whether your org has custom cards or templates and decide whether to maintain them or customize the new versions.[](https://help.salesforce.com/s?language=en_US)
    1.  From the App Launcher, find and select **Vlocity Templates**,
    2.  Check the **Last Modified By ID** column value for each template.
        
        [](https://help.salesforce.com/s?language=en_US)Customized cards and templates show an ID other than the original Vlocity out-of-the-box ID. After new cards and templates are installed and activated, you can customize them in the same ways. Or you can deactivate the new cards and templates and reactivate your older customized versions.
        
4.  Verify that [Vlocity Support Processes](https://help.salesforce.com/s/articleView?id=ind.insurance_activate_vlocity_support_processes.htm&language=en_US&type=5 "Before you upgrade Insurance, activate Vlocity Support Processes.") are active.
5.  Verify that the [Allow Activities](https://help.salesforce.com/s/articleView?id=ind.insurance_enable_allow_activities_on_activity_template.htm&language=en_US&type=5 "Before you upgrade Insurance, enable the Allow Activities setting on the Activity Template object.") option is selected on the Activity Template object.
6.  Verify that the [Party.EnablePartyModel custom setting](https://help.salesforce.com/s/articleView?id=ind.insurance_verify_the_party_enablepartymodel_custom_setting.htm&language=en_US&type=5 "Before you upgrade managed packages, make sure the Party.EnablePartyModel custom setting exists in your org.") is in your org.

-   **[Activate Vlocity Support Processes](https://help.salesforce.com/s/articleView?id=ind.insurance_activate_vlocity_support_processes.htm&language=en_US&type=5)**  
    Before you upgrade Insurance, activate Vlocity Support Processes.
-   **[Enable Allow Activities on Activity Template](https://help.salesforce.com/s/articleView?id=ind.insurance_enable_allow_activities_on_activity_template.htm&language=en_US&type=5)**  
    Before you upgrade Insurance, enable the Allow Activities setting on the Activity Template object.
-   **[Verify the Party.EnablePartyModel Custom Setting](https://help.salesforce.com/s/articleView?id=ind.insurance_verify_the_party_enablepartymodel_custom_setting.htm&language=en_US&type=5)**  
    Before you upgrade managed packages, make sure the Party.EnablePartyModel custom setting exists in your org.

Did this article solve your issue?

Let us know so we can improve!

YesNo