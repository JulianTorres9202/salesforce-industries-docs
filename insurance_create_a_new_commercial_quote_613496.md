---
title: "Create a New Commercial Quote"
source: "https://help.salesforce.com/s/articleView?id=ind.insurance_create_a_new_commercial_quote_613496.htm&language=en_US&type=5"
scraped: "2026-04-14"
filter: "ind.insurance_"
---# Create a New Commercial Quote

Create a New Commercial Quote[](https://help.salesforce.com/s?language=en_US)

You are here:

1.  [Salesforce Help](/s/?language=en_US)
2.  [Docs](/s/products?language=en_US)
3.  [Digital Insurance](https://help.salesforce.com/s/articleView?id=ind.insurance_admin_standard.htm&language=en_US&type=5)

# Create a New Commercial Quote

To estimate how much a commercial policy would cost, you use a quote.

[](https://help.salesforce.com/s?language=en_US)You can't start a new quote directly from the Quote object. Instead, start on the Opportunities object, because all quotes require an opportunity.

[](https://help.salesforce.com/s?language=en_US)

1.  Go to the Opportunities object list view.
2.  Select the Opportunity you want to create a quote for or create a new Opportunity.
3.  On the Quotes panel, click the carat or button for **New Quote**.
4.  Select **Quote** in the New Quote dialog box that appears, then click **Next**.
    
    Note
    
    The quote record types and their associated pages and LWCs are customizable and configurable.
    
5.  On the New Quote window, enter a **Quote Name**.
6.  (Optional) Enter information in the other fields on the **New Quote** window.
    
    Important
    
    Don't enter a value into the Primary Root Item.
    
    Entering a value into this field causes a conflict that doesn't let you modify the quote on the Quote object.
    
7.  Click **Save**.

[](https://help.salesforce.com/s?language=en_US)

[](https://help.salesforce.com/s?language=en_US)When you click **Save**, you create a blank quote record. Add a product and insured parties or insured items to configure the quote to meet your needs.

[](https://help.salesforce.com/s?language=en_US)

[Configure a Commercial Quote](https://help.salesforce.com/s/articleView?id=ind.insurance_configure_a_commercial_quote_613553.htm&language=en_US&type=5 "Once you have created a Commercial quote, you can configure it to provide your customer with exactly the coverage they need.")

#### See Also

-   [Pricing Discount for Multiroot Quotes](https://help.salesforce.com/s/articleView?id=ind.insurance_pricing_discount.htm&language=en_US&type=5)

Did this article solve your issue?

Let us know so we can improve!

YesNo