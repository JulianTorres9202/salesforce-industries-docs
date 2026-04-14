---
title: "Required Permissions for the Partner Community User Profile"
source: "https://help.salesforce.com/s/articleView?id=ind.insurance_required_permissions_for_the_partner_community_user_profile.htm&language=en_US&type=5"
scraped: "2026-04-14"
filter: "ind.insurance_"
---# Required Permissions for the Partner Community User Profile

Required Permissions for the Partner Community User Profile[](https://help.salesforce.com/s?language=en_US)

You are here:

1.  [Salesforce Help](/s/?language=en_US)
2.  [Docs](/s/products?language=en_US)
3.  [Digital Insurance](https://help.salesforce.com/s/articleView?id=ind.insurance_admin_standard.htm&language=en_US&type=5)

# Required Permissions for the Partner Community User Profile

You can add a number of permissions to the Partner Community User profile to grant Partner Community Users access to important information.

This task is optional and should only be completed if you have Partner Community users.

1.  From **Setup**, in the **Quick Find** box, enter Permission Sets.
2.  Click **Permissions Sets**.
3.  Click **New**.
4.  Enter a **Label** and **API Name**.
5.  From the **License** dropdown, select **Partner Community**.
6.  Click **Save**.
7.  In the **Apps** section, click **Object Settings**.
8.  Click the object.
9.  Click **Edit**.
10.  In **Object Permissions** enable the appropriate permissions, for example, **Read**, **Create**, **Edit** , and **Delete**.
11.  In **Field Permissions**, enable the appropriate permissions, for example, **Read Access** and **Edit Access**.
12.  Repeat the previous three steps for each of these custom objects and fields.
     
     | Object | Field | Permissions to Set |
     | --- | --- | --- |
     |  |  | **Create** | **Read** | **Edit** | **Delete** |
     | **Billing Account** |  | X | X | X | X |
     | Automatic Payment Amount |  | X | X |  |
     | Bill Due Date |  | X | X |  |
     | Bill Status |  | X | X |  |
     | **Group Census Member Plan** Note: Access to this object is only required for users that work with Group Benefits. |   | X | X | X | X |
     | **Help Product Relationships** |  | X | X | X | X |
     |  | Attribute Selected Values |  | X | X |  |
     |  | Fee Amount |  | X | X |  |
     |  | Insured Party Number |  | X | X |  |
     |  | Insured Party Spec Id |  | X | X |  |
     |  | Party |  | X | X |  |
     |  | Premium |  | X | X |  |
     |  | Prorated Fee Amount |  |  | X |  |
     |  | Prorated Premium |  | X | X |  |
     |  | Prorated Tax Amount |  | X | X |  |
     |  | Tax Amount |  | X | X |  |
     |  | Total Sum Insured |  | X | X |  |
     | **Insured Item Parties** |  | X | X | X | X |
     |  | Attribute Selected Values |  | X | X |  |
     |  | Help Product Relationship |  | X | X |  |
     | **Insured Items** |  | X | X | X | X |
     |  | Attribute Selected Values |  | X | X |  |
     |  | Fee Amount |  | X | X |  |
     |  | Held Product Relationship |  | X | X |  |
     |  | Insured Item Number |  | X | X |  |
     |  | Insured Item Spec |  | X | X |  |
     |  | Parent Insured Item |  | X | X |  |
     |  | Policy Insured Item Spec |  | X | X |  |
     |  | Prorated Fee Amount |  | X | X |  |
     |  | Prorated Premium |  | X | X |  |
     |  | Prorated Tax Amount |  | X | X |  |
     |  | Tax Amount |  | X | X |  |
     |  | Total Sum Insured |  | X | X |  |
     | **Parties** |  |  | X |  |  |
     | **Policy Coverages** |  | X | X | X | X |
     |  | Attribute Selected Values |  | X | X |  |
     |  | Coverage Spec |  | X | X |  |
     |  | End Date |  | X | X |  |
     |  | Fee Amount |  | X | X |  |
     |  | Insured Item |  | X | X |  |
     |  | Insured Party |  | X | X |  |
     |  | Policy Coverage Spec |  | X | X |  |
     |  | Premium |  | X | X |  |
     |  | Prorated Premium |  | X | X |  |
     |  | Prorated Fee Amount |  | X | X |  |
     |  | Prorated Tax Amount |  | X | X |  |
     |  | Start Date |  | X | X |  |
     |  | Tax Amount |  | X | X |  |
     | **Policy Pricing Adjustments** |  | X | X | X |  |
     |  | Adjustment Type |  | X | X |  |
     |  | Amount |  | X |  |  |
     |  | Applicable Item Type |  | X | X |  |
     |  | Coverage |  | X | X |  |
     |  | Insured Item |  | X | X |  |
     |  | Party Relationship |  | X | X |  |
     |  | Tax/Fee Id |  | X | X |  |
     |  | Transaction |  | X | X |  |
     | **Product Child Item** |  |  | X |  |  |
     | **Product Taxes and Fees** |  |  | X |  |  |
     | **Quote Pricing Adjustments** |  | X | X | X |  |
     |  | Adjustment Type |  | X | X |  |
     |  | Amount |  | X | X |  |
     |  | Quote Item |  | X | X |  |
     |  | Tax/Fee Id |  | X | X |  |
     | **Statements** |  | X | X | X |  |
     |  | Balance Due |  | X | X |  |
     |  | Due Date |  | X | X |  |
     |  | Fee Due |  | X | X |  |
     |  | Previous Balance |  | X | X |  |
     |  | Statement Date |  | X | X |  |
     |  | Statement Period End Date |  | X | X |  |
     |  | Statement Period Start Date |  | X | X |  |
     |  | Tax Due |  | X | X |  |
     | **Transactions** |  | X | X | X |  |
     |  | Amount |  | X | X |  |
     |  | Fee Amount |  | X | X |  |
     |  | Post Date |  | X | X |  |
     |  | Statement Id |  | X | X |  |
     |  | Tax Amount |  | X | X |  |
     |  | Transaction Date |  | X | X |  |
     |  | Transaction Number |  | X | X |  |
     |  | Type |  | X | X |  |
     

Did this article solve your issue?

Let us know so we can improve!

YesNo