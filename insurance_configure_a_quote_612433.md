---
title: "Configure a Quote"
source: "https://help.salesforce.com/s/articleView?id=ind.insurance_configure_a_quote_612433.htm&language=en_US&type=5"
scraped: "2026-04-14"
filter: "ind.insurance_"
---# Configure a Quote

Configure a Quote[](https://help.salesforce.com/s?language=en_US)

You are here:

1.  [Salesforce Help](/s/?language=en_US)
2.  [Docs](/s/products?language=en_US)
3.  [Digital Insurance](https://help.salesforce.com/s/articleView?id=ind.insurance_admin_standard.htm&language=en_US&type=5)

# Configure a Quote

Once you have created a quote, you can configure it to provide your customer with exactly the coverage they need.

Important

The state of a quote affects the changes you can make to it. For example, if a quote is **Issued**, you can't modify it because a policy has already been issued from it. Create another quote instead. Also, states in the Quote State Model can be configured to prevent certain changes. If a state is set up with **No Delete** selected, you can't remove insured items, parties, or coverages from a quote in that state. With **No Update** selected, quote line items are read-only in that state. For more information about state models, see [Overview of State Models, Transitions, Rules, and Actions](https://help.salesforce.com/s/articleView?id=ind.os_overview_of_state_modelstransitionsrulesand_actions_179897.htm&language=en_US&type=5).

-   **[Add a Product to a Quote](https://help.salesforce.com/s/articleView?id=ind.insurance_add_a_product_to_a_quote_612496.htm&language=en_US&type=5)**  
    Add a product to a quote to start configuring it. You must add a product to a quote before you can add insured items or parties.
-   **[Add Insured Items](https://help.salesforce.com/s/articleView?id=ind.insurance_add_insured_items_612518.htm&language=en_US&type=5)**  
    You can add insured items to a product in a quote to provide additional coverage.
-   **[Add a Grandchild Insured Party or Insured Item to an Insured Item](https://help.salesforce.com/s/articleView?id=ind.insurance_add_a_grandchild_insured_party_or_insured_item_to_an_insured_item_612550.htm&language=en_US&type=5)**  
    If you're working with a multi-instance insurance product with grandchild insured items or insured parties, you can add a grandchild to an existing insured item.
-   **[Modify Details and Attributes on a Grandchild Insured Party or Insured Item](https://help.salesforce.com/s/articleView?id=ind.insurance_modify_details_and_attributes_on_a_grandchild_insured_party_or_insureditem_612583.htm&language=en_US&type=5)**  
    You can modify the attributes and details of a Grandchild insured item or insured party to provide your customer with exactly the coverage they need.
-   **[Set a Primary Grandchild Insured Party or Insured Item](https://help.salesforce.com/s/articleView?id=ind.insurance_set_a_primary_grandchild_insured_party_or_insured_item_612606.htm&language=en_US&type=5)**  
    Some quotes require a primary grandchild insured item or insured party. You can set the primary insured item or insured party to give your customers just the right coverage.
-   **[Remove a Grandchild Insured Party or Insured Item from a Parent Insured Item](https://help.salesforce.com/s/articleView?id=ind.insurance_remove_a_grandchild_insured_party_or_insured_item_from_a_parent_insureditem_612627.htm&language=en_US&type=5)**  
    You can remove a grandchild insured item or insured party from a parent insured item to provide your customer with exactly the coverage they need.
-   **[Remove an Insured Item from a Quote](https://help.salesforce.com/s/articleView?id=ind.insurance_remove_an_insured_item_from_a_quote_612648.htm&language=en_US&type=5)**  
    You can remove an insured item from a quote to provide your customer with the necessary coverage when their needs change.
-   **[Add a Coverage](https://help.salesforce.com/s/articleView?id=ind.insurance_add_a_coverage_612668.htm&language=en_US&type=5)**  
    You can add a coverage to a product or insured item.
-   **[Remove a Coverage](https://help.salesforce.com/s/articleView?id=ind.insurance_remove_a_coverage_612695.htm&language=en_US&type=5)**  
    You can remove a coverage if it is no longer needed.
-   **[Change Attributes on an Existing Coverage](https://help.salesforce.com/s/articleView?id=ind.insurance_change_attributes_on_an_existing_coverage_612716.htm&language=en_US&type=5)**  
    You can change some coverage attributes based on what's available in the product model.
-   **[Change Attributes on an Existing Insured Item or Insured Party](https://help.salesforce.com/s/articleView?id=ind.insurance_change_attributes_on_an_existing_insured_item_or_insured_party_612737.htm&language=en_US&type=5)**  
    You can change some insured item attributes based on what's available in the product model.
-   **[Adjust the Total Price of a Single Root Quote](https://help.salesforce.com/s/articleView?id=ind.insurance_adjust_the_total_price_of_a_single_root_quote_612763.htm&language=en_US&type=5)**  
    With the Vlocity Manual Pricing component, users can adjust the total price of a single root quote manually. When they enter price adjustments, the quote automatically refreshes to show the adjustment amount and the updated price in real time.

Did this article solve your issue?

Let us know so we can improve!

YesNo