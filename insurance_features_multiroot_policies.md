---
title: "Hierarchical Structure and Features of Multiroot Policies"
source: "https://help.salesforce.com/s/articleView?id=ind.insurance_features_multiroot_policies.htm&language=en_US&type=5"
scraped: "2026-04-14"
filter: "ind.insurance_"
---# Hierarchical Structure and Features of Multiroot Policies

Hierarchical Structure and Features of Multiroot Policies[](https://help.salesforce.com/s?language=en_US)

You are here:

1.  [Salesforce Help](/s/?language=en_US)
2.  [Docs](/s/products?language=en_US)
3.  [Digital Insurance](https://help.salesforce.com/s/articleView?id=ind.insurance_admin_standard.htm&language=en_US&type=5)

# Hierarchical Structure and Features of Multiroot Policies

Multiroot policies are organized in a hierarchical structure. A parent policy serves as the primary entity, connecting to multiple child policies, each representing a specific insurance product within the bundle. This approach provides a clear and comprehensive representation of the entire multiroot policy.

[](https://help.salesforce.com/s?language=en_US)

-   Multiroot policies adhere to a parent-child structure with one parent policy and corresponding child policies for each root product in the quote.
    
-   If a policy was originally issued with just one product, but if you plan to add multiple products under the same policy, you must still use the create multiroot policy service. Similarly, if a policy is left with just one product due to the removal of products during a policy endorsement, it continues to maintain a parent-child relationship.
    
-   In a multiroot policy, you can perform a transaction operation only on the parent policy. You can't endorse a child policy.
    
-   Multiroot services are run by using only the quote ID.
    

Did this article solve your issue?

Let us know so we can improve!

YesNo