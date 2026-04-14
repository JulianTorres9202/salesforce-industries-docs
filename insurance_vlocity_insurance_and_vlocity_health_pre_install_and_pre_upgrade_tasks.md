---
title: "Prerequisite Tasks for Insurance"
source: "https://help.salesforce.com/s/articleView?id=ind.insurance_vlocity_insurance_and_vlocity_health_pre_install_and_pre_upgrade_tasks.htm&language=en_US&type=5"
scraped: "2026-04-14"
filter: "ind.insurance_"
---# Prerequisite Tasks for Insurance

Prerequisite Tasks for Insurance

You are here:

1.  [Salesforce Help](/s/?language=en_US)
2.  [Docs](/s/products?language=en_US)
3.  [Digital Insurance](https://help.salesforce.com/s/articleView?id=ind.insurance_admin_standard.htm&language=en_US&type=5)

[](https://help.salesforce.com/s?language=en_US)

# Prerequisite Tasks for Insurance

Insurance uses some Salesforce features that aren't enabled by default in a typical org. To ensure Insurance works correctly with Salesforce, complete certain tasks and verify certain settings before you install or upgrade Insurance packages.

-   **[Confirm System Requirements](https://help.salesforce.com/s/articleView?id=ind.insurance_vlocity_insurance_and_vlocity_health_pre_install_and_pre_upgrade_tasks.htm&language=en_US&type=5#insurance_confirm_system_requirements)**  
    Verify that your web browser and Salesforce version meet these minimum requirements.
-   **[Disable Advanced Currency Management](https://help.salesforce.com/s/articleView?id=ind.insurance_vlocity_insurance_and_vlocity_health_pre_install_and_pre_upgrade_tasks.htm&language=en_US&type=5#insurance_disable_advanced_currency_mgmt)**  
    Advanced currency management allows you to manage dated exchange rates within opportunities using Salesforce. To prepare for your installation or upgrade, disable it.
-   **[Empty the Org Recycle Bin](https://help.salesforce.com/s/articleView?id=ind.insurance_vlocity_insurance_and_vlocity_health_pre_install_and_pre_upgrade_tasks.htm&language=en_US&type=5#insurance_empty_org_recycle_bin)**  
    As an admin, you have access to the Salesforce org's Recycle Bin and can delete records from it.
-   **[Enable Contacts to Multiple Accounts](https://help.salesforce.com/s/articleView?id=ind.insurance_vlocity_insurance_and_vlocity_health_pre_install_and_pre_upgrade_tasks.htm&language=en_US&type=5#insurance_enable_contacts_to_multiple_accounts)**  
    To prepare your org for Insurance, allow users to link contacts to multiple accounts.
-   **[Enable Content Deliveries](https://help.salesforce.com/s/articleView?id=ind.insurance_vlocity_insurance_and_vlocity_health_pre_install_and_pre_upgrade_tasks.htm&language=en_US&type=5#insurance_enable_content_deliveries)**  
    To prepare your org for Insurance, enable content deliveries and public links.
-   **[Enable Data Protection and Privacy](https://help.salesforce.com/s/articleView?id=ind.insurance_vlocity_insurance_and_vlocity_health_pre_install_and_pre_upgrade_tasks.htm&language=en_US&type=5#insurance_enable_data_protection_and_privacy)**  
    To prepare your org for Insurance, enable data protection and privacy.
-   **[Enable Enhanced Email](https://help.salesforce.com/s/articleView?id=ind.insurance_vlocity_insurance_and_vlocity_health_pre_install_and_pre_upgrade_tasks.htm&language=en_US&type=5#insurance_enable_enhanced_email)**  
    To prepare your org for Insurance, enable Enhanced Email.
-   **[Enable Forecasts](https://help.salesforce.com/s/articleView?id=ind.insurance_vlocity_insurance_and_vlocity_health_pre_install_and_pre_upgrade_tasks.htm&language=en_US&type=5#insurance_enable_forecasts)**  
    To prepare your org for Insurance, enable Forecasts.
-   **[Enable Salesforce Files Settings](https://help.salesforce.com/s/articleView?id=ind.insurance_vlocity_insurance_and_vlocity_health_pre_install_and_pre_upgrade_tasks.htm&language=en_US&type=5#insurance_enable_salesforce_files_setting)**  
    Enable the Salesforce Files Settings to avoid errors while installing the managed package.
-   **[Enable Multiple Contacts](https://help.salesforce.com/s/articleView?id=ind.insurance_vlocity_insurance_and_vlocity_health_pre_install_and_pre_upgrade_tasks.htm&language=en_US&type=5#insurance_enable_multiple_contacts)**  
    To prepare your org for Insurance, allow users to relate multiple contacts to tasks and events.
-   **[Enable Orders](https://help.salesforce.com/s/articleView?id=ind.insurance_vlocity_insurance_and_vlocity_health_pre_install_and_pre_upgrade_tasks.htm&language=en_US&type=5#insurance_enable_orders)**  
    To prepare your org for Insurance, enable Orders.
-   **[Enable Product Scheduling](https://help.salesforce.com/s/articleView?id=ind.insurance_vlocity_insurance_and_vlocity_health_pre_install_and_pre_upgrade_tasks.htm&language=en_US&type=5#insurance_enable_product_scheduling)**  
    To prepare your org for Insurance, enable Product Scheduling.
-   **[Enable Quotes](https://help.salesforce.com/s/articleView?id=ind.insurance_vlocity_insurance_and_vlocity_health_pre_install_and_pre_upgrade_tasks.htm&language=en_US&type=5#insurance_enable_quotes)**  
    To prepare your org for Insurance, enable Quotes.
-   **[Enable Salesforce CRM Content](https://help.salesforce.com/s/articleView?id=ind.insurance_vlocity_insurance_and_vlocity_health_pre_install_and_pre_upgrade_tasks.htm&language=en_US&type=5#insurance_enable_salesforce_crm_content)**  
    To prepare your org for Insurance, enable Salesforce CRM Content.
-   **[Enable Work Orders](https://help.salesforce.com/s/articleView?id=ind.insurance_vlocity_insurance_and_vlocity_health_pre_install_and_pre_upgrade_tasks.htm&language=en_US&type=5#insurance_enable_work_orders)**  
    To prepare your org for Insurance, enable Work Orders.
-   **[Set Deliverability to All Email](https://help.salesforce.com/s/articleView?id=ind.insurance_vlocity_insurance_and_vlocity_health_pre_install_and_pre_upgrade_tasks.htm&language=en_US&type=5#insurance_set_deliverability_to_all_email)**  
    To prepare your org for Insurance, set email deliverability to **All email**.
-   **[Verify Order Save Behavior](https://help.salesforce.com/s/articleView?id=ind.insurance_vlocity_insurance_and_vlocity_health_pre_install_and_pre_upgrade_tasks.htm&language=en_US&type=5#insurance_verify_order_save_behavior)**  
    Verify that the New Order Save Behavior is disabled. Otherwise, your Insurance package won’t install.
-   **[Assign Permissions for Orchestration Items](https://help.salesforce.com/s/articleView?id=ind.insurance_vlocity_insurance_and_vlocity_health_pre_install_and_pre_upgrade_tasks.htm&language=en_US&type=5#insurance_assign_permissions_for_orchestration_items)**  
    As of Summer '22, users who edit Task records and who aren't Salesforce admins need Read and Create permissions for the Orchestration Items object. These required permissions help keep your Salesforce data more secure. Assign permissions to user profiles, or create a permission set with these permissions and assign it to users.
-   **[Omni Interaction Configuration Settings](https://help.salesforce.com/s/articleView?id=ind.insurance_vlocity_insurance_and_vlocity_health_pre_install_and_pre_upgrade_tasks.htm&language=en_US&type=5#insurance_omni_interaction_configuration_settings)**  
    The Insurance package installation checks information about your OmniStudio components and defines feature settings based on what it finds. This check happens automatically, and if you have an OmniStudio license, a script that's called by the installation defines Omni Interaction Configuration feature settings.

[](https://help.salesforce.com/s?language=en_US)

## Confirm System Requirements

Verify that your web browser and Salesforce version meet these minimum requirements.

[](https://help.salesforce.com/s?language=en_US)

1.  Ensure that you are using a supported browser for Salesforce Lightning Experience. See [Supported Browsers and Devices for Lightning Experience](https://help.salesforce.com/s/articleView?id=xcloud.getstart_browsers_sfx.htm&language=en_US&type=5) for details.
    
    For best results, don't use Microsoft Internet Explorer.
    
2.  Your system has a minimum of 4GB of RAM.
3.  Your browser has JavaScript enabled.
4.  Your Salesforce Edition is **Enterprise**, **Unlimited**, or **Performance**.
5.  You have Salesforce licenses for all users who need access to Insurance.
6.  You have a valid subscription to Salesforce Customer Community, Salesforce Customer Community Plus, or Salesforce Partner Community.
7.  You have a minimum of 10 MB Platform Cache Partition configured in Salesforce. Insurance uses the Platform Cache partition to store the RatingsCache.
8.  Allocate at least 2 MB for Insurance metadata in the org metadata cache for all production and testing orgs.

[](https://help.salesforce.com/s?language=en_US)

## Disable Advanced Currency Management

Advanced currency management allows you to manage dated exchange rates within opportunities using Salesforce. To prepare for your installation or upgrade, disable it.

To learn more, see [Enable or Disable Advanced Currency Management](https://help.salesforce.com/s/articleView?id=sales.administration_enable_advanced_currency_management.htm&language=en_US&type=5).

Note In Setup, if you can't find **Manage Currencies**, advanced currency management is already disabled.

[](https://help.salesforce.com/s?language=en_US)

## Empty the Org Recycle Bin

As an admin, you have access to the Salesforce org's Recycle Bin and can delete records from it.

Too learn more, see [Manage the Recycle Bin in Lightning Experience](https://help.salesforce.com/s/articleView?id=xcloud.recycle_bin_manage.htm&language=en_US&type=5).

[](https://help.salesforce.com/s?language=en_US)

## Enable Contacts to Multiple Accounts

To prepare your org for Insurance, allow users to link contacts to multiple accounts.

1.  From Setup, enter Account Settings in the Quick Find box, and then select **Account Settings**.
2.  Click **Edit**.
3.  In the **Contacts to Multiple Accounts Settings** area, select **Allow users to relate a contact to multiple accounts**.
4.  Click **Save**.
    
    Note Changing this setting may take a while. You will receive an email from Salesforce once it has completed. See more about this setting [here](https://help.salesforce.com/s/articleView?id=sales.shared_contacts_overview.htm&language=en_US&type=5).
    

[](https://help.salesforce.com/s?language=en_US)

## Enable Content Deliveries

To prepare your org for Insurance, enable content deliveries and public links.

1.  From Setup, enter Content Deliveries in the Quick Find box, and then select **Content Deliveries and Public Links**.
2.  Select **Content Deliveries feature can be enabled for users**, then select **Public Links can be enabled for users (Requires Content Deliveries)**.
3.  Click **Save**.

[](https://help.salesforce.com/s?language=en_US)

## Enable Data Protection and Privacy

To prepare your org for Insurance, enable data protection and privacy.

1.  From Setup, enter Data Protection in the Quick Find box, and then select **Data Protection and Privacy**.
2.  Click **Edit**.
3.  Select **Make data protection details available in records**.
4.  Click **Save**.

[](https://help.salesforce.com/s?language=en_US)

## Enable Enhanced Email

To prepare your org for Insurance, enable Enhanced Email.

1.  From Setup, enter Enhanced Email in the Quick Find box, and then select **Enhanced Email**.
2.  Click **Enable**.

[](https://help.salesforce.com/s?language=en_US)

## Enable Forecasts

To prepare your org for Insurance, enable Forecasts.

1.  From Setup, enter Forecasts Settings in the Quick Find box, and then select **Forecasts Settings**.
2.  If Forecasts isn’t enabled, enable it.

[](https://help.salesforce.com/s?language=en_US)

## Enable Salesforce Files Settings

Enable the Salesforce Files Settings to avoid errors while installing the managed package.

1.  From Setup, enter Salesforce Files in the Quick Find box, and then select **General Settings**.
2.  Click **Edit**.
3.  Select these Salesforce Files Settings:
    
    -   **Libraries in Salesforce Files**
    -   **Skip triggers execution when deploying asset files**
    -   **Skip triggers execution and validation rules on asset files**
    
4.  Click **Save**.

[](https://help.salesforce.com/s?language=en_US)

## Enable Multiple Contacts

To prepare your org for Insurance, allow users to relate multiple contacts to tasks and events.

1.  From Setup, enter Activity in the Quick Find box, and then select **Activity Settings**.
2.  Select **Allow Users to Relate Multiple Contacts to Tasks and Events**.
3.  Click **Submit**.

[](https://help.salesforce.com/s?language=en_US)

## Enable Orders

To prepare your org for Insurance, enable Orders.

1.  From Setup, enter Order Settings in the Quick Find box, and then select **Order Settings**.
2.  Select **Enable Orders**.
3.  Click **Save**.

[](https://help.salesforce.com/s?language=en_US)

## Enable Product Scheduling

To prepare your org for Insurance, enable Product Scheduling.

1.  From Setup enter Product Schedule in the Quick Find box, and then select **Product Schedules Settings.**
2.  On the Schedule Setup page, in the Schedule Types area, select **Enable quantity scheduling**, and then **Enable for all products**.
3.  Select **Enable revenue scheduling**, then **Enable for all products**.
4.  Click **Save**.

[](https://help.salesforce.com/s?language=en_US)

## Enable Quotes

To prepare your org for Insurance, enable Quotes.

1.  From Setup, enter Quote in the Quick Find box, and then select **Quote Settings**.
2.  Click **Enable**.

[](https://help.salesforce.com/s?language=en_US)

## Enable Salesforce CRM Content

To prepare your org for Insurance, enable Salesforce CRM Content.

1.  From Setup enter Salesforce CRM in the Quick Find box, and then select **Salesforce CRM Content**.
2.  Select **Enable Salesforce CRM Content**.
3.  Click **Save**.

[](https://help.salesforce.com/s?language=en_US)

## Enable Work Orders

To prepare your org for Insurance, enable Work Orders.

1.  From Setup, in the Quick Find box, enter Field Service Settings, and then select **Field Service Settings**.
2.  Enable **Field Service**, and then click **Save**.
    
    Work Orders are enabled by default. If Work Orders are disabled in your org, enable them before you try to install the Insurance managed package.
    

[](https://help.salesforce.com/s?language=en_US)

## Set Deliverability to All Email

To prepare your org for Insurance, set email deliverability to **All email**.

1.  From Setup, enter Deliverability in the Quick Find box, and then select **Deliverability**.
2.  In the **Access to Send Email** section, select **All email** from the dropdown menu.
3.  Click **Save**.

[](https://help.salesforce.com/s?language=en_US)

## Verify Order Save Behavior

Verify that the New Order Save Behavior is disabled. Otherwise, your Insurance package won’t install.

For more information about the update, see [Order Save Behavior Update](https://help.salesforce.com/s/articleView?id=000354241&language=en_US&type=1).

1.  From **Setup**, in the Quick Find box, enter Release Updates, and then select **Release Updates**.
2.  On the **Needs Action** page, find the **Enable New Order Save Behavior** release update. Click **Get Started**.
3.  If the step-by-step guide shows that the update is enabled for testing, click **Disable Test Run**.
    
    If you see an **Enable Test Run** button, the new behavior is disabled and you can proceed with package installation.
    

[](https://help.salesforce.com/s?language=en_US)

## Assign Permissions for Orchestration Items

As of Summer '22, users who edit Task records and who aren't Salesforce admins need Read and Create permissions for the Orchestration Items object. These required permissions help keep your Salesforce data more secure. Assign permissions to user profiles, or create a permission set with these permissions and assign it to users.

-   In user profiles, in the **Custom Object Permissions** section, find **Orchestration Items** and select **Read** and **Create**. If these permissions aren't available to select, create and assign a permission set to users instead.
-   In permission set Object Settings, find **Orchestration Items** and select **Read** and **Create**. Assign the permission set to a single user from the user detail page, or to one or more users from the permission set page.

[](https://help.salesforce.com/s?language=en_US)

## Omni Interaction Configuration Settings

The Insurance package installation checks information about your OmniStudio components and defines feature settings based on what it finds. This check happens automatically, and if you have an OmniStudio license, a script that's called by the installation defines Omni Interaction Configuration feature settings.

-   **InstalledIndustryPackage** shows the namespace of your industry package, if you have one installed.
-   **TheFirstInstalledOmniPackage** shows the namespace of the first package with OmniStudio that was installed.

These settings affect which OmniStudio components are used in your org, either custom objects from the package or base platform objects in the core Salesforce platform. The OmniStudio user’s experience remains the same no matter which components are used. But behind the scenes, your org consistently points to only one set of objects—the ones that were installed first.

Did this article solve your issue?

Let us know so we can improve!

YesNo