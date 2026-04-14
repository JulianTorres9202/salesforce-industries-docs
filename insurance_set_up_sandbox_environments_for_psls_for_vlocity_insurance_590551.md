---
title: "Set Up Sandbox Environments for Permission Set Licenses for Insurance"
source: "https://help.salesforce.com/s/articleView?id=ind.insurance_set_up_sandbox_environments_for_psls_for_vlocity_insurance_590551.htm&language=en_US&type=5"
scraped: "2026-04-14"
filter: "ind.insurance_"
---# Set Up Sandbox Environments for Permission Set Licenses for Insurance

Set Up Sandbox Environments for Permission Set Licenses for Insurance[](https://help.salesforce.com/s?language=en_US)

You are here:

1.  [Salesforce Help](/s/?language=en_US)
2.  [Docs](/s/products?language=en_US)
3.  [Digital Insurance](https://help.salesforce.com/s/articleView?id=ind.insurance_admin_standard.htm&language=en_US&type=5)

# Set Up Sandbox Environments for Permission Set Licenses for Insurance

To use sandbox environments to test permission set licenses, configure your environment by creating a custom setting and running a command.

[](https://help.salesforce.com/s?language=en_US)Warning Run these steps only if you want to test permission set licenses in a sandbox environment.

Create a PSLOnlyLicenseCheckInSandboxEnabled custom setting with the value as true.

1.  From **Setup**, in the **Quick Find** box, enter Custom Settings.
    
2.  Click **Custom Settings**.
    
3.  Click **Manage** next to **General Settings**.
    
4.  Click **New**.
    
5.  For **Name**, enter PSLOnlyLicenseCheckInSandboxEnabled.
    
6.  For **Value**, enter true.
    
7.  Click **Save**.
    

Did this article solve your issue?

Let us know so we can improve!

YesNo