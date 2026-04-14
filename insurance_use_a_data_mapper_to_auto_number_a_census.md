---
title: "Use a Data Mapper to Auto-Number a Census"
source: "https://help.salesforce.com/s/articleView?id=ind.insurance_use_a_data_mapper_to_auto_number_a_census.htm&language=en_US&type=5"
scraped: "2026-04-14"
filter: "ind.insurance_"
---# Use a Data Mapper to Auto-Number a Census

Use a Data Mapper to Auto-Number a Census[](https://help.salesforce.com/s?language=en_US)

You are here:

1.  [Salesforce Help](/s/?language=en_US)
2.  [Docs](/s/products?language=en_US)
3.  [Digital Insurance](https://help.salesforce.com/s/articleView?id=ind.insurance_admin_standard.htm&language=en_US&type=5)

# Use a Data Mapper to Auto-Number a Census

You can also use an Omnistudio Data Mapper to auto-number census records so that they number sequentially, specific to the census object, by using a formula.

[](https://help.salesforce.com/s?language=en_US)Use this formula to auto-number census records: `'CensusNumber-'+GLOBALAUTONUMBER()`.

[](https://help.salesforce.com/s?language=en_US)The Data Mapper can then be specified in an OmniScript which references a census.

Did this article solve your issue?

Let us know so we can improve!

YesNo