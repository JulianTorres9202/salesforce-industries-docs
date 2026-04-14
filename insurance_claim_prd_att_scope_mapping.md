---
title: "Product Attribute Scope Mapping"
source: "https://help.salesforce.com/s/articleView?id=ind.insurance_claim_prd_att_scope_mapping.htm&language=en_US&type=5"
scraped: "2026-04-14"
filter: "ind.insurance_"
---# Product Attribute Scope Mapping

Product Attribute Scope Mapping[](https://help.salesforce.com/s?language=en_US)

You are here:

1.  [Salesforce Help](/s/?language=en_US)
2.  [Docs](/s/products?language=en_US)
3.  [Digital Insurance](https://help.salesforce.com/s/articleView?id=ind.insurance_admin_standard.htm&language=en_US&type=5)

# Product Attribute Scope Mapping

As a claim admin, you can configure a product with product attribute scopes. These scopes are used to enforce policy limits, such as deductibles, copays, limits, coinsurance, and out-of-pocket max on attributes associated with coverage and root products. These attributes have specific definitions that make sure that the claims management system enforces their policy limit requirements. To use a coverage or root attribute in claims with specific tracking to enforce a policy limit, create it as a record in the Product Attribute Scope entity and add it to either or both the root coverage and policy coverage overrridden attributes. Use the Product Attribute Scope to track the consumption of policy limits, such as deductibles, copays, coinsurance, and out-of-pocket maximums, through a claim for a policy.

### Required Editions

<table class="slds-table slds-table_bordered slds-m-bottom_small edition" lwc-3eigj2skqo3=""><colgroup lwc-3eigj2skqo3=""><col style="width:100%" lwc-3eigj2skqo3=""></colgroup><tbody lwc-3eigj2skqo3=""><tr class="" lwc-3eigj2skqo3=""><td style="vertical-align:top;" class="slds-cell-wrap" lwc-3eigj2skqo3=""><a title="Give users access to Claims Management features. Review the supported edition and permission sets for Claims Management." href="https://help.salesforce.com/s/articleView?id=ind.insurance_claim_perm_set_licenses.htm&amp;language=en_US&amp;type=5" lwc-3eigj2skqo3="">View supported editions.</a></td></tr></tbody></table>

Let's look at an example.

Example If you set the coverage limit for collision of $10,000 per claim when a policy is sold, then the limit for collision coverage per claim can't exceed $10,000. When a policyholder files a claim for a collision, the product attribute scope defines the functional data, such as scope, category, duration type and so on necessary to enforce and track this limit. This makes sure that when you make payments to the claimant, they don't exceed the $10,000 limit set for collision coverage.

-   **[Considerations and Limitations for Product Attribute Scope Mapping](https://help.salesforce.com/s/articleView?id=ind.insurance_claim_prd_att_scope_considerations.htm&language=en_US&type=5)**  
    Review the following considerations and limitations before you set up the Product Attribute Scopes for your org and map them with their respective overridden attributes (Product Attribute Definitions).
-   **[Create a Product Attribute Scope](https://help.salesforce.com/s/articleView?id=ind.insurance_claim_create_prd_att_scope.htm&language=en_US&type=5)**  
    Follow these steps to create a new Product Attribute Scope.
-   **[Add the Product Attribute Processing Definition Component to the Product Details Page](https://help.salesforce.com/s/articleView?id=ind.insurance_claim_prd_att_lwc.htm&language=en_US&type=5)**  
    Use Lightning App Builder to add the Product Attribute Processing Definition Lightning web component to the policy root product details page.
-   **[Create Product Mapped Scopes](https://help.salesforce.com/s/articleView?id=ind.insurance_claim_create_prd_att_mapped_scope.htm&language=en_US&type=5)**  
    Map the Product Attribute Scope to their respective root product attributes before creating a quote and issuing an insurance policy.
-   **[Create Product Mapped Scopes and Assign Sublimits with Benefit Types](https://help.salesforce.com/s/articleView?id=ind.insurance_claim_sublimits.htm&language=en_US&type=5)**  
    Some product attributes have sublimits that are defined as subcoverages. Configure a mapped scope for these subcoverages by defining them as subcoverages and them mapping them to the parent mapped scope.

Did this article solve your issue?

Let us know so we can improve!

YesNo