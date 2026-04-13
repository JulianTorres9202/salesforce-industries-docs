---
title: "Add Insured Items to a Commercial Quote"
source: "https://help.salesforce.com/s/articleView?id=ind.insurance_add_insured_items_to_a_commercial_quote_613624.htm&language=en_US&type=5"
scraped: "2026-04-13"
filter: "ind.insurance_"
---# Add Insured Items to a Commercial Quote

Add Insured Items to a Commercial Quote[](https://help.salesforce.com/s?language=en_US)

You are here:

1.  [Salesforce Help](/s/?language=en_US)
2.  [Docs](/s/products?language=en_US)
3.  [Digital Insurance](https://help.salesforce.com/s/articleView?id=ind.insurance_admin_standard.htm&language=en_US&type=5)

# Add Insured Items to a Commercial Quote

You can add insured items to a commercial product in a quote to provide additional coverage.

1.  From the Quote list page, open the quote you want to add to.
2.  On the Insurance Commercial Quote LWC, click the carat on the right side of the card for the product you are adding the insured item to.
3.  From the dropdown menu, select **Add** InsuredItemName.
4.  On the **Add** InsuredItemName window, fill out the information about the item, then click **Save**.
    
    [](https://help.salesforce.com/s?language=en_US)Note
    
    Adding or editing insured items and coverages triggers optional coverage and attribute rules.
    
    The quote details appear.
    

[](https://help.salesforce.com/s?language=en_US)

The system runs the optional coverage rules.

Coverages appear under the insured item name. Any optional coverages that the rules evaluate as true include configurable attributes and a red rating amount. (The amount = 0 until you rate the product.)

[](https://help.salesforce.com/s?language=en_US)

[Add a Commercial Grandchild Insured Item to an Insured Item or Party](https://help.salesforce.com/s/articleView?id=ind.insurance_add_a_commercial_grandchild_insured_item_to_an_insured_item_or_party_613664.htm&language=en_US&type=5 "If you're working with a multi-instance insurance product with grandchild insured items, you can add a grandchild item to an existing insured item on a commercial quote.")

Did this article solve your issue?

Let us know so we can improve!

YesNo