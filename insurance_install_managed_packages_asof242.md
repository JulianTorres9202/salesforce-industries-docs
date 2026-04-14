---
title: "Install Managed Packages for Insurance"
source: "https://help.salesforce.com/s/articleView?id=ind.insurance_install_managed_packages_asof242.htm&language=en_US&type=5"
scraped: "2026-04-14"
filter: "ind.insurance_"
---# Install Managed Packages for Insurance

Install Managed Packages for Insurance[](https://help.salesforce.com/s?language=en_US)

You are here:

1.  [Salesforce Help](/s/?language=en_US)
2.  [Docs](/s/products?language=en_US)
3.  [Digital Insurance](https://help.salesforce.com/s/articleView?id=ind.insurance_admin_standard.htm&language=en_US&type=5)

# Install Managed Packages for Insurance

Managed packages are the first packages you install in your Insurance install or upgrade process.

[](https://help.salesforce.com/s?language=en_US)Important Before you install a managed package, make sure you're ready to proceed. Salesforce doesn't support uninstalling managed packages.

1.  Go to the [Insurance Release Summary](https://help.salesforce.com/s/articleView?id=ind.insurance_release_summary.htm&language=en_US&type=5#insurance_release_summary "Get release summaries for Insurance minor releases delivered each Winter, Spring, and Summer.") to find the managed package you want to install.
2.  Click or copy and paste the link to the current package.
3.  Select which users to install for, then click **Install**.
4.  On the **Approve Third-Party Access** window, confirm that all options are selected, select **Yes, grant access to these third-party websites**, then click **Continue**.
    
    The example.com and vlocity.com websites are safe and trusted sites. You must grant access to these sites for the managed package to install.
    
    [](https://help.salesforce.com/s?language=en_US)Note
    
    If this window doesn't appear, these options are already selected.
    
    If you get errors about missing entity objects, make sure you've assigned the permission set licenses required for those objects. After assigning the licenses in a production org, refresh your sandbox org. For information about licensing, see [Package Installation Flows](https://help.salesforce.com/s/articleView?id=ind.insurance_package_installation_flows.htm&language=en_US&type=5 "Insurance uses managed and unmanaged packages that you install in a certain order. The number of packages you install depends on which features you plan to use.").
    
5.  Wait. The managed package can take longer to install than the standard Salesforce timeout.
6.  Verify that the package installed:
    
    1.  From Setup, enter Installed Packages in the Quick Find box, then select **Installed Packages**.
    2.  Confirm that the Vlocity package is present.
        
        The Installed Packages UI
        
    
    [](https://help.salesforce.com/s?language=en_US)Important Don't start installing the other packages until the managed package installation is complete.
    
    [](https://help.salesforce.com/s?language=en_US)Note Licensed seats are required only for Production orgs, so you won’t see a **Manage Licenses** link for Sandbox orgs.
    

Did this article solve your issue?

Let us know so we can improve!

YesNo