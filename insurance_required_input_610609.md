---
title: "Required Input in a Rating Integration Procedure"
source: "https://help.salesforce.com/s/articleView?id=ind.insurance_required_input_610609.htm&language=en_US&type=5"
scraped: "2026-04-14"
filter: "ind.insurance_"
---# Required Input in a Rating Integration Procedure

Required Input in a Rating Integration Procedure[](https://help.salesforce.com/s?language=en_US)

You are here:

1.  [Salesforce Help](/s/?language=en_US)
2.  [Docs](/s/products?language=en_US)
3.  [Digital Insurance](https://help.salesforce.com/s/articleView?id=ind.insurance_admin_standard.htm&language=en_US&type=5)

# Required Input in a Rating Integration Procedure

Each input JSON node in a rating Integration Procedure must include `parentProdKey` and `productKey`. These two keys carry over as input to the expression sets called by this Integration Procedure.

Also, the input variables coming into the Integration Procedure need to map correctly to the input variables of the expression set that this Integration Procedure calls in the calculation step. The expression set needs these input variables to run correctly.

Fun fact: expression set input variables don't correspond directly to attributes on a product model. Instead, they correspond to the Rating Input Mapping that's configured on the attribute in the product model.

Now let's look at an example that shows the flow from product model to expression set to Integration Procedure.

Here's a product model. In it, the `Value` (**Attribute Code** = `avValue`) has the **Rating Input Mapping** set to `carValue`.

This is how this input variable appears in an expression set.

And here's the input JSON for the Integration Procedure that calls the expression set, with the carValue input variable and the required parentProdKey and productKey highlighted. Both of these required keys must be carried over to the output JSON.

Did this article solve your issue?

Let us know so we can improve!

YesNo