---
title: "Insurance Policy Administration"
source: "https://help.salesforce.com/s/articleView?id=ind.insurance_admin_policy_administration.htm&language=en_US&type=5"
scraped: "2026-04-13"
filter: "ind.insurance_"
---# Insurance Policy Administration

Insurance Policy Administration[](https://help.salesforce.com/s?language=en_US)

You are here:

1.  [Salesforce Help](/s/?language=en_US)
2.  [Docs](/s/products?language=en_US)
3.  [Digital Insurance](https://help.salesforce.com/s/articleView?id=ind.insurance_admin_standard.htm&language=en_US&type=5)

# Insurance Policy Administration

Insurance Policy Administration extends throughout the lifecycle of an insurance policy. Any updates made to a policy during its term are managed through policy transactions.

-   **[Insurance Policy Lightning Web Component](https://help.salesforce.com/s/articleView?id=ind.insurance_admin_policy_lwc.htm&language=en_US&type=5)**  
    The Insurance policy Lightning web component (LWC) gives captive agents quick access to important policy information directly on the Insurance Policy record.
-   **[Insurance Product Configuration Lightning Web Component](https://help.salesforce.com/s/articleView?id=ind.insurance_product_config_lwc.htm&language=en_US&type=5)**  
    Dynamically see how policy attribute changes affect the premium, enabling efficient, real-time quote generation. This component accepts multiple rating inputs and calls the Insurance Rating POST and PATCH APIs to update attribute values for specific coverages.
-   **[Insurance Product Selection Lightning Web Component](https://help.salesforce.com/s/articleView?id=ind.insurance_product_select_lwc.htm&language=en_US&type=5)**  
    The Insurance Product Selection Lightning Web Component enables end users to effortlessly compare multiple rated insurance products and choose the optimal plan directly within a guided OmniScript flow.
-   **[APIs and Invocable Actions in Insurance Policy Administration](https://help.salesforce.com/s/articleView?id=ind.insurance_admin_policies_apis_ia.htm&language=en_US&type=5)**  
    Enhance your insurance policy administration with policy APIs and invocable actions. These APIs integrate seamlessly with Omniscripts to help you efficiently manage policy data. Use the invocable actions in Salesforce flows to manage policies. An Insurance Policy Transaction record is created, categorizing the transaction for the insurance policy. Premium amounts and taxes are prorated based on the effective dates, if applicable. Tax details are stored in the InsurancePolicySurcharge object.
-   **[Insurance Policy Bulk Renewal Implementor Journey](https://help.salesforce.com/s/articleView?id=ind.insurance_policy_bulk_renewal.htm&language=en_US&type=5)**  
    Automate the process of renewing multiple insurance policies at once with bulk renewal. Insurance providers can renew policies at scale by grouping eligible policies and processing them in batches.
-   **[Manage Multi-Root Quoting and Policy Lifecycle](https://help.salesforce.com/s/articleView?id=ind.insurance_multi_root_quoting_and_policy_lifecycle.htm&language=en_US&type=5)**  
    Streamline insurance sales by grouping multiple root products such as Auto, Home, and Medical into a single quote and policy structure. Insurance carriers can add multiple root products to a quote and offer them together as a single unit. This topic explains what a multi-root policy is, how it differs from a single-root policy, and the key considerations across quoting and policy lifecycle management.
-   **[Insurance Policy Out of Sequence Endorsement](https://help.salesforce.com/s/articleView?id=ind.insurance_out_of_sequence_endorsement.htm&language=en_US&type=5)**  
    Perform a backdated change on a policy in the past, current, or future policy term, even when another policy version with an effective date later than the endorsement date already exists. When policyholders or insurance brokers issue an out-of-sequence policy endorsement, the changes automatically apply to all future policy versions to maintain consistency.
-   **[Common Features of Insurance Policy Administration](https://help.salesforce.com/s/articleView?id=ind.insurance_admin_policies_features.htm&language=en_US&type=5)**  
    Learn how policy APIs and invocable actions manage policy transactions such as issuance, endorsement, renewal, and cancellation. Calculate term taxes based on transaction types and policy durations, and support both annual and nonannual policies.

Did this article solve your issue?

Let us know so we can improve!

YesNo