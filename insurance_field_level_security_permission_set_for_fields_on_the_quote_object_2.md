---
title: "Field-Level Security Permission Set for Fields on the Quote Object"
source: "https://help.salesforce.com/s/articleView?id=ind.insurance_field_level_security_permission_set_for_fields_on_the_quote_object_2.htm&language=en_US&type=5"
scraped: "2026-04-14"
filter: "ind.insurance_"
---# Field-Level Security Permission Set for Fields on the Quote Object

Field-Level Security Permission Set for Fields on the Quote Object[](https://help.salesforce.com/s?language=en_US)

You are here:

1.  [Salesforce Help](/s/?language=en_US)
2.  [Docs](/s/products?language=en_US)
3.  [Digital Insurance](https://help.salesforce.com/s/articleView?id=ind.insurance_admin_standard.htm&language=en_US&type=5)

# Field-Level Security Permission Set for Fields on the Quote Object

Provide your users with access to specific fields on the Quote object by creating a permission set.

Add the Quote object and certain fields to a permission set, then assign that permission set to users. Use these steps to add access to all of the fields listed in the table below to a permission set.

1.  From Setup, in the Quick Find box, enter Permission Sets, and then select **Permission Sets**.
2.  Click **New**.
3.  Enter a **Name** and **API Name** for your permission set.
4.  Click **Save**.
5.  Ins the **Apps** section, click **Object Settings**.
6.  Click the **Quotes** object.
7.  Click **Edit**.
8.  In **Object Permissions**, enable **Read**, **Create**, **Edit** , and **Delete**.
9.  In **Field Permissions**, enable **Read Access** and **Edit Access** for:
    
    -   **Additional To**
    -   **Contact Name**
    -   **Discount**
    -   **Email**
    -   **Phone**
    
10.  Click **Save**.

[](https://help.salesforce.com/s?language=en_US)

You can now assign this permission set to your users.

[](https://help.salesforce.com/s?language=en_US)

Decide which users need access to these objects and fields, then assign the permission set to a [single user](https://help.salesforce.com/s/articleView?id=platform.perm_sets_assigning.htm&language=en_US&type=5), or [multiple users](https://help.salesforce.com/s/articleView?id=platform.perm_sets_mass_assign.htm&language=en_US&type=5).

Did this article solve your issue?

Let us know so we can improve!

YesNo