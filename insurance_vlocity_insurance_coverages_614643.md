---
title: "Insurance Coverages"
source: "https://help.salesforce.com/s/articleView?id=ind.insurance_vlocity_insurance_coverages_614643.htm&language=en_US&type=5"
scraped: "2026-04-14"
filter: "ind.insurance_"
---# Insurance Coverages

Insurance Coverages[](https://help.salesforce.com/s?language=en_US)

You are here:

1.  [Salesforce Help](/s/?language=en_US)
2.  [Docs](/s/products?language=en_US)
3.  [Digital Insurance](https://help.salesforce.com/s/articleView?id=ind.insurance_admin_standard.htm&language=en_US&type=5)

# Insurance Coverages

Vlocity uses the root product(s) as the basis for storing coverages and creating relationships between coverages, insured items, and root products in the quote data model.

[](https://help.salesforce.com/s?language=en_US)Each coverage on a quote is stored as a separate quote line item.

[](https://help.salesforce.com/s?language=en_US)The root insurance product model contains all the insurance product information. This includes the structure Vlocity uses to create relationships between coverages and insured items, relationships between grandchild insured items and insured items, and so on.

[](https://help.salesforce.com/s?language=en_US)If a coverage applies directly to the root product on the insurance product model, the coverage's Parent Item Id and Sub Parent Item Id have the same value (the root product's quote line item Id).

[](https://help.salesforce.com/s?language=en_US)Coverage details get pulled from the coverage specs associated with the root product.

[](https://help.salesforce.com/s?language=en_US)This is a list of the insured items that contain coverages on the Coverages tab. Click the arrow on the left to open an insured item to see its coverages.

[](https://help.salesforce.com/s?language=en_US)If a specific coverage includes more data than Vlocity can show on one line, click **More** on the right of that coverage to see all the coverage's quote data.

Did this article solve your issue?

Let us know so we can improve!

YesNo