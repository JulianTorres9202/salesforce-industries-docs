---
title: "Data Transforms in a Rating Integration Procedure"
source: "https://help.salesforce.com/s/articleView?id=ind.insurance_data_transforms_610698.htm&language=en_US&type=5"
scraped: "2026-04-14"
filter: "ind.insurance_"
---# Data Transforms in a Rating Integration Procedure

Data Transforms in a Rating Integration Procedure[](https://help.salesforce.com/s?language=en_US)

You are here:

1.  [Salesforce Help](/s/?language=en_US)
2.  [Docs](/s/products?language=en_US)
3.  [Digital Insurance](https://help.salesforce.com/s/articleView?id=ind.insurance_admin_standard.htm&language=en_US&type=5)

# Data Transforms in a Rating Integration Procedure

Transform data if necessary based on the format of the input JSON and the format of the results of the expression set or external rating engine.

[](https://help.salesforce.com/s?language=en_US)

1.  Create one or more Omnistudio Data Mappers to transform the data.
2.  In the rating Integration Procedure, call a Data Mapper using a Data Mapper Transform Action.

## Merge Lists

For multi-instance products, that is, insurance products that can rate more than one instance of an insured item in the same rating procedure—you can add a List Action to the Integration Procedure.

Did this article solve your issue?

Let us know so we can improve!

YesNo