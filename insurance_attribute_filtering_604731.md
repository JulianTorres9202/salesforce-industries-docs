---
title: "Attribute Filtering"
source: "https://help.salesforce.com/s/articleView?id=ind.insurance_attribute_filtering_604731.htm&language=en_US&type=5"
scraped: "2026-04-13"
filter: "ind.insurance_"
---# Attribute Filtering

Attribute Filtering[](https://help.salesforce.com/s?language=en_US)

You are here:

1.  [Salesforce Help](/s/?language=en_US)
2.  [Docs](/s/products?language=en_US)
3.  [Digital Insurance](https://help.salesforce.com/s/articleView?id=ind.insurance_admin_standard.htm&language=en_US&type=5)

# Attribute Filtering

When you create an attribute, you select whether or not it is filterable. This choice impacts how the attribute can be found and used by other parts of Vlocity.

For both insurance products and health plans, leave Filterable checked to allow the `InsProductService:getRatedProducts` and `InsEnrollmentService:getRatedProducts` services to use this attribute to filter plans to rate and display. If you deselect this option, the services can't use this attribute to filter plans for rating and display.

For small group plans, leave Filterable checked so the Small Group UI (OmniScript) template can use this attribute to filter plans to display. If you deselect this option, the template can't use this attribute to filter plans for display.

Did this article solve your issue?

Let us know so we can improve!

YesNo