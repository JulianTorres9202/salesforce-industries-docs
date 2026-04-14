---
title: "Insurance Insured Items"
source: "https://help.salesforce.com/s/articleView?id=ind.insurance_vlocity_insurance_insured_items_614670.htm&language=en_US&type=5"
scraped: "2026-04-14"
filter: "ind.insurance_"
---# Insurance Insured Items

Insurance Insured Items[](https://help.salesforce.com/s?language=en_US)

You are here:

1.  [Salesforce Help](/s/?language=en_US)
2.  [Docs](/s/products?language=en_US)
3.  [Digital Insurance](https://help.salesforce.com/s/articleView?id=ind.insurance_admin_standard.htm&language=en_US&type=5)

# Insurance Insured Items

The insured item data in the quote gets pulled from the insured item specs associated with the root product that's been quoted.

[](https://help.salesforce.com/s?language=en_US)Each insured item on a quote is stored as a separate quote line item.

[](https://help.salesforce.com/s?language=en_US)Vlocity uses the root product(s) as the basis for storing coverages and creating relationships between coverages, insured items, insured parties, and root products in the quote data model.

[](https://help.salesforce.com/s?language=en_US)The root insurance product model contains all the insurance product information. This includes the structure Vlocity uses to create relationships between coverages and insured items, relationships between grandchild insured items and insured items, and so on.

[](https://help.salesforce.com/s?language=en_US)If an insured item applies directly to the root product on the root insurance product model, the Parent Item Id and Sub Parent Item Id contain the same value (the root product's quote line item Id).

[](https://help.salesforce.com/s?language=en_US)The insured item details come from the insured item specs associated with the root product.

[](https://help.salesforce.com/s?language=en_US)To modify any insured item on this quote, click the **Edit** button at the top right of the insured item's section.

Did this article solve your issue?

Let us know so we can improve!

YesNo