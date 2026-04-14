---
title: "Considerations and Limitations for Product Attribute Scope Mapping"
source: "https://help.salesforce.com/s/articleView?id=ind.insurance_claim_prd_att_scope_considerations.htm&language=en_US&type=5"
scraped: "2026-04-14"
filter: "ind.insurance_"
---# Considerations and Limitations for Product Attribute Scope Mapping

Considerations and Limitations for Product Attribute Scope Mapping[](https://help.salesforce.com/s?language=en_US)

You are here:

1.  [Salesforce Help](/s/?language=en_US)
2.  [Docs](/s/products?language=en_US)
3.  [Digital Insurance](https://help.salesforce.com/s/articleView?id=ind.insurance_admin_standard.htm&language=en_US&type=5)

# Considerations and Limitations for Product Attribute Scope Mapping

Review the following considerations and limitations before you set up the Product Attribute Scopes for your org and map them with their respective overridden attributes (Product Attribute Definitions).

## Guidelines to Create Product Attribute Scope Data

-   Deductible, Copay, Coinsurance, and Out-of-Pocket Max categories always use the Calculate Adjustment applicable action. Set the API name to CalculateAdjustment in the dynamic picklist for Applicable Action. This determines how much of the cost the insured person is responsible for when they're making a claim. Set the API name to PaymentAttempted in the dynamic picklist for Applicable Action.
-   Limit - Currency category uses the CalculateAdjustment applicable action to cap the adjusted amount for a loss item at the lowest remaining limit across the Policy, Policy Coverage, Claim, and Claim Coverage scopes. The capping avoids failed payment attempts.
-   Limit - Currency and Limit - Unit Count categories use the Payment Attempted applicable action to check whether the adjusted amount exceeds the limit before payment.
-   Map Deductible to Policy, Policy Coverage, Claim, or Claim Coverage scopes.
-   Map CoPay or Coinsurance to Claim or Claim Coverage scopes.
-   Map Limit - Currency and Limit - Unit Count to Policy, Policy Coverage, Claim, or Claim Coverage scopes.
-   Map Out-of-Pocket Max to Policy, Policy Coverage, Claim, or Claim Coverage scopes.
-   Associate all ‌attribute categories with any single item type.
-   The Policy and Policy Coverage scopes support these duration types.
    -   Calendar Year: Policy limits reset at the end of a calendar year.
    -   Custom Override: Policy limits reset at a specified override date.
    -   Lifetime: Policy limits don’t reset during the policy’s lifetime.
    -   Policy Term: Policy limits reset on renewal at the end of the policy term.
-   The Claim and Claim Coverage scopes support only the Policy Term duration type.

Refer to the list of supported Product Attribute Scope data sets .

| Category | Scope | Applicable Action | Item TYpe | Duration Type |
| --- | --- | --- | --- | --- |
| Deductible | Policy | CalculateAdjustment | Injury | Calendar Year, Custom Override, Lifetime, or Policy Term |
| Deductible | Policy | CalculateAdjustment | Property | Calendar Year, Custom Override, Lifetime, or Policy Term |
| Deductible | Policy | CalculateAdjustment | Any | Calendar Year, Custom Override, Lifetime, or Policy Term |
| Deductible | Policy Coverage | CalculateAdjustment | Injury | Calendar Year, Custom Override, Lifetime, or Policy Term |
| Deductible | Policy Coverage | CalculateAdjustment | Property | Calendar Year, Custom Override, Lifetime, or Policy Term |
| Deductible | Policy Coverage | CalculateAdjustment | Any | Calendar Year, Custom Override, Lifetime, or Policy Term |
| Deductible | Claim | CalculateAdjustment | Injury | Policy Term |
| Deductible | Claim | CalculateAdjustment | Property | Policy Term |
| Deductible | Claim | CalculateAdjustment | Any | Policy Term |
| Deductible | Claim Coverage | CalculateAdjustment | Injury | Policy Term |
| Deductible | Claim Coverage | CalculateAdjustment | Property | Policy Term |
| Deductible | Claim Coverage | CalculateAdjustment | Any | Policy Term |
| Copay | Claim | CalculateAdjustment | Injury | Policy Term |
| Copay | Claim | CalculateAdjustment | Property | Policy Term |
| Copay | Claim | CalculateAdjustment | Any | Policy Term |
| Copay | Claim Coverage | CalculateAdjustment | Injury | Policy Term |
| Copay | Claim Coverage | CalculateAdjustment | Property | Policy Term |
| Copay | Claim Coverage | CalculateAdjustment | Any | Policy Term |
| Coinsurance | Claim | CalculateAdjustment | Injury | Policy Term |
| Coinsurance | Claim | CalculateAdjustment | Property | Policy Term |
| Coinsurance | Claim | CalculateAdjustment | Any | Policy Term |
| Coinsurance | Claim Coverage | CalculateAdjustment | Injury | Policy Term |
| Coinsurance | Claim Coverage | CalculateAdjustment | Property | Policy Term |
| Coinsurance | Claim Coverage | CalculateAdjustment | Any | Policy Term |
| Out-of-Pocket Max | Policy | CalculateAdjustment | Injury | Calendar Year, Custom Override, Lifetime, or Policy Term |
| Out-of-Pocket Max | Policy | CalculateAdjustment | Property | Calendar Year, Custom Override, Lifetime, or Policy Term |
| Out-of-Pocket Max | Policy | CalculateAdjustment | Any | Calendar Year, Custom Override, Lifetime, or Policy Term |
| Out-of-Pocket Max | Policy Coverage | CalculateAdjustment | Injury | Calendar Year, Custom Override, Lifetime, or Policy Term |
| Out-of-Pocket Max | Policy Coverage | CalculateAdjustment | Property | Calendar Year, Custom Override, Lifetime, or Policy Term |
| Out-of-Pocket Max | Policy Coverage | CalculateAdjustment | Any | Calendar Year, Custom Override, Lifetime, or Policy Term |
| Out-of-Pocket Max | Claim | CalculateAdjustment | Injury | Policy Term |
| Out-of-Pocket Max | Claim | CalculateAdjustment | Property | Policy Term |
| Out-of-Pocket Max | Claim | CalculateAdjustment | Any | Policy Term |
| Out-of-Pocket Max | Claim Coverage | CalculateAdjustment | Injury | Policy Term |
| Out-of-Pocket Max | Claim Coverage | CalculateAdjustment | Property | Policy Term |
| Out-of-Pocket Max | Claim Coverage | CalculateAdjustment | Any | Policy Term |
| Limit - Currency | Policy | PaymentAttempted, CalculateAdjustment | Injury | Calendar Year, Custom Override, Lifetime, or Policy Term |
| Limit - Currency | Policy | PaymentAttempted, CalculateAdjustment | Property | Calendar Year, Custom Override, Lifetime, or Policy Term |
| Limit - Currency | Policy | PaymentAttempted, CalculateAdjustment | Any | Calendar Year, Custom Override, Lifetime, or Policy Term |
| Limit - Currency | Policy Coverage | PaymentAttempted, CalculateAdjustment | Injury | Calendar Year, Custom Override, Lifetime, or Policy Term |
| Limit - Currency | Policy Coverage | PaymentAttempted, CalculateAdjustment | Property | Calendar Year, Custom Override, Lifetime, or Policy Term |
| Limit - Currency | Policy Coverage | PaymentAttempted, CalculateAdjustment | Any | Calendar Year, Custom Override, Lifetime, or Policy Term |
| Limit - Currency | Claim | PaymentAttempted, CalculateAdjustment | Injury | Policy Term |
| Limit - Currency | Claim | PaymentAttempted, CalculateAdjustment | Property | Policy Term |
| Limit - Currency | Claim | PaymentAttempted, CalculateAdjustment | Any | Policy Term |
| Limit - Currency | Claim Coverage | PaymentAttempted, CalculateAdjustment | Injury | Policy Term |
| Limit - Currency | Claim Coverage | PaymentAttempted, CalculateAdjustment | Property | Policy Term |
| Limit - Currency | Claim Coverage | PaymentAttempted, CalculateAdjustment | Any | Policy Term |
| Limit - Unit Count | Policy | PaymentAttempted | Injury | Calendar Year, Custom Override, Lifetime, or Policy Term |
| Limit - Unit Count | Policy | PaymentAttempted | Property | Calendar Year, Custom Override, Lifetime, or Policy Term |
| Limit - Unit Count | Policy | PaymentAttempted | Any | Calendar Year, Custom Override, Lifetime, or Policy Term |
| Limit - Unit Count | Policy Coverage | PaymentAttempted | Injury | Calendar Year, Custom Override, Lifetime, or Policy Term |
| Limit - Unit Count | Policy Coverage | PaymentAttempted | Property | Calendar Year, Custom Override, Lifetime, or Policy Term |
| Limit - Unit Count | Policy Coverage | PaymentAttempted | Any | Calendar Year, Custom Override, Lifetime, or Policy Term |
| Limit - Unit Count | Claim | PaymentAttempted | Injury | Policy Term |
| Limit - Unit Count | Claim | PaymentAttempted | Property | Policy Term |
| Limit - Unit Count | Claim | PaymentAttempted | Any | Policy Term |
| Limit - Unit Count | Claim Coverage | PaymentAttempted | Injury | Policy Term |
| Limit - Unit Count | Claim Coverage | PaymentAttempted | Property | Policy Term |
| Limit - Unit Count | Claim Coverage | PaymentAttempted | Any | Policy Term |

## Guidelines to Associate Product Attribute Scope Data to Product Attribute Definition

The Product Attribute Scope (PAS) can be linked to attributes from a policy root product. This association enables the system to manage the limit consumption of these attributes when a claim payment is made against the policy coverages. Refer to the functional guidelines below for configuring the Product Attribute Scope Mapping.

-   Associate the product attribute scope with only Policy or Policy Coverage attributes.
-   Associate a policy root attribute only with the Policy or Claim scope.
    
-   Associate a policy coverage attribute only with the PolicyCoverage or ClaimCoverage scope.
    
-   A deductible can be standalone, or combined with OOPM, Copay and OOPM, or Coinsurance and OOPM.
-   OOPM must be combined with either a Deductible, Copay, or Coinsurance. An OOPM-based attribute can also exist alone in a Policy or Policy Coverage.
-   Assign only Copay or Coinsurance as an attribute for a given Policy or Policy Coverage. They can't coexist as a single Policy or Policy Coverage attribute.
-   Apply Subcoverage and Benefit Name to the Limit - Currency and Limit-Unit Count categories.
-   Ensure a subcoverage is a policy coverage attribute. When you create the product mapped scope for a subcoverage, associate it with a corresponding parentproduct mapped scope record.
    

Did this article solve your issue?

Let us know so we can improve!

YesNo