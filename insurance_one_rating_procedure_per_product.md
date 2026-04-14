---
title: "One Rating Procedure per Product for getRatedProducts"
source: "https://help.salesforce.com/s/articleView?id=ind.insurance_one_rating_procedure_per_product.htm&language=en_US&type=5"
scraped: "2026-04-14"
filter: "ind.insurance_"
---# One Rating Procedure per Product for getRatedProducts

One Rating Procedure per Product for getRatedProducts[](https://help.salesforce.com/s?language=en_US)

You are here:

1.  [Salesforce Help](/s/?language=en_US)
2.  [Docs](/s/products?language=en_US)
3.  [Digital Insurance](https://help.salesforce.com/s/articleView?id=ind.insurance_admin_standard.htm&language=en_US&type=5)

# One Rating Procedure per Product for getRatedProducts

Format `InsProductService:getRatedProducts userInputs` for products that use a single rating procedure per root product.

Note

For most products that use multiple rating procedures in the product hierarchy or multiple specs in any level of the hierarchy, you format input JSON differently. See [Multiple Rating Procedures per Product or Multiple Specs at Any Level for getRatedProducts](https://help.salesforce.com/s/articleView?id=ind.insurance_multiple_rating_procedures_per_product_or_multiple_specs_at_any_level.htm&language=en_US&type=5 "Format InsProductService:getRatedProducts userInputs for products that use multiple rating procedures in the product hierarchy or multiple child specs in any level of the hierarchy.").

Products configured before Winter '23 release 240.22 can have multiple child specs in a given level of the hierarchy, no grandchild specs, and only one rating procedure at the root level. For these products, use the same `userInputs` format as you did in earlier releases.

To prevent errors, run the service with only one type of `userInputs` format at a time.

`InsProductService: getRatedProducts` looks for a `userInputs` key in the input JSON. This object contains the inputs needed by the rating procedure as mapped in the attributes of the product, including its associated coverage specs, insured item specs, insured party specs, and rating fact specs. This object also includes all input parameters needed by the rating procedure to do its calculations. If attributes mapped for rating aren't included in the object, the service uses defaults set by the product administrator.

For any product, you can get the target format for the `userInputs` object from the service listing in the API tab of the product view. You can copy this JSON in a transform Data Mapper to transform user inputs to the desired format for rating. The object keys are in the form `"<ProductCode>.<AttributeCode>"` where the ProductCode is the code of the product or the product code of associated coverage specs, insured item specs, or rating facts.

For example, a business owner's policy typically rates an insured item, the property, for its property coverage. This example uses the property coverage product code `busProperty`.

```json
{
  "userInputs": {
    "busProperty.ageBusiness": 10,
    "busProperty.yearWiring": 2000,
    "busProperty.yearRoof": 2000,
    "busProperty.yearPlumbing": 2000,
    "busProperty.yearBusiness": 2000,
    "busProperty.yearBuilding": 2000,
    "busProperty.bldgSprinker": true,
    "busProperty.SIC": "5251",
    "busProperty.protectionClass": 4,
    "busProperty.bldgFrame": "Superior",
    "busProperty.bldgAlarm": "Central",
    "busProperty.ageBuilding": 40
  }
```

Note

An alternate approach is to define a Data Mapper transform that maps the data that's passed into the input JSON into the form the service needs. This Data Mapper's output JSON is the `userInputs` JSON defined in the product view API tab. To set up the service to use the Data Mapper, set the `preTransformBundle` option to the name of the Data Mapper.

Did this article solve your issue?

Let us know so we can improve!

YesNo