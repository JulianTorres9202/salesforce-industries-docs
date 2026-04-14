---
title: "Create a New Multi-Root Quote"
source: "https://help.salesforce.com/s/articleView?id=ind.insurance_create_a_new_multi_root_quote_613380.htm&language=en_US&type=5"
scraped: "2026-04-14"
filter: "ind.insurance_"
---# Create a New Multi-Root Quote

Create a New Multi-Root Quote[](https://help.salesforce.com/s?language=en_US)

You are here:

1.  [Salesforce Help](/s/?language=en_US)
2.  [Docs](/s/products?language=en_US)
3.  [Digital Insurance](https://help.salesforce.com/s/articleView?id=ind.insurance_admin_standard.htm&language=en_US&type=5)

# Create a New Multi-Root Quote

To estimate how much a policy would cost, you use a quote. Multi-root quoting allows you to add more than one product to a quote.

You can't start a new quote directly from the Quote object. Instead, start on the Opportunities object, because all quotes require an opportunity.

1.  Go to the Opportunities object list view.
2.  Select the Opportunity you want to create a quote for or [create a new Opportunity](https://help.salesforce.com/s/articleView?id=ind.insurance_create_an_opportunity_612244.htm&language=en_US&type=5 "An opportunity represents a sale or pending deal. New business and some endorsement (mid-term adjustment) quotes are created from opportunities.").
3.  On the Quotes panel, click the carat or button for **New Quote**.
4.  On the New Quote window, enter a **Quote Name**.
5.  (Optional) Enter Information in the other fields on the **New Quote** window.
    
    [](https://help.salesforce.com/s?language=en_US)Important
    
    Don't enter a value into the Primary Root Item.
    
    Entering a value into this field causes a conflict that doesn't let you modify the quote on the Quote object.
    
6.  Click **Save**.

[](https://help.salesforce.com/s?language=en_US)

[](https://help.salesforce.com/s?language=en_US)When you click **Save**, you create a blank quote record. Add a product and insured parties or insured items to configure the quote to meet your needs.

[](https://help.salesforce.com/s?language=en_US)

[Configure a Quote](https://help.salesforce.com/s/articleView?id=ind.insurance_configure_a_quote_612433.htm&language=en_US&type=5 "Once you have created a quote, you can configure it to provide your customer with exactly the coverage they need.")

Did this article solve your issue?

Let us know so we can improve!

YesNo