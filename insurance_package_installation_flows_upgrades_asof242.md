---
title: "Package Installation Flows for Insurance Upgrades"
source: "https://help.salesforce.com/s/articleView?id=ind.insurance_package_installation_flows_upgrades_asof242.htm&language=en_US&type=5"
scraped: "2026-04-14"
filter: "ind.insurance_"
---# Package Installation Flows for Insurance Upgrades

Package Installation Flows for Insurance Upgrades[](https://help.salesforce.com/s?language=en_US)

You are here:

1.  [Salesforce Help](/s/?language=en_US)
2.  [Docs](/s/products?language=en_US)
3.  [Digital Insurance](https://help.salesforce.com/s/articleView?id=ind.insurance_admin_standard.htm&language=en_US&type=5)

# Package Installation Flows for Insurance Upgrades

Your release includes new managed packages. If you plan to use the Insurance Industries Extension package, you have two managed packages to install. Otherwise, you have just one package to install.

[](https://help.salesforce.com/s?language=en_US)Important Before you install a managed package, make sure you're ready to proceed. Salesforce doesn't support uninstalling managed packages.

[](https://help.salesforce.com/s?language=en_US)

## Package Installation Flow with the Insurance Industries Extension Packages

To use all of the great features in our Insurance Industries Extension package, you must have the required licenses.

If you're using Insurance, you must have a **Salesforce FSC** license, a **Policy Administration** license, and a **Claims Management** license.

Complete tasks in this order:

[](https://help.salesforce.com/s?language=en_US)

1.  Install the Insurance and Vlocity Health Managed Package.
    
    This package contains data model extensions, Apex Insurance services, templates, cards, Lightning components, product modeling components, and rating engine components.
    
2.  Install the Insurance Industries Extension Managed Package.
    
    This package contains Insurance components for use with Salesforce Financial Services Cloud. Install this package in addition to the standard managed package only if you use Salesforce Financial Services Cloud.
    
    [](https://help.salesforce.com/s?language=en_US)If you have the add-on licenses for Policy Administration and Claims Management, you must enable these features before you install the Insurance Industries Extension Managed Package. From Setup, in the Quick Find box, enter **Insurance**, and then select **Insurance Settings**. Enable **Policy Administration** and **Claims Management**.
    
    If you use group benefits, see [Give Users Access to Group Benefits in the Salesforce Data Model](https://help.salesforce.com/s/articleView?id=ind.insurance_give_users_access_to_group_benefits.htm&language=en_US&type=5 "To use group benefits in the Salesforce data model, check your add-on licenses and permission set license assignments.").
    

Did this article solve your issue?

Let us know so we can improve!

YesNo