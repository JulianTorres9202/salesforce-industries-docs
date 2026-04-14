---
title: "Create Claim Product Rules"
source: "https://help.salesforce.com/s/articleView?id=ind.insurance_create_claim_product_rules_617684.htm&language=en_US&type=5"
scraped: "2026-04-14"
filter: "ind.insurance_"
---# Create Claim Product Rules

Create Claim Product Rules[](https://help.salesforce.com/s?language=en_US)

You are here:

1.  [Salesforce Help](/s/?language=en_US)
2.  [Docs](/s/products?language=en_US)
3.  [Digital Insurance](https://help.salesforce.com/s/articleView?id=ind.insurance_admin_standard.htm&language=en_US&type=5)

# Create Claim Product Rules

Rules on a claim product let you automate parts of creating a claim at runtime. For example, you can create rules that open claim coverages and set loss and expense reserves, or in some cases automatically pay and close the claim.

Before You Begin

-   Create a state model that you'll use for claims.
    
-   Create Vlocity Actions for claims.
    
-   Create Integration Procedures that the Actions will call to do things like open specific claim coverages and set reserves and create claim line items.
    

Claim product rules also change the state of a claim, using state transitions defined in a state model. For example, when a rule opens a coverage on a claim, it can change the state of the claim from Draft to Adjuster Review.

You specify Vlocity Actions in rules to open claim coverages, add payment details to an open coverage, and issue automated payments if business rules allow. The Vlocity Actions call Integration Procedures that handle these tasks. In turn, the Integration Procedures call InsClaimCoverageService:createUpdateCoverage to open the coverage and set reserves. In an auto-payment scenario, the Integration Procedures would additionally call the InsClaimItemService: add and InsClaimItemService: invokeInitiatePaymentIP services.

[](https://help.salesforce.com/s?language=en_US)Note

You'll use the **Underwriting Rules** area on the **Rules** tab to create claim product rules.

1.  Go to the **Rules** tab on your claim product and click **Add Underwriting Rule**.
2.  (Required) Enter a unique **Name** for the underwriting rule.
3.  (Required) In **Applicable Type**, choose **InsuranceClaim\_\_c**.
4.  (Required) In **Transition Name**, choose the transition that you want to happen if this rule evaluates to true.
    
    [](https://help.salesforce.com/s?language=en_US)Tip
    
    The most common transition you'll use will be **Draft > Adjuster Review** or something similar that moves a claim to adjuster review status.
    
5.  (Optional) In **Action**, choose the Vlocity Action you want to be triggered if this rule evaluates to true.
6.  (Optional) Enter an **Expression** to be evaluated.
7.  (Optional) Enter a **Message** to display if this rule evaluates to true.
8.  Select **Active** to activate this rule.
9.  (Optional) Click the bubble icon next to the Active checkbox and enter internal notes about this rule.

Did this article solve your issue?

Let us know so we can improve!

YesNo