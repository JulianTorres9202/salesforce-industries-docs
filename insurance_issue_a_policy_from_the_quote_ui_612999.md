---
title: "Issue a Policy from the Quote UI"
source: "https://help.salesforce.com/s/articleView?id=ind.insurance_issue_a_policy_from_the_quote_ui_612999.htm&language=en_US&type=5"
scraped: "2026-04-14"
filter: "ind.insurance_"
---# Issue a Policy from the Quote UI

Issue a Policy from the Quote UI[](https://help.salesforce.com/s?language=en_US)

You are here:

1.  [Salesforce Help](/s/?language=en_US)
2.  [Docs](/s/products?language=en_US)
3.  [Digital Insurance](https://help.salesforce.com/s/articleView?id=ind.insurance_admin_standard.htm&language=en_US&type=5)

# Issue a Policy from the Quote UI

You can issue a policy directly from a quote using the Issue Policy button.

1.  Click the **Issue Policy** button on the **Actions** panel.
2.  A dialog box opens. You can edit the information in the **Asset Name** and **Effective Date** fields as necessary.
    
    -   **Asset Name**: The name of the policy that is being created. This field pre-fills with the name of the quote.
        
    -   **Effective Date**: The date the policy goes into effect. This field pre-fills with the Effective Date listed in the quote.
        
    
    Note
    
    You can customize these fields by editing the IssuePolicyFields field set on the Policy (Asset) object. See [Editing Field Sets](https://help.salesforce.com/s/articleView?id=sf.fields_editing_field_sets.htm&amp%3Btype=5&language=en_US&type=5) for details.
    
    The **Expiration Date** is a formula field that will automatically adjust according to the **Term** set on the quote (when the quote is created) and the **Effective Date** chosen. This field cannot be manually modified.
    
3.  Click **Create**.
    
    The Quote Lightning Web Component UI issues the policy and generates the new Policy (Asset) record.
    

[](https://help.salesforce.com/s?language=en_US)

[](https://help.salesforce.com/s?language=en_US)When you issue a policy with the **Issue Policy** button, you automatically create a **Revenue Schedule** , **Transaction**, **Payment Schedule Entry** and **Transaction Details** that you can view on the Policy (Asset) record.

Note

When you issue a policy from a Multi-Root Quote, you create a parent policy that represents all line items included in the quote. Each line item has its own policy that is tied to the parent policy.

Did this article solve your issue?

Let us know so we can improve!

YesNo