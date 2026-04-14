---
title: "Configure Create Contacts Invocable Action"
source: "https://help.salesforce.com/s/articleView?id=ind.insurance_configure_create_contacts_invocable_action.htm&language=en_US&type=5"
scraped: "2026-04-14"
filter: "ind.insurance_"
---# Configure Create Contacts Invocable Action

Configure Create Contacts Invocable Action[](https://help.salesforce.com/s?language=en_US)

You are here:

1.  [Salesforce Help](/s/?language=en_US)
2.  [Docs](/s/products?language=en_US)
3.  [Digital Insurance](https://help.salesforce.com/s/articleView?id=ind.insurance_admin_standard.htm&language=en_US&type=5)

# Configure Create Contacts Invocable Action

Create matching rules and duplicate rules for the Contact object to avoid fuzzy matching and create contacts for the census members during bulk enrollment and new hire enrollment.

1.  From Setup, in the Quick Find box, enter Duplicate Rules, and then select **Duplicate Rules**.
2.  Click **Standard Contact Duplicate Rule**, and then click **Activate**.
3.  Click **Deactivate**.
4.  From Setup, in the Quick Find box, enter Matching Rules , and then select **Matching Rules**.
5.  Click **New Rule**.
6.  For **Object**, select Contact, and then click **Next**.
7.  Enter a **Rule name**.
8.  For Matching Method, select Exact Match.
9.  Save the changes.
10.  In the Quick Find box, enter Duplicate Rules, and then select **Duplicate Rules**.
11.  Click **New Rule**, and then select Contact.
12.  Enter a **Rule Name**, and then select the matching rule that you created for the **Matching Rule** field.
13.  Save the changes, and then click **Activate**.
     
     SEE ALSO
     
     [Matching Methods Used in Matching Rules](https://help.salesforce.com/s/articleView?id=sales.matching_rules_matching_methods.htm&language=en_US&type=5)
     

Did this article solve your issue?

Let us know so we can improve!

YesNo