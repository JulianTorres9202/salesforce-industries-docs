---
title: "Create a Product Attribute Scope"
source: "https://help.salesforce.com/s/articleView?id=ind.insurance_claim_create_prd_att_scope.htm&language=en_US&type=5"
scraped: "2026-04-14"
filter: "ind.insurance_"
---# Create a Product Attribute Scope

Create a Product Attribute Scope[](https://help.salesforce.com/s?language=en_US)

You are here:

1.  [Salesforce Help](/s/?language=en_US)
2.  [Docs](/s/products?language=en_US)
3.  [Digital Insurance](https://help.salesforce.com/s/articleView?id=ind.insurance_admin_standard.htm&language=en_US&type=5)

# Create a Product Attribute Scope

Follow these steps to create a new Product Attribute Scope.

### Required Editions

<table class="slds-table slds-table_bordered slds-m-bottom_small edition" lwc-3eigj2skqo3=""><colgroup lwc-3eigj2skqo3=""><col style="width:100%" lwc-3eigj2skqo3=""></colgroup><tbody lwc-3eigj2skqo3=""><tr class="" lwc-3eigj2skqo3=""><td style="vertical-align:top;" class="slds-cell-wrap" lwc-3eigj2skqo3=""><a title="Give users access to Claims Management features. Review the supported edition and permission sets for Claims Management." href="https://help.salesforce.com/s/articleView?id=ind.insurance_claim_perm_set_licenses.htm&amp;language=en_US&amp;type=5" lwc-3eigj2skqo3="">View supported editions.</a></td></tr></tbody></table>

| User Permissions Needed |
| --- |
| [View user permissions.](https://help.salesforce.com/s/articleView?id=ind.insurance_claim_perm_set_licenses.htm&language=en_US&type=5 "Give users access to Claims Management features. Review the supported edition and permission sets for Claims Management.") |

1.  From the App Launcher, find and select **Product Attribute Scopes**.
2.  Click **New**.
3.  Enter a Name.
4.  Select a **Category**.
5.  Select a **Scope**.
    
    **Policy:** This attribute value describes a limit or deductible that is aggregated across a whole policy.
    
    **Policy Coverage:** This attribute value describes a limit or deductible that is aggregated for one coverage on a policy.
    
    **Claim:** This attribute value describes a limit or deductible that applies per claim.
    
    **Claim Coverage:** This attribute value describes a limit or deductible that applies per claim coverages.
    
6.  Select Applicable Actions.
    
    To choose the appropriate actions, think about when you want your system to evaluate the attribute.
    
7.  Select an Item Type.
    
    **Any:** Track a limit marked with the Any item type for a claim coverage where the claim item's product specification type is either ClaimDamage or ClaimInjury.
    
    **Property:** Track a limit marked with the Property item type for a claim coverage where the claim item's product specification type is ClaimDamage.
    
    **Injury:** Track a limit marked with the Injury item type for a claim coverage where the claim item's product specification type is ClaimInjury.
    
8.  For Duration Type, select when the policy limits are reset.
    1.  For the Policy or Policy Coverage scope, select one of these duration types.
        
        -   Calendar Year: Policy limits reset at the end of a calendar year.
            
        -   Custom Override: Policy limits reset at a specified override date. Specify the Override Month and Override Date.
            
        -   Lifetime: Policy limits don’t reset during the policy’s lifetime.
            
        -   Policy Term: Policy limits reset on renewal at the end of the policy term.
            
        
    2.  For the Claim or Claim Coverage scope, select Policy Term as the duration type.
9.  Save your changes.

Did this article solve your issue?

Let us know so we can improve!

YesNo