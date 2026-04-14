---
title: "Policy Management Key Considerations"
source: "https://help.salesforce.com/s/articleView?id=ind.insurance_multi_root_policy_management_considerations.htm&language=en_US&type=5"
scraped: "2026-04-14"
filter: "ind.insurance_"
---# Policy Management Key Considerations

Policy Management Key Considerations[](https://help.salesforce.com/s?language=en_US)

You are here:

1.  [Salesforce Help](/s/?language=en_US)
2.  [Docs](/s/products?language=en_US)
3.  [Digital Insurance](https://help.salesforce.com/s/articleView?id=ind.insurance_admin_standard.htm&language=en_US&type=5)

# Policy Management Key Considerations

Understand how multi-root policies handle lifecycle operations, financial rollups, asynchronous processing, structure rules, and configuration behavior across parent and child policies.

-   Multi-root policies follow a parent–child structure and operate with a lifecycle distinct from single-root policies. All life cycle operations, including renewal and endorsement, occur at the parent policy level.
-   Premiums and taxes calculate at the child policy level and roll up to the parent policy to provide a consolidated financial view.
-   Multi-root policy lifecycle operations run asynchronously through a separate set of APIs. Users receive status updates through bell icon notifications or by subscribing to lifecycle events such as Insurance Policy Issuance Status Event for policy issuance.
-   The parent policy acts as a container for the multi-root structure and isn’t associated with products, attributes, clauses, or surcharges.
-   Surcharges and clauses are supported at each root product in a quote and the corresponding child policy.
-   Single-root and multi-root policies can’t be converted between each other. A multi-root policy can start with a single root product and still follow the multi-root lifecycle.
-   All child policies under the same parent policy use the same currency.
-   Configure additional fields at the parent policy level using the predefined instance key parentPolicyIdentifier.
-   Child policies support custom reference numbers. Reference numbers remain unchangeable once set and default to the policy ID when not provided. When you add a new child policy during endorsement or renewal, you can assign a reference number using additional fields. If you don’t specify a reference number, it defaults to the ID of the policy.
-   Set rating date at the parent policy level using the additional fields. This date applies uniformly to both parent and child policies. Rating dates provided at the child policy level don’t affect pricing or computation logic. However, the rating date set at parent will be used for further processing such as passing it during renewal or endorsement quote.
-   Each child policy creates a transaction record. The parent policy creates a corresponding transaction that represents the rolled-up amounts from all child policy transactions.

Did this article solve your issue?

Let us know so we can improve!

YesNo