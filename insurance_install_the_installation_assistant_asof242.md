---
title: "Install the Vlocity Installation Assistant"
source: "https://help.salesforce.com/s/articleView?id=ind.insurance_install_the_installation_assistant_asof242.htm&language=en_US&type=5"
scraped: "2026-04-14"
filter: "ind.insurance_"
---# Install the Vlocity Installation Assistant

Install the Vlocity Installation Assistant

You are here:

1.  [Salesforce Help](/s/?language=en_US)
2.  [Docs](/s/products?language=en_US)
3.  [Digital Insurance](https://help.salesforce.com/s/articleView?id=ind.insurance_admin_standard.htm&language=en_US&type=5)

[](https://help.salesforce.com/s?language=en_US)

# Install the Vlocity Installation Assistant

To make it easier to configure Insurance after installing or upgrading, install the unmanaged package that contains the Installation Assistant.

1.  Go to the [Insurance Release Summary](https://help.salesforce.com/s/articleView?id=ind.insurance_release_summary.htm&language=en_US&type=5#insurance_release_summary "Get release summaries for Insurance minor releases delivered each Winter, Spring, and Summer.") and click the link for the Installation Assistant Package that matches the version of Insurance you want to configure.
2.  On the Install window, select **Rename conflicting components in package**.
3.  Select which users to install Installation Assistant for, then click **Install**.
4.  Verify that the Installation Assistant is installed in your org:
    1.  From Setup, in the **Quick Find Box**, enter Installed Packages, and then select **Installed Packages**.
    2.  Confirm that the Vlocity Installation Assistant package is present.

-   **[Uninstall the Vlocity Installation Assistant](https://help.salesforce.com/s/articleView?id=ind.insurance_install_the_installation_assistant_asof242.htm&language=en_US&type=5#insurance_uninstall_the_vlocity_installation_assistant)**  
    After you complete all the steps for an installation or upgrade, uninstall the Vlocity Installation Assistant. Or, if you're upgrading and have a version of the Vlocity Installation Assistant from an earlier release, uninstall it before you install the new Vlocity Installation Assistant.

[](https://help.salesforce.com/s?language=en_US)

## Uninstall the Vlocity Installation Assistant

After you complete all the steps for an installation or upgrade, uninstall the Vlocity Installation Assistant. Or, if you're upgrading and have a version of the Vlocity Installation Assistant from an earlier release, uninstall it before you install the new Vlocity Installation Assistant.

[](https://help.salesforce.com/s?language=en_US)Note

If you're upgrading to a minor release that's built on the same major release your org is already on, you don't have to uninstall the Installation Assistant package.

1.  From Setup, in the **Quick Find Box**, enter Installed Packages, and then select **Installed Packages**.
2.  Find the Vlocity Installation Assistant package.
    
    It has a name similar to **Vlocity\_Installation\_Assistant\_INS**.
    
3.  On the Vlocity Installation Assistant package line, click **Uninstall**.
4.  Scroll to the bottom of the page and choose **Save a copy of this package's data for 48 hours after uninstall**.
5.  Select **Yes, I want to uninstall this package and permanently delete all associated components**.
6.  Click **Uninstall**.

Did this article solve your issue?

Let us know so we can improve!

YesNo