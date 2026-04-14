---
title: "Migrate Your Licenses for Insurance"
source: "https://help.salesforce.com/s/articleView?id=ind.insurance_migrate_your_licenses_for_vlocity_insurance_590587.htm&language=en_US&type=5"
scraped: "2026-04-14"
filter: "ind.insurance_"
---# Migrate Your Licenses for Insurance

Migrate Your Licenses for Insurance[](https://help.salesforce.com/s?language=en_US)

You are here:

1.  [Salesforce Help](/s/?language=en_US)
2.  [Docs](/s/products?language=en_US)
3.  [Digital Insurance](https://help.salesforce.com/s/articleView?id=ind.insurance_admin_standard.htm&language=en_US&type=5)

# Migrate Your Licenses for Insurance

Migrate your users from Managed Package Licenses (MPL) to Permission Set Licenses.

1.  Identify the permission set licenses that you want to assign to your users.
2.  Assign permission set licenses for the SKU to the user:
    1.  From Setup, enter Users in the Quick Find box, then select **Users**.
    2.  Select a user.
    3.  n the Permission Set License Assignments section, click **Edit Assignments**.
    4.  Select the permission set licenses for the SKU allotted to the user. For example, if you want to assign the Insurance Claims Management SKU to a user, then enable the Claims Management Package and Claims FNOL Community Package Permission set licenses.
    5.  Click **Save**.
3.  Assign permission sets for the SKU to the user:
    1.  From Setup, enter Users in the Quick Find box, then select **Users**.
    2.  Select a user.
    3.  In the Permission Set Assignments related section, click **Edit Assignments**.
    4.  Select the permission sets specific to their permission set licenses to assign. For example, if you want to assign the Insurance Claims Management SKU to a user, then enable the Insurance Claim Management package and Insurance Claims FNOL Community Package permission sets.
    5.  Click **Save**.
4.  Unassign MPLs from the user:
    1.  From Setup, enter Installed Packages in the Quick Find box and then select **Installed Packages**.
    2.  Click **Manage Licenses** next to the Vlocity Insurance package.
    3.  Click **Remove** next to the user.
5.  Verify that the user can perform all the necessary actions with permission set licenses.
6.  After your users verify their access in the sandbox, run steps 1 to 5 in the production environment.

Did this article solve your issue?

Let us know so we can improve!

YesNo