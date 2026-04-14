---
title: "Create Power Attributes"
source: "https://help.salesforce.com/s/articleView?id=ind.insurance_create_power_attributes_604759.htm&language=en_US&type=5"
scraped: "2026-04-14"
filter: "ind.insurance_"
---# Create Power Attributes

Create Power Attributes[](https://help.salesforce.com/s?language=en_US)

You are here:

1.  [Salesforce Help](/s/?language=en_US)
2.  [Docs](/s/products?language=en_US)
3.  [Digital Insurance](https://help.salesforce.com/s/articleView?id=ind.insurance_admin_standard.htm&language=en_US&type=5)

# Create Power Attributes

Use power attributes to track limits, deductibles, copays, coinsurance, and out of pocket maximums. Create power attributes the same way you create regular attributes, in the same attribute categories, and then complete some extra configuration steps.

[](https://help.salesforce.com/s?language=en_US)Note

Insurance includes the settings you choose for **Attribute Class**, **Attribute Scope**, **Applicable Actions**, **Applicable Item**, and **Value Type**. They're ready to use without any additional setup or configuration.

1.  Follow steps 1 through 10 in [Create Attributes](https://help.salesforce.com/s/articleView?id=ind.insurance_create_attributes_604671.htm&language=en_US&type=5 "Product attributes define coverages, insured items, and other parts of insurance products and health plans. They correspond to anything that's important to quoting, rating, and writing an insurance policy.").
2.  Select an **Attribute Class**:
    
    [](https://help.salesforce.com/s?language=en_US)
    
    -   **Limit - Currency**
        
    -   **Limit - Scope Count**
        
    -   **Limit - Claim Line Item Unit Count**
        
    -   **Deductible**
        
    -   **Copay**
        
    -   **Coinsurance**
        
    -   **Out Of Pocket Max**
        
    
3.  Select an **Attribute Scope**:
    
    -   Policy
        
        This power attribute describes a limit or deductible that is the aggregate across a whole policy.
        
    -   Policy Coverage
        
        This power attribute describes a limit or deductible that is aggregated for one coverage on a policy.
        
    -   Claim
        
        This power attribute describes a limit or deductible that applies per claim.
        
        [](https://help.salesforce.com/s?language=en_US)Note
        
        You can't specify Claim scope for the attribute class **Limit - Scope Count**.
        
    -   Claim Coverage
        
        This power attribute describes a limit or deductible that applies per claim coverages.
        
    
    [](https://help.salesforce.com/s?language=en_US)Important
    
    Some Attribute Classes must be set to specific Attribute Scopes:
    
    -   Out Of Pocket Max
        
        Attribute Scope: Policy or Policy Coverage only
        
    -   Copay
        
        Attribute Scope: Claim or Claim Coverage only
        
    -   Coinsurance
        
        Attribute Scope: Claim or Claim Coverage only
        
    
    Also, combinations of power attributes matter. When you use Copay or Coinsurance with Deductible, the Attribute Scope of Deductible must be Policy or Policy Coverage.
    
4.  Select **Applicable Actions**.
    
    To choose the appropriate actions, think about when you want your system to evaluate the power attribute:
    
    -   When a claim amount is entered (**ClaimLineItemClaimedAmountEntered** action)
        
    -   When a payment is attempted (**PaymentAttempted** action)
        
    -   When a reserve is adjusted (**ReserveAdjustmentAttempted** action)
        
    
    Each **Attribute Class** has its own set of valid **Applicable Actions**.
    
    | 
    Attribute Class
    
     | 
    
    Applicable Actions
    
     |
    | --- | --- |
    | 
    
    Limit - Currency
    
     | [](https://help.salesforce.com/s?language=en_US)
    
    -   **ClaimLineItemClaimedAmountEntered**
        
    -   **PaymentAttempted**
        
    -   **ReserveAdjustmentAttempted**
        
    
     |
    | 
    
    Limit - Scope Count
    
     | [](https://help.salesforce.com/s?language=en_US)
    
    -   **PaymentAttempted**
        
    -   **ReserveAdjustmentAttempted**
        
    
     |
    | 
    
    Limit - Claim Line Item Unit Count
    
     | [](https://help.salesforce.com/s?language=en_US)
    
    -   **PaymentAttempted**
        
    -   **ReserveAdjustmentAttempted**
        
    
     |
    | 
    
    Deductible
    
     | [](https://help.salesforce.com/s?language=en_US)
    
    -   **ClaimLineItemClaimedAmountEntered**
        
    
     |
    | 
    
    Copay
    
     | [](https://help.salesforce.com/s?language=en_US)
    
    -   **ClaimLineItemClaimedAmountEntered**
        
    
     |
    | 
    
    Coinsurance
    
     | [](https://help.salesforce.com/s?language=en_US)
    
    -   **ClaimLineItemClaimedAmountEntered**
        
    
     |
    | 
    
    Out Of Pocket Max
    
     | [](https://help.salesforce.com/s?language=en_US)
    
    -   **ClaimLineItemClaimedAmountEntered**
        
    
     |
    
    Tip
    
    For Limit - Scope Count and Limit - Claim Line Item Unit Count class attributes, you can choose both **PaymentAttempted** and **ReserveAdjustmentAttempted**.
    
5.  Select an **Applicable Type**:
    
    -   **Any**
        
        This power attribute can apply to both people and property. Use for all power attributes that stand alone.
        
    -   **Property**
        
        This power attribute gets applied to property only, not to people. Use this option only for attributes that are part of split-limit attributes on coverage specs and product specs.
        
    -   **Person**
        
        This power attribute gets applied to people only, not property. Use this option only for attributes that are part of split-limit attributes on coverage specs and product specs.
        
    
6.  Select a **Value Type**:
    
    Select **Number** if this power attribute has one of the following classes:
    
    -   **Limit - Scope Count**
        
    -   **Limit - Claim Line Item Unit Count**
        
    
    -   Select Percentage if this power attribute is **Coinsurance** class.
        
    -   For all other power attribute classes, select **Currency**.
        
7.  Enter a **Benefit Type**:
    
    Enter a **Benefit Type** if this power attribute describes a specific benefit type (health and voluntary benefits) or sublimit (individual insurance).
    
    The **Benefit Type** you enter appears on the coverage spec that this **Benefit Type** applies to.
    
8.  Select a **Duration Type**:
    
    -   Calendar Year
        
        January 1 through December 31, regardless of when the policy term starts. The first year a policy is effective, all power attributes that use Calendar Year apply the day the policy is issued through December 31. For the first year, this duration is almost always less than 365 days.
        
        Calendar Year resets on January 1. Each year following the first year, the duration is 365 days.
        
    -   Policy Term
        
        The time period defined by the start date and expiration date of a policy.
        
    -   [](https://help.salesforce.com/s?language=en_US)
        
        Lifetime
        
        For as long as the policy terms are in force, including after midterm adjustments and renewals.
        
    -   [](https://help.salesforce.com/s?language=en_US)
        
        Rolling time period
        
        A number of days or months with a reset at the beginning of the next period.
        
    

Did this article solve your issue?

Let us know so we can improve!

YesNo