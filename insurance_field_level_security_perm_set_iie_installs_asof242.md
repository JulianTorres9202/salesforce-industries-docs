---
title: "Field-Level Security Permission Set for Insurance Industries Extension Objects and Fields in Installations"
source: "https://help.salesforce.com/s/articleView?id=ind.insurance_field_level_security_perm_set_iie_installs_asof242.htm&language=en_US&type=5"
scraped: "2026-04-14"
filter: "ind.insurance_"
---# Field-Level Security Permission Set for Insurance Industries Extension Objects and Fields in Installations

Field-Level Security Permission Set for Insurance Industries Extension Objects and Fields in Installations[](https://help.salesforce.com/s?language=en_US)

You are here:

1.  [Salesforce Help](/s/?language=en_US)
2.  [Docs](/s/products?language=en_US)
3.  [Digital Insurance](https://help.salesforce.com/s/articleView?id=ind.insurance_admin_standard.htm&language=en_US&type=5)

# Field-Level Security Permission Set for Insurance Industries Extension Objects and Fields in Installations

Provide your users with access to Insurance Industries Extension objects and fields by creating a permission set.

This task is optional and should only be completed if you use the Insurance Industries Extension managed package.

Important

This step is for new Insurance Industries Extension users only. If you already use the Insurance Industries Extension, see [Field-Level Security Permission Set for Insurance Industries Extension Objects and Fields in Upgrades](https://help.salesforce.com/s/articleView?id=ind.insurance_field_level_security_perm_set_for_iie_upgrades_asof242.htm&language=en_US&type=5 "Provide your users with access to Insurance Industries Extension objects and fields by creating a permission set.").

You must add Insurance Industries Extension specific objects and fields to a permission set, then assign that permission set to users. Use these steps to add access to all of the objects and fields listed in the table below to a permission set.

1.  From Setup, enter Permission Sets into the **Quick Find** box, then select **Permission Sets**.
2.  Click **New**.
3.  Enter a **Name** and **API Name** for your permission set.
4.  Click **Save**.
5.  Ins the **Apps** section, click **Object Settings**.
6.  Click the object.
    
    | 
    Object
    
     | 
    
    Fields
    
     |
    | --- | --- |
    | Insurance Payment Schedule Entry Details | 
    
    -   Currency
    -   Entry Name
        
    -   Entry Number
        
    -   Fee Amount
        
    -   Insurance Payment Schedule Entry
        
    -   Insurance Policy
        
    -   Insurance Policy Asset
        
    -   Insurance Policy Coverage
        
    -   Insurance Policy Participant
        
    -   Premium Amount
        
    -   Tax Amount
        
    
     |
    | 
    
    Insurance Policies
    
     | 
    
    -   Active
        
    -   Audit Term
        
    -   Billing Carrier Account
        
    -   Cancellation Date
        
    -   Cancellation Reason
        
    -   Cancellation Reason Type
        
    -   Cash Surrender Value
        
    -   Change Subtype
        
    -   Change Type
        
    -   Contract Group Plan
        
    -   Currency ISO Code
        
    -   Current Due Amount
        
    -   Date Renewed
        
    -   Discount
        
    -   Effective Date
        
    -   Eligible for Loan
        
    -   Employer Contribution
        
    -   Expiration Date
        
    -   Final Renewal Date
        
    -   Gross Written Premium
        
    -   Has Any Auto Coverage
        
    -   Intermediary Account
        
    -   Monthly Premium
        
    -   Name Insured
        
    -   Original Effective Date
        
    -   Original Expiration Date
        
    -   Original Policy
        
    -   Owner Name
        
    -   Paid To Date
        
    -   Parent Policy
        
    -   Past Due Amount
        
    -   Payment Due Date
        
    -   Plan
        
    -   Plan Tier
        
    -   Plan Type
        
    -   Policy Description
        
    -   Policy Edit Locked
        
    -   Policy Name
        
    -   Policy Number
        
    -   Policy Paid To Date
        
    -   Policy Term
        
    -   Policy Type
        
    -   Premium Amount
        
    -   Premium Calculation Method
        
    -   Premium Frequency
        
    -   Premium Payment Type
        
    -   Previous Premium
        
    -   Previous Renewal Date
        
    -   Prior Policy
        
    -   Producer
        
    -   Product
        
    -   Rating Date
        
    -   Reference Policy Number
        
    -   Renewal Channel
        
    -   Renewal Date
        
    -   Renewed From Policy
        
    -   Renewed Policy
        
    -   Sale Date
        
    -   Servicing Officer
        
    -   Source Opportunity
        
    -   Source System
        
    -   Source System Identifier
        
    -   Standard Fee
        
    -   Standard Premium
        
    -   Standard Tax
        
    -   Status
        
    -   Substatus
        
    -   Sum Insured
        
    -   Taxes and Surcharges
        
    -   Term Fee
        
    -   Term Premium
        
    -   Term Tax
        
    -   Total Amount
        
    -   Total Amount for Term
        
    -   Total Commission
        
    -   Total Commission Amount
        
    -   Total Fee Amount
        
    -   Total Fee for Term
        
    -   Total Premium for Term
        
    -   Total Standard Amount
        
    -   Total Sum Insured
        
    -   Total Tax Amount
        
    -   Total Tax and Fee Amount
        
    -   Total Tax for Term
        
    -   Total Term Fee Amount
        
    -   Total Term Premium Amount
        
    -   Total Term Tax Amount
        
    -   Underwriting Entity
        
    -   Universal Policy Number
        
    -   Writing Carrier Account
        
    
     |
    | 
    
    Insurance Policy Assets
    
     | 
    
    -   Active
        
    -   Asset Code
        
    -   Asset Name
        
    -   Customer Property
        
    -   Insurance Policy
        
    -   Name
        
    -   Owner Name
        
    -   Primary Policy Participant
        
    -   Related Insurance Policy Asset
        
    -   Source System
        
    -   Source System Identifier
        
    -   Standard Fee
        
    -   Standard Premium
        
    -   Standard Tax
        
    -   Term Fee
        
    -   Term Premium
        
    -   Term Tax
        
    -   Total Standard Amount
        
    -   Total Term Amount
        
    
     |
    | 
    
    Insurance Policy Coverages
    
     | 
    
    -   Benefit Payment Frequency
        
    -   Category
        
    -   Category Code
        
    -   Category Group
        
    -   Category Group Type
        
    -   Contract Group Plan
        
    -   Coverage Code
        
    -   Coverage Name
        
    -   Currency ISO Code
        
    -   Death Benefit Option Type
        
    -   Deductible Amount
        
    -   Description
        
    -   Discount
        
    -   Effective Date
        
    -   Expiration Date
        
    -   Fee Amount
        
    -   Income Option Type
        
    -   Insurance Policy
        
    -   Insurance Policy Asset
        
    -   Insurance Policy Participant
        
    -   Limit Amount
        
    -   Limit Date
        
    -   Limit Percentage
        
    -   Limit Range
        
    -   Name
        
    -   Premium Amount
        
    -   Source system
        
    -   Source System Identifier
        
    -   Standard Fee
        
    -   Standard Premium
        
    -   Standard Tax
        
    -   Term Fee
        
    -   Term Premium
        
    -   Term Tax
        
    -   Total Standard Amount
        
    
     |
    | 
    
    Insurance Policy Member Assets
    
     | 
    
    -   Insurance Policy
        
    -   Insurance Policy Asset
        
    -   Insurance Policy Id
        
    -   Insurance Policy Participant
        
    -   Name
        
    -   Source System
        
    -   Source System Identifier
        
    
     |
    | 
    
    Insurance Policy Participants
    
     | 
    
    -   Active Participant
        
    -   Beneficiary Share Percentage
        
    -   Effective Date
        
    -   Expiration Date
        
    -   Insurance Policy
        
    -   Legal Guardian
        
    -   Minor Beneficiary
        
    -   Name
        
    -   Participant Code
        
    -   Policyholder
        
    -   Primary Participant Account
        
    -   Primary Participant Contact
        
    -   Related Participant Account
        
    -   Related Participant Contact
        
    -   Relationship to Insured
        
    -   Role
        
    -   Source System
        
    -   Source System ID
        
    -   Standard Fee
        
    -   Standard Premium
        
    -   Standard Tax
        
    -   Term Fee
        
    -   Term Premium
        
    -   Term Tax
        
    -   Total Standard Amount
        
    -   Total Term Amount
        
    
     |
    | Insurance Policy Payment Schedule | 
    
    -   Currency
    -   Entry Number
        
    -   Fee Amount
        
    -   Insurance Policy
        
    -   Insurance Policy Transaction
        
    -   Is Paid
        
    -   Premium Amount
        
    -   Schedule Date
        
    -   Status
        
    -   Tax Amount
        
    -   Total Amount
        
    
     |
    | 
    
    Insurance Policy Surcharges
    
     | 
    
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
    
    Insurance Policy Transactions
    
     | 
    
    -   Insurance Policy
        
    -   Insurance Policy Version
        
    -   Name
        
    -   Parent Transaction
        
    -   Status
        
    -   Total Transaction Amount
        
    -   Transaction Amount
        
    -   Transaction Effective Date
        
    -   Transaction Fee
        
    -   Transaction Number
        
    -   Transaction Posted Date
        
    -   Transaction Tax
        
    -   Type
        
    
     |
    | Insurance Policy Transaction Details | 
    
    -   Commission
    -   Fee
        
    -   Insurance Policy Transaction
        
    -   Name
        
    -   Premium
        
    -   Reference Object
        
    -   Tax
        
    
     |
    | 
    
    Producer Commissions
    
     | 
    
    -   Commission Amount
        
    -   Commission Schedule
        
    -   Commissionable Amount
        
    -   Insurance Policy
        
    -   Insurance Policy Asset
        
    -   Insurance Policy Coverage
        
    -   Insurance Policy Transaction
        
    -   Max Commission Amount
        
    -   Min Commission Amount
        
    -   Name
        
    -   Owner Name
        
    -   Parent Producer Commission
        
    -   Payee Producer
        
    -   Payment Date
        
    -   Processing Producer
        
    -   Producer Production Code
        
    -   Source System
        
    -   Source System Identifier
        
    -   Status
        
    -   Type
        
    
     |
    
7.  Click **Edit**.
8.  In **Object Permissions** enable **Read**, **Create**, and **Edit**.
9.  In **Field Permissions**, enable **Read Access** and **Edit Access** for the appropriate fields.
10.  Click **Save**.

[](https://help.salesforce.com/s?language=en_US)

You can now assign this permission set to your users.

[](https://help.salesforce.com/s?language=en_US)

Decide which users need access to these objects and fields, then assign the permission set to a [single user](https://help.salesforce.com/s/articleView?id=platform.perm_sets_assigning.htm&language=en_US&type=5), or [multiple users](https://help.salesforce.com/s/articleView?id=platform.perm_sets_mass_assign.htm&language=en_US&type=5).

Did this article solve your issue?

Let us know so we can improve!

YesNo