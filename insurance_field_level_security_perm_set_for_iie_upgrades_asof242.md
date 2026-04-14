---
title: "Field-Level Security Permission Set for Insurance Industries Extension Objects and Fields in Upgrades"
source: "https://help.salesforce.com/s/articleView?id=ind.insurance_field_level_security_perm_set_for_iie_upgrades_asof242.htm&language=en_US&type=5"
scraped: "2026-04-14"
filter: "ind.insurance_"
---# Field-Level Security Permission Set for Insurance Industries Extension Objects and Fields in Upgrades

Field-Level Security Permission Set for Insurance Industries Extension Objects and Fields in Upgrades[](https://help.salesforce.com/s?language=en_US)

You are here:

1.  [Salesforce Help](/s/?language=en_US)
2.  [Docs](/s/products?language=en_US)
3.  [Digital Insurance](https://help.salesforce.com/s/articleView?id=ind.insurance_admin_standard.htm&language=en_US&type=5)

# Field-Level Security Permission Set for Insurance Industries Extension Objects and Fields in Upgrades

Provide your users with access to Insurance Industries Extension objects and fields by creating a permission set.

This task is optional and should only be completed if you use the Insurance Industries Extension managed package.

Important

This step is for upgrading Insurance Industries Extension users only. If you're installing the Insurance Industries Extension managed package for the first time, see [Field-Level Security Permission Set for Insurance Industries Extension Objects and Fields in Installations](https://help.salesforce.com/s/articleView?id=ind.insurance_field_level_security_perm_set_iie_installs_asof242.htm&language=en_US&type=5 "Provide your users with access to Insurance Industries Extension objects and fields by creating a permission set.").

Add Insurance Industries Extension specific objects and fields to a permission set, then assign that permission set to users. Use these steps to add access to all of the objects and fields listed in the table below to a permission set.

1.  From Setup, in the Quick Find box, enter Permission Sets, and then select **Permission Sets**.
2.  Click **New**.
3.  Enter a **Name** and **API Name** for your permission set.
4.  Click **Save**.
5.  Ins the **Apps** section, click **Object Settings**.
6.  Click the object.
    
    | Object | Field |
    | --- | --- |
    | Insurance Policies | 
    -   Original Effective Date
    -   Original Expiration Date
    -   Original Policy
    -   Paid to Date
    -   Policy Term
    -   Premium Calculation Method
    -   Premium Payment Type
    -   Reference Policy Number
    -   Standard Fee
    -   Standard Premium
    -   Standard Tax
    -   Sum Insured
    -   Term Fee
    -   Term Premium
    -   Term Tax
    -   Total Standard Amount
    -   Total Sum Insured
    
     |
    | Insurance Policy Assets | 
    
    -   Asset Name
    -   Primary Policy Participant
    -   Related Insurance Policy Asset
    -   Standard Fee
    -   Standard Premium
    -   Standard Tax
    -   Term Fee
    -   Term Premium
    -   Term Tax
    -   Total Standard Amount
    -   Total Term Amount
    
     |
    | Insurance Policy Coverages | 
    
    -   Insurance Policy Participant
    -   Standard Fee
    -   Standard Premium
    -   Standard Tax
    -   Term Fee
    -   Term Premium
    -   Term Tax
    -   Total Standard Amount
    
     |
    | Insurance Policy Member Assets | 
    
    -   Insurance Policy
    
     |
    | Insurance Policy Participants | 
    
    -   Policyholder
    -   Standard Fee
    -   Standard Premium
    -   Standard Tax
    -   Term Fee
    -   Term Premium
    -   Term Tax
    -   Total Standard Amount
    -   Total Term Amount
    
     |
    | Insurance Policy Surcharges | 
    
    -   Insurance Policy
    -   Insurance Policy Asset
    -   Insurance Policy Coverage
    -   Insurance Policy Participant
    -   Insurance Policy Transaction
    -   Name
    -   Refundable
    -   Source System
    -   Source System Identifier
    -   Surcharge Amount
    -   Surcharged Item
    
     |
    | 
    
    Insurance Policy Terms
    
    (User only need Read access to these fields. Verify that users have this access in Spring ’22 and later versions.)
    
     | 
    
    -   Term Duration Value
    -   Term Duration Unit of Measurement
    -   Term Duration Value
    
     |
    | Insurance Policy Transactions | 
    
    -   Insurance Policy
    -   Insurance Policy Version
    -   Name
    -   Parent Transaction
    -   Tax Amount
    -   Total Amount
    -   Transaction Date
    -   Transaction Effective Date
    -   Transaction Fee
    -   Transaction Number
    -   Transaction Tax
    -   Transaction Type
    
     |
    | Producer Commissions | 
    
    -   Commission Amount
    -   Commissionable Amount
    -   Insurance Policy
    -   Insurance Policy Asset
    -   Insurance Policy Coverage
    -   Insurance Policy Transaction
    -   Name
    -   Payment Date
    -   Producer Production Code
    -   Source System
    -   Source System Identifier
    -   Status
    -   Type
    
     |
    
7.  Click **Edit**.
8.  In **Object Permissions** enable **Read**, **Create**, **Edit** , and **Delete**.
9.  In **Field Permissions**, enable **Read Access** and **Edit Access** for the appropriate fields.
10.  Click **Save**.

[](https://help.salesforce.com/s?language=en_US)

You can now assign this permission set to your users.

[](https://help.salesforce.com/s?language=en_US)

Decide which users need access to these objects and fields, then assign the permission set to a [single user](https://help.salesforce.com/s/articleView?id=platform.perm_sets_assigning.htm&language=en_US&type=5), or [multiple users](https://help.salesforce.com/s/articleView?id=platform.perm_sets_mass_assign.htm&language=en_US&type=5).

Did this article solve your issue?

Let us know so we can improve!

YesNo