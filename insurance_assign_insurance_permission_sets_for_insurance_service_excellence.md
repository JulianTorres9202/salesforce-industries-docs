---
title: "Assign Insurance Permission Sets for Insurance Service Excellence Components"
source: "https://help.salesforce.com/s/articleView?id=ind.insurance_assign_insurance_permission_sets_for_insurance_service_excellence.htm&language=en_US&type=5"
scraped: "2026-04-13"
filter: "ind.insurance_"
---# Assign Insurance Permission Sets for Insurance Service Excellence Components

Assign Insurance Permission Sets for Insurance Service Excellence Components[](https://help.salesforce.com/s?language=en_US)

You are here:

1.  [Salesforce Help](/s/?language=en_US)
2.  [Docs](/s/products?language=en_US)
3.  [Digital Insurance](https://help.salesforce.com/s/articleView?id=ind.insurance_admin_standard.htm&language=en_US&type=5)

# Assign Insurance Permission Sets for Insurance Service Excellence Components

Assign permission sets to admins and users based on their required level of access to the Service Excellence for Insurance features.

| Component | FSC Insurance Permission Set | Industry Service Excellence Permission Set | OmniStudio Runtime Permission Set |
| --- | --- | --- | --- |
| Insurance Agent Console | Yes | No | No |
| Action Launcher | No | Yes | No |
| Alerts | No | Yes | No |
| Profile Card | Yes | Yes | Yes |
| Sentiment Indicator | Yes | Yes | Yes |
| Policy 360 | Yes | Yes | Yes |
| Timeline | No | Yes | No |
| Identity Verification | No | Yes | No |

Note System Admin users can access Insurance Agent Console without assigning any permission sets. For all other users, ensure that appropriate permission sets are assigned.

1.  From Setup, in the Quick Find box, enter Users, and then select **Users**.
2.  Select a user and in the Permission Set Assignments section, click **Edit Assignments**.
3.  Select the required permission sets from the Available Permission Sets list, and move them to the Enabled Permission Sets list.
4.  Save your changes.

Did this article solve your issue?

Let us know so we can improve!

YesNo