---
title: "Insurance Claim Products"
source: "https://help.salesforce.com/s/articleView?id=ind.insurance_claim_prd_model.htm&language=en_US&type=5"
scraped: "2026-04-14"
filter: "ind.insurance_"
---# Insurance Claim Products

Insurance Claim Products[](https://help.salesforce.com/s?language=en_US)

You are here:

1.  [Salesforce Help](/s/?language=en_US)
2.  [Docs](/s/products?language=en_US)
3.  [Digital Insurance](https://help.salesforce.com/s/articleView?id=ind.insurance_admin_standard.htm&language=en_US&type=5)

# Insurance Claim Products

Set up Insurance Claim products to manage different types of insurance claims, including those related to property damage or personal injury. This framework ensures efficient management of specific cases, such as auto and medical insurance claims. The framework benefits administrators by standardizing processes while accommodating diverse needs.

### Required Editions

<table class="slds-table slds-table_bordered slds-m-bottom_small edition" lwc-3eigj2skqo3=""><colgroup lwc-3eigj2skqo3=""><col style="width:100%" lwc-3eigj2skqo3=""></colgroup><tbody lwc-3eigj2skqo3=""><tr class="" lwc-3eigj2skqo3=""><td style="vertical-align:top;" class="slds-cell-wrap" lwc-3eigj2skqo3=""><a title="Give users access to Claims Management features. Review the supported edition and permission sets for Claims Management." href="https://help.salesforce.com/s/articleView?id=ind.insurance_claim_perm_set_licenses.htm&amp;language=en_US&amp;type=5" lwc-3eigj2skqo3="">View supported editions.</a></td></tr></tbody></table>

Claim product models include claim damage specs, claim injury specs, and the same coverage specs used in your insurance product models. To create a claim product model, you start with a root product that includes these specifications:

-   **Claim Damage Spec:** These describe the damage to an asset involved in the claim.
-   **Claim Injury Spec:** These describe the injuries sustained by a person involved in the claim.

For example, in an auto claim, the Auto Claim product includes two child specifications:

-   **Injury Spec:** These store details about any injuries and other personnel information needed during the claim processing.
-   **Involved Vehicle Spec:** These store information about the damages to the vehicles involved in the incident.

You can reuse claim product specs across multiple claim product models, even across different lines of business. For example, you can create an involved property spec that models third-party damaged property. You can then use it on Auto, Watercraft, Motorcycle, and RV insurance claim products.

Claim product models include both standard and extended attributes. Administrators create standard attributes for Claims, Claim Damage Specs, and Claim Injury Specs during product modeling. They also create extended attributes for Claim Damage Specs and Claim Injury Specs. The product attribute scope is mapped to policy or policy coverage attributes, enabling admins to enforce policy limits such as deductibles. This scope provides additional data for processing the policy limit consumption. The claim product model is also where admins set up workflow rules to manage claims. Claim workflow rules use state transitions to automate straight-through processing by executing actions when rules are met.

While setting up a claim product model, admins can:

-   Create a hierarchical product structure with a root product and child products, including claim, claim damage, and claim injury record types.
-   Ensure proper system logic by setting the correct product specification type for each product type in the setup.
-   Simplify attribute management by assigning attributes at the class level, enabling all products within a class to inherit them.
-   Configure Product Attribute Scope (PAS) and Product Attribute Mapped Scope (PAMS) to manage consumption of policy limits effectively. This configuration is done at the policy product level for attributes such as deductibles, copays, coinsurance, and out-of-pocket maximums (OOPM).

This feature addresses the challenge of creating a flexible and extensible claims system that can handle different types of claims, such as those involving property damage or personal injury. It provides a structured way to define products and their attributes based on the specific needs of a claim, ensuring the system is adaptable for various use cases, including health insurance.

Did this article solve your issue?

Let us know so we can improve!

YesNo