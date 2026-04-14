---
title: "Determine the Policy Lifecycle at Issuance"
source: "https://help.salesforce.com/s/articleView?id=ind.insurance_multi_root_determine_policy_lifecycle.htm&language=en_US&type=5"
scraped: "2026-04-14"
filter: "ind.insurance_"
---# Determine the Policy Lifecycle at Issuance

Determine the Policy Lifecycle at Issuance[](https://help.salesforce.com/s?language=en_US)

You are here:

1.  [Salesforce Help](/s/?language=en_US)
2.  [Docs](/s/products?language=en_US)
3.  [Digital Insurance](https://help.salesforce.com/s/articleView?id=ind.insurance_admin_standard.htm&language=en_US&type=5)

# Determine the Policy Lifecycle at Issuance

At the time of policy issuance, you must decide whether the policy should follow a single-root or multi-root lifecycle. This decision applies even when the quote contains only one product.

This decision determines how endorsement and renewal operate for the policy. All lifecycle operations for multi-root policies occur only at the parent policy level.

-   If a policy follows the multi-root lifecycle, it always maintains a parent–child structure.
-   Single-root and multi-root policies can’t be converted between each other.
-   Even if a quote contains only one product, issue it as a multi-root policy if you intend to add additional products later.
-   If you remove products from a multi-root policy until only one remains, the policy still retains its multi-root parent-child structure.

Did this article solve your issue?

Let us know so we can improve!

YesNo