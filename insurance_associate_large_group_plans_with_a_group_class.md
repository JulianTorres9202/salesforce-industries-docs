---
title: "Add Group Classes and Associate them with Large Group Plans"
source: "https://help.salesforce.com/s/articleView?id=ind.insurance_associate_large_group_plans_with_a_group_class.htm&language=en_US&type=5"
scraped: "2026-04-13"
filter: "ind.insurance_"
---# Add Group Classes and Associate them with Large Group Plans

Add Group Classes and Associate them with Large Group Plans[](https://help.salesforce.com/s?language=en_US)

You are here:

1.  [Salesforce Help](/s/?language=en_US)
2.  [Docs](/s/products?language=en_US)
3.  [Digital Insurance](https://help.salesforce.com/s/articleView?id=ind.insurance_admin_standard.htm&language=en_US&type=5)

# Add Group Classes and Associate them with Large Group Plans

Group classes describe a group of plan subscribers who all receive similar or the same benefits. You can add them to plans on large group quotes. Users can associate plans in a quote with a Group Class from within the large group quoting UI.

On the Large Group Quote Lightning web component, users can select the eligible group classes for each quote line item. Only the primary members (and their families) whose group class falls in the selected eligible group classes are rated.

The Group Class object identifies a group of members that all receive similar benefits when different classes of members receive different benefits. Example classes include Executives, Union, and Office workers.

To view details about the Group Class object, review the Fields & Relationships shown for Group Class in Object Manager.

Tip Edit the Group Class search layout and move the Account field below the Name field. This makes it easier to differentiate the associated group classes for an account when you add new members. See ​[Edit Your Search Layout](https://help.salesforce.com/s/articleView?id=ai.search_edit_layouts.htm&language=en_US&type=5)​.​

1.  Select a plan on the Large Group Quote LWC.
2.  Click **Assign**.
3.  A dialog box appears. Select a group class and then click **Save**. The group class appears as a group associated with the plan.

Did this article solve your issue?

Let us know so we can improve!

YesNo