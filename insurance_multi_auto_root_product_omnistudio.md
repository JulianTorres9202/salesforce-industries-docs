---
title: "Multi Auto Root Product"
source: "https://help.salesforce.com/s/articleView?id=ind.insurance_multi_auto_root_product_omnistudio.htm&language=en_US&type=5"
scraped: "2026-04-14"
filter: "ind.insurance_"
---# Multi Auto Root Product

Multi Auto Root Product[](https://help.salesforce.com/s?language=en_US)

You are here:

1.  [Salesforce Help](/s/?language=en_US)
2.  [Docs](/s/products?language=en_US)
3.  [Digital Insurance](https://help.salesforce.com/s/articleView?id=ind.insurance_admin_standard.htm&language=en_US&type=5)

# Multi Auto Root Product

The root product spec is the container for the Multi Auto product model. The system uses the data stored in this product model in downstream business processes, including quoting, issuing policies, and adjudicating claims.

The Auto Driver insured party spec is a child of the Vehicle insured item spec, which makes Auto Driver a grandchild of the Multi Auto root product. This hierarchy creates a parent > children > grandchildren product structure. When the Multi Auto product is rated out for quoting and a policy gets issued, multiple drivers can be associated with one vehicle. The driver records are stored only once, despite being associated with multiple vehicles.

The Multi Auto root product contains a number of coverages, all of which are associated with the Vehicle insured item as a parent insured item. This structure makes Multi Auto a multi-instance product model. This means that whenever a quote is rated out for this product, each vehicle in the quote can have its own different levels of coverage.

To learn about how to set up root product specs, see [](https://help.salesforce.com/s?language=en_US)[Root Product Specs](https://help.salesforce.com/s/articleView?id=ind.insurance_root_product_specs_605705.htm&language=en_US&type=5 "Root product specs act as the product models that Vlocity uses at runtime to generate quotes and policies.").

Did this article solve your issue?

Let us know so we can improve!

YesNo