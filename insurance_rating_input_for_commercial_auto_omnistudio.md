---
title: "Rating Input for Commercial Auto"
source: "https://help.salesforce.com/s/articleView?id=ind.insurance_rating_input_for_commercial_auto_omnistudio.htm&language=en_US&type=5"
scraped: "2026-04-14"
filter: "ind.insurance_"
---# Rating Input for Commercial Auto

Rating Input for Commercial Auto[](https://help.salesforce.com/s?language=en_US)

You are here:

1.  [Salesforce Help](/s/?language=en_US)
2.  [Docs](/s/products?language=en_US)
3.  [Digital Insurance](https://help.salesforce.com/s/articleView?id=ind.insurance_admin_standard.htm&language=en_US&type=5)

# Rating Input for Commercial Auto

To understand the construction of the rating procedure, you need to understand the form of the input data passed into the procedure. The Commercial Auto product includes a Vehicle insured item spec as the primary multi-instance item that auto policies will insure. You can create quotes for multiple vehicles.

The Driver insured party spec is a child of the Vehicle Insured Item spec, which lets a vehicle have multiple drivers.

All coverages in the model are children of the Vehicle insured item spec. This way, each vehicle quoted can have its own separately configured coverages.

Did this article solve your issue?

Let us know so we can improve!

YesNo