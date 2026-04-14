---
title: "Differences Between Single and Multi Root Policies"
source: "https://help.salesforce.com/s/articleView?id=ind.insurance_multi_root_difference_single_and_multi_root.htm&language=en_US&type=5"
scraped: "2026-04-14"
filter: "ind.insurance_"
---# Differences Between Single and Multi Root Policies

Differences Between Single and Multi Root Policies[](https://help.salesforce.com/s?language=en_US)

You are here:

1.  [Salesforce Help](/s/?language=en_US)
2.  [Docs](/s/products?language=en_US)
3.  [Digital Insurance](https://help.salesforce.com/s/articleView?id=ind.insurance_admin_standard.htm&language=en_US&type=5)

# Differences Between Single and Multi Root Policies

Compare single-root and multi-root policies to understand the differences in structure, lifecycle, and product management.

The structural hierarchy distinguishes a multi-root policy from a single-root policy. A multi-root policy can contain one or many child policies.

Differences between single and multi root
| Aspect | single-root policy | multi-root policy |
| --- | --- | --- |
| Policy structure | A single-root policy is a standalone policy and doesn’t have a parent policy. | A multi-root policy includes a parent policy and one or more child policies. |
| Root products | A single-root policy contains one root product. | A multi-root policy contains one or more root products. |
| Lifecycle model | A single-root policy follows the single-root lifecycle. | A multi-root policy follows the multi-root lifecycle. |
| Issuance decision | The policy follows the single-root lifecycle by default. | The policy follows the multi-root lifecycle based on the decision made at issuance. |
| Adding products later | Additional products require separate policies. | Additional products are added as child policies under the same parent policy. |
| Endorsement | Endorsement is performed on the policy. | Endorsement is performed at the parent policy level. |
| Renewal | Renewal is performed on the policy. | Renewal is performed at the parent policy level. |
| Claims | Claims are supported on the policy. | Claims are supported only on child policies. |
| Conversion | A single-root policy can’t be converted to a multi-root policy. | A multi-root policy can’t be converted to a single-root policy. |

Did this article solve your issue?

Let us know so we can improve!

YesNo