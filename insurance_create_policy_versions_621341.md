---
title: "Create Policy Versions"
source: "https://help.salesforce.com/s/articleView?id=ind.insurance_create_policy_versions_621341.htm&language=en_US&type=5"
scraped: "2026-04-14"
filter: "ind.insurance_"
---# Create Policy Versions

Create Policy Versions[](https://help.salesforce.com/s?language=en_US)

You are here:

1.  [Salesforce Help](/s/?language=en_US)
2.  [Docs](/s/products?language=en_US)
3.  [Digital Insurance](https://help.salesforce.com/s/articleView?id=ind.insurance_admin_standard.htm&language=en_US&type=5)

# Create Policy Versions

With policy versioning, all changes to a policy are tracked in different versions of that policy. So you can create a new version of an existing policy, while maintaining the existing policy record as-is.

You can create versions of existing policies from a Policy (Asset) record. To create a new version of a policy, you must first create an Endorsement (mid-term adjustment) quote, then issue the new policy from that quote.

1.  On an Insurance Policy or Policy (Asset) record, click the **Modify Policy** button on the **Actions** panel.
2.  A dialog box opens. You can edit the information in the **Asset Name** and **Effective Date** fields as necessary.
    
    -   **Asset Name**: The name of the policy version you are creating. This field pre-fills with the name of the current policy.
        
    -   **Effective Date**: The date the new version of the policy goes into effect.
        
    
3.  Click **Create** to generate an Endorsement quote. You can add, remove, edit coverages, and insured items as needed. You can see how the changes affect the price with [Real-time Price Re-rating](https://help.salesforce.com/s/articleView?id=ind.insurance_single_root_quoting_612298.htm&language=en_US&type=5 "You can configure quotes directly in the Quote object, without any need to go through an OmniScript flow.").
4.  Once you have finished making changes to the quote, click the **Issue Policy** button in the **Actions** panel.
5.  A dialog box opens. You can edit the information in the **Asset Name** field as necessary.
6.  Click **Create** to finish issuing the new version of the policy from the Endorsement quote.
7.  After you have issued the policy, you can view the new **Transaction** and **Revenue Schedule** on the Insurance Policy or Policy (Asset) record.

Did this article solve your issue?

Let us know so we can improve!

YesNo