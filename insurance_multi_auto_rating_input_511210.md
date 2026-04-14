---
title: "Multi Auto Rating Input"
source: "https://help.salesforce.com/s/articleView?id=ind.insurance_multi_auto_rating_input_511210.htm&language=en_US&type=5"
scraped: "2026-04-14"
filter: "ind.insurance_"
---# Multi Auto Rating Input

Multi Auto Rating Input[](https://help.salesforce.com/s?language=en_US)

You are here:

1.  [Salesforce Help](/s/?language=en_US)
2.  [Docs](/s/products?language=en_US)
3.  [Digital Insurance](https://help.salesforce.com/s/articleView?id=ind.insurance_admin_standard.htm&language=en_US&type=5)

# Multi Auto Rating Input

To understand the construction of the rating procedure, you need to understand the form of the input data passed into the procedure. The Multi Auto product includes a Vehicle insured item spec as the primary multi-instance item that auto policies will insure. You can create quotes for multiple vehicles.

The Driver insured party spec is a child of the Vehicle Insured Item spec, which lets a vehicle have multiple drivers.

All coverages in the model are children of the Vehicle insured item spec. This way, each vehicle quoted can have its own separately configured coverages.

To learn more about this product model, see [Auto Product Model](https://help.salesforce.com/s/articleView?id=ind.insurance_auto_product_model_510402.htm&language=en_US&type=5 "The product model underpins all the business processes used in the Auto line of business. This line of business offers two products namely Multi Auto and Commercial Auto.").

Below is an example of the Multi Auto product quoted for two vehicles, a 2016 BMW 3 Series and a 2017 Honda Odyssey. This quote includes three drivers: Roger Moore, Mary Moore, and John Moore. Roger Moore and Mary Moore are drivers on the 2016 BMW 3 Series. Mary Moore and John Moore are drivers on the 2017 Honda Odyssey.

When forming the rating inputs for this multi-instance hierarchy, the service passes all the vehicle\\driver combinations to the rating procedure. In this case, the rating input data includes the four combinations below.

Each of these four sets of data includes vehicle-specific coverage attributes. Here's what the high-level input JSON structure looks like for this example:

Did this article solve your issue?

Let us know so we can improve!

YesNo