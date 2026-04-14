---
title: "Verify and Update Required Permissions for Quoting"
source: "https://help.salesforce.com/s/articleView?id=ind.insurance_verify_required_quoting_permissions.htm&language=en_US&type=5"
scraped: "2026-04-14"
filter: "ind.insurance_"
---# Verify and Update Required Permissions for Quoting

Verify and Update Required Permissions for Quoting[](https://help.salesforce.com/s?language=en_US)

You are here:

1.  [Salesforce Help](/s/?language=en_US)
2.  [Docs](/s/products?language=en_US)
3.  [Digital Insurance](https://help.salesforce.com/s/articleView?id=ind.insurance_admin_standard.htm&language=en_US&type=5)

# Verify and Update Required Permissions for Quoting

To view and create quotes, users must have access to certain information.

Verify that permission sets provide users, including community users, access to these fields:

| Object | Fields | Permission Level Needed |
| --- | --- | --- |
| Quote | Group Census ID | Read, Edit |
| Source System | Read, Edit |
| Source System Identifier | Read, Edit |
| Total Fee for Term | Read, Edit |
| Total Tax for Term | Read, Edit |
| Quote Line Item | Image ID | Read |
| Source System Identifier | Read, Edit |

If your permission sets don't provide this level of access to users who view and create quotes, update them.

1.  From Setup, in the Quick Find box, enter Permission Sets, and then select **Permission Sets**.
2.  Open the permission set.
3.  In the **Apps** section, click **Object Settings**.
4.  Click the object.
5.  Click **Edit**.
6.  In **Field Permissions**, enable the appropriate permissions, for example, **Read Access** and **Edit Access**.
7.  Repeat these steps for each of the custom fields.

Did this article solve your issue?

Let us know so we can improve!

YesNo