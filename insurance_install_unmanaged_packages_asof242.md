---
title: "Install Unmanaged Packages for Insurance"
source: "https://help.salesforce.com/s/articleView?id=ind.insurance_install_unmanaged_packages_asof242.htm&language=en_US&type=5"
scraped: "2026-04-14"
filter: "ind.insurance_"
---# Install Unmanaged Packages for Insurance

Install Unmanaged Packages for Insurance[](https://help.salesforce.com/s?language=en_US)

You are here:

1.  [Salesforce Help](/s/?language=en_US)
2.  [Docs](/s/products?language=en_US)
3.  [Digital Insurance](https://help.salesforce.com/s/articleView?id=ind.insurance_admin_standard.htm&language=en_US&type=5)

# Install Unmanaged Packages for Insurance

The Insurance unmanaged package contains custom record pages. The Insurance FSC unmanaged package contains Digital Experience Site templates.

Note

Before you can install the Insurance FSC Unmanaged Package, you need to enable Digital Experience Sites. To learn how, see [Enable Digital Experiences](https://help.salesforce.com/s/articleView?id=experience.networks_enable.htm&language=en_US&type=5).

1.  Ensure the Party.EnablePartyModel custom setting exists in your org and is enabled:
    1.  From Setup, in the **Quick Find** box, enter Custom Settings.
    2.  Click **Custom Settings**.
    3.  Click **Trigger Setup**.
    4.  Next to **Trigger Setup** click **Manage**.
    5.  Click **New**. The Trigger Setup Edit page opens.
    6.  In the **Name** field, enter Party.EnablePartyModel..
    7.  Select the **Trigger On** checkbox to enable the trigger.
2.  Go to the [Insurance Release Summary](https://help.salesforce.com/s/articleView?id=ind.insurance_release_summary.htm&language=en_US&type=5#insurance_release_summary "Get release summaries for Insurance minor releases delivered each Winter, Spring, and Summer.") and click the link for the most recent unmanaged package.
3.  On the Install window, select **Rename conflicting components in package**.
4.  Select which users to install the unmanaged package for, then click **Install**.

Did this article solve your issue?

Let us know so we can improve!

YesNo