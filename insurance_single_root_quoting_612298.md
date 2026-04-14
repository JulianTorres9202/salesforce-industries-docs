---
title: "Single Root Quoting"
source: "https://help.salesforce.com/s/articleView?id=ind.insurance_single_root_quoting_612298.htm&language=en_US&type=5"
scraped: "2026-04-14"
filter: "ind.insurance_"
---# Single Root Quoting

Single Root Quoting[](https://help.salesforce.com/s?language=en_US)

You are here:

1.  [Salesforce Help](/s/?language=en_US)
2.  [Docs](/s/products?language=en_US)
3.  [Digital Insurance](https://help.salesforce.com/s/articleView?id=ind.insurance_admin_standard.htm&language=en_US&type=5)

# Single Root Quoting

You can configure quotes directly in the Quote object, without any need to go through an OmniScript flow.

We've built the Quote UI using Salesforce Lightning web component technology. You don't need to extend most of these Lightning web components to offer a full-featured experience to your users who work with insurance quotes.

[](https://help.salesforce.com/s?language=en_US)

Your basic workflow:

[](https://help.salesforce.com/s?language=en_US)

1.  [Create a New Single Root Quote](https://help.salesforce.com/s/articleView?id=ind.insurance_create_a_new_single_root_quote_612379.htm&language=en_US&type=5 "To estimate how much a policy would cost, you use a quote.")
    
    To estimate how much a policy would cost, you use a quote.
    
2.  [Configure a Quote](https://help.salesforce.com/s/articleView?id=ind.insurance_configure_a_quote_612433.htm&language=en_US&type=5 "Once you have created a quote, you can configure it to provide your customer with exactly the coverage they need.")
    
    Once you have created a quote, you can configure it to provide the coverages needed.
    

[](https://help.salesforce.com/s?language=en_US)

[](https://help.salesforce.com/s?language=en_US)After you've created and configured a quote, there are several other things you may want to do and be aware of:

[](https://help.salesforce.com/s?language=en_US)

-   [](https://help.salesforce.com/s?language=en_US)[Quote Rating](https://help.salesforce.com/s/articleView?id=ind.insurance_quote_rating_612853.htm&language=en_US&type=5 "You can rate quotes as many times as you need to during the quoting process. When you rate a quote, optional coverage validation rules and optional coverage relationship rules run, and a price is created and displayed for the coverage.")
    
    You can rate quotes as many times as you need to during the quoting process. When you rate a quote, optional coverage validation rules and optional coverage relationship rules run, and a price is created and displayed for the coverage.
    
-   [](https://help.salesforce.com/s?language=en_US)[Quote Versioning](https://help.salesforce.com/s/articleView?id=ind.insurance_quote_versioning_612894.htm&language=en_US&type=5 "You can create and compare quote versions from a Quote record.")
    
    You can create and compare quote versions from a Quote record.
    
-   [](https://help.salesforce.com/s?language=en_US)[Quote Record Types](https://help.salesforce.com/s/articleView?id=ind.insurance_quote_record_types_612976.htm&language=en_US&type=5 "The Type field on the Quote Details tab helps you to differentiate between quotes created for new business and endorsement (mid-term adjustment) quotes.")
    
    The **Type** field on the **Quote** Details tab helps you to differentiate between quotes created for new business and endorsement (mid-term adjustment) quotes.
    
-   [](https://help.salesforce.com/s?language=en_US)[Issue a Policy from the Quote UI](https://help.salesforce.com/s/articleView?id=ind.insurance_issue_a_policy_from_the_quote_ui_612999.htm&language=en_US&type=5 "You can issue a policy directly from a quote using the Issue Policy button.")
    
    You can issue a policy directly from a quote using the Issue Policy button.
    
-   [](https://help.salesforce.com/s?language=en_US)[Optional Coverage Rules for Quoting](https://help.salesforce.com/s/articleView?id=ind.insurance_optional_coverage_rules_for_quoting_613045.htm&language=en_US&type=5 "When you make changes to insured items, insured parties, and coverages on the Quote UI, optional coverage rules run. Which rules run and what the system does depends on what you've done to the quote.")
    
    When you make changes to insured items, insured parties, and coverages on the Quote UI, optional coverage rules run. Which rules run and what the system does depends on what you've done to the quote.
    
-   [](https://help.salesforce.com/s?language=en_US)[Commissions for Quoting](https://help.salesforce.com/s/articleView?id=ind.insurance_commissions_for_quoting_613215.htm&language=en_US&type=5 "You can use a variety of commission calculations that apply to individual agents and products in different time periods. You get to choose which events trigger a calculation, including quotes. As agents do business, services calculate and save commission data to quote objects so you can view and report on them.")
    
    You can use a variety of commission calculations that apply to individual agents and products in different time periods. You get to choose which events trigger a calculation, including quotes. As agents do business, services calculate and save commission data to quote objects so you can view and report on them.
    

[](https://help.salesforce.com/s?language=en_US)

## What's Next

After you have configured the quote and issued a policy, you can view and modify them on the Policy (Asset) record.

See [Manage Insurance Policies](https://help.salesforce.com/s/articleView?id=ind.insurance_policy_administration_621128.htm&language=en_US&type=5 "Insurance Policy Administration extends throughout the lifecycle of an insurance policy. Any updates made to a policy during its term are managed through policy transactions.") to learn more.

-   **[Create a New Single Root Quote](https://help.salesforce.com/s/articleView?id=ind.insurance_create_a_new_single_root_quote_612379.htm&language=en_US&type=5)**  
    To estimate how much a policy would cost, you use a quote.
-   **[Configure a Quote](https://help.salesforce.com/s/articleView?id=ind.insurance_configure_a_quote_612433.htm&language=en_US&type=5)**  
    Once you have created a quote, you can configure it to provide your customer with exactly the coverage they need.
-   **[Quote Rating](https://help.salesforce.com/s/articleView?id=ind.insurance_quote_rating_612853.htm&language=en_US&type=5)**  
    You can rate quotes as many times as you need to during the quoting process. When you rate a quote, optional coverage validation rules and optional coverage relationship rules run, and a price is created and displayed for the coverage.
-   **[Quote Versioning](https://help.salesforce.com/s/articleView?id=ind.insurance_quote_versioning_612894.htm&language=en_US&type=5)**  
    You can create and compare quote versions from a Quote record.
-   **[Quote Record Types](https://help.salesforce.com/s/articleView?id=ind.insurance_quote_record_types_612976.htm&language=en_US&type=5)**  
    The **Type** field on the **Quote** Details tab helps you to differentiate between quotes created for new business and endorsement (mid-term adjustment) quotes.
-   **[Issue a Policy from the Quote UI](https://help.salesforce.com/s/articleView?id=ind.insurance_issue_a_policy_from_the_quote_ui_612999.htm&language=en_US&type=5)**  
    You can issue a policy directly from a quote using the Issue Policy button.
-   **[Optional Coverage Rules for Quoting](https://help.salesforce.com/s/articleView?id=ind.insurance_optional_coverage_rules_for_quoting_613045.htm&language=en_US&type=5)**  
    When you make changes to insured items, insured parties, and coverages on the Quote UI, optional coverage rules run. Which rules run and what the system does depends on what you've done to the quote.
-   **[Commissions for Quoting](https://help.salesforce.com/s/articleView?id=ind.insurance_commissions_for_quoting_613215.htm&language=en_US&type=5)**  
    You can use a variety of commission calculations that apply to individual agents and products in different time periods. You get to choose which events trigger a calculation, including quotes. As agents do business, services calculate and save commission data to quote objects so you can view and report on them.

Did this article solve your issue?

Let us know so we can improve!

YesNo