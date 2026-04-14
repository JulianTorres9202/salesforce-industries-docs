---
title: "Package Installation Flows"
source: "https://help.salesforce.com/s/articleView?id=ind.insurance_package_installation_flows.htm&language=en_US&type=5"
scraped: "2026-04-14"
filter: "ind.insurance_"
---# Package Installation Flows

Package Installation Flows[](https://help.salesforce.com/s?language=en_US)

You are here:

1.  [Salesforce Help](/s/?language=en_US)
2.  [Docs](/s/products?language=en_US)
3.  [Digital Insurance](https://help.salesforce.com/s/articleView?id=ind.insurance_admin_standard.htm&language=en_US&type=5)

# Package Installation Flows

Insurance uses managed and unmanaged packages that you install in a certain order. The number of packages you install depends on which features you plan to use.

[](https://help.salesforce.com/s?language=en_US)

## Basic Package Installation Flow

You install at least three packages to use Insurance.

[](https://help.salesforce.com/s?language=en_US)Important Before you install a managed package, make sure you're ready to proceed. Salesforce doesn't support uninstalling managed packages.

Install the packages in this order:

[](https://help.salesforce.com/s?language=en_US)

1.  The Insurance and Vlocity Health Managed Package.
    
2.  The Insurance and Vlocity Health Unmanaged Package.
    
3.  The Vlocity Installation Assistant.
    

[](https://help.salesforce.com/s?language=en_US)

## Package Installation Flow with the Insurance Industries Extension Packages

To use all of the great features in our Insurance Industries Extension packages, you must have the required licenses.

If you're using Insurance, you must have a **Salesforce FSC** license, a **Policy Administration** license, and a **Claims Management** license.

Install the packages in this order:

[](https://help.salesforce.com/s?language=en_US)

1.  The Insurance and Vlocity Health Managed Package.
    
    This package contains data model extensions, Apex Insurance services, templates, cards, Lightning components, product modeling components, and rating engine components.
    
2.  The Insurance Industries Extension Managed Package.
    
    This package contains Insurance components for use with Salesforce Financial Services Cloud. Install this package in addition to the standard managed package only if you use Salesforce Financial Services Cloud.
    
    [](https://help.salesforce.com/s?language=en_US)If you have the add-on licenses for Policy Administration and Claims Management, you must enable these features before you install the Insurance Industries Extension Managed Package. From Setup, in the Quick Find box, enter **Insurance**, and then select **Insurance Settings**. Enable **Policy Administration** and **Claims Management**.
    
    If you use group benefits, see [Give Users Access to Group Benefits in the Salesforce Data Model](https://help.salesforce.com/s/articleView?id=ind.insurance_give_users_access_to_group_benefits.htm&language=en_US&type=5 "To use group benefits in the Salesforce data model, check your add-on licenses and permission set license assignments.").
    
3.  The Vlocity Insurance and Vlocity Health Unmanaged Package.
    
    This package contains the Lightning record pages for the product modeling and rating UI, as well as UIs for quotes, policies, and other objects. A new version of the unmanaged package is available for select releases.
    
4.  The Insurance FSC Unmanaged Package.
    
    This unmanaged package contains Digital Experience Site templates. To learn about using these templates, see [Set Up Your Digital Experience Site](https://help.salesforce.com/s/articleView?id=ind.insurance_set_up_your_digital_experience_site_649987.htm&language=en_US&type=5 "Create an Experience site for your users using the templates provided in the Insurance FSC unmanaged package.").
    
    Important
    
    If you decide to install the Insurance FSC Unmanaged Package, enable Digital Experience Sites first. See [Enable Digital Experiences](https://help.salesforce.com/s/articleView?id=experience.networks_enable.htm&language=en_US&type=5).
    
5.  The Vlocity Installation Assistant.
    
    This unmanaged package contains the Vlocity Installation Assistant app, which walks you through installation and upgrade tasks. A new version of the Installation Assistant is available for select releases.
    

-   **[Install Managed Packages for Insurance](https://help.salesforce.com/s/articleView?id=ind.insurance_install_managed_packages_asof242.htm&language=en_US&type=5)**  
    Managed packages are the first packages you install in your Insurance install or upgrade process.
-   **[Install Unmanaged Packages for Insurance](https://help.salesforce.com/s/articleView?id=ind.insurance_install_unmanaged_packages_asof242.htm&language=en_US&type=5)**  
    The Insurance unmanaged package contains custom record pages. The Insurance FSC unmanaged package contains Digital Experience Site templates.
-   **[Install the Vlocity Installation Assistant](https://help.salesforce.com/s/articleView?id=ind.insurance_install_the_installation_assistant_asof242.htm&language=en_US&type=5#insurance_install_the_installation_assistant_asof242)**  
    To make it easier to configure Insurance after installing or upgrading, install the unmanaged package that contains the Installation Assistant.

Did this article solve your issue?

Let us know so we can improve!

YesNo