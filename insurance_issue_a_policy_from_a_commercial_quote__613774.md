---
title: "Issue a Policy from a Commercial Quote"
source: "https://help.salesforce.com/s/articleView?id=ind.insurance_issue_a_policy_from_a_commercial_quote__613774.htm&language=en_US&type=5"
scraped: "2026-04-14"
filter: "ind.insurance_"
---# Issue a Policy from a Commercial Quote

Issue a Policy from a Commercial Quote[](https://help.salesforce.com/s?language=en_US)

You are here:

1.  [Salesforce Help](/s/?language=en_US)
2.  [Docs](/s/products?language=en_US)
3.  [Digital Insurance](https://help.salesforce.com/s/articleView?id=ind.insurance_admin_standard.htm&language=en_US&type=5)

# Issue a Policy from a Commercial Quote

You can issue a commercial policy directly from a quote using the Issue Policy button.

1.  Click the **Issue Policy** button.
2.  A dialog box opens. You can edit the information in the **Policy Number**, **Effective Date** , and **Premium Frequency** fields as necessary.
    
    -   **Policy Number**: The number of the policy being created. This field pre-fills with the name of the quote.
        
    -   **Effective Date**: The date the policy goes into effect. This field pre-fills with the effective date set of the quote.
        
    -   **Premium Frequency**: The frequency the premium is due.
        
    
    Note
    
    You can customize these fields by editing the IssuePolicy field set on the Insurance Policy object. See [Edit Field Sets](https://help.salesforce.com/s/articleView?id=sf.fields_editing_field_sets.htm&amp%3Btype=5&language=en_US&type=5) for details.
    
    The **Expiration Date** is a formula field that will automatically adjust according to the **Term** set on the quote (when the quote is created) and the **Effective Date** chosen. This field cannot be manually modified.
    
3.  Click **Create**.
    
    The Insurance Quote Commercial LWC issues the policy and generates the new Insurance Policy record.
    

[](https://help.salesforce.com/s?language=en_US)

[](https://help.salesforce.com/s?language=en_US)When you issue a policy with the **Issue Policy** button, you automatically create a **Revenue Schedule** and a **Transaction** that you can view on the Insurance Policy record.

Did this article solve your issue?

Let us know so we can improve!

YesNo