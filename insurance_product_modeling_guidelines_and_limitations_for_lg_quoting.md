---
title: "Product Modeling Guidelines and Limitations for Large Group Quoting"
source: "https://help.salesforce.com/s/articleView?id=ind.insurance_product_modeling_guidelines_and_limitations_for_lg_quoting.htm&language=en_US&type=5"
scraped: "2026-04-14"
filter: "ind.insurance_"
---# Product Modeling Guidelines and Limitations for Large Group Quoting

Product Modeling Guidelines and Limitations for Large Group Quoting[](https://help.salesforce.com/s?language=en_US)

You are here:

1.  [Salesforce Help](/s/?language=en_US)
2.  [Docs](/s/products?language=en_US)
3.  [Digital Insurance](https://help.salesforce.com/s/articleView?id=ind.insurance_admin_standard.htm&language=en_US&type=5)

# Product Modeling Guidelines and Limitations for Large Group Quoting

An insurance product model is a structured definition of a product that a company sells, then services. A product model acts as a blueprint for an insurance product. In a group quoting scenario, a product is called a plan.

Creating plans for group quoting is similar to creating products for other types of quoting scenarios–with a few exceptions. If you're interested in learning more about the basics of product modeling, read [Build Insurance Product Models](https://help.salesforce.com/s/articleView?id=ind.insurance_insurance_and_health_product_models_603786.htm&language=en_US&type=5 "An insurance product model is a structured definition of a product that a company sells, then services. A product model acts as a blueprint for an insurance product.").

When you create a plan for group quoting, specify the Pricing Strategy Type in the product configuration. You can select either **Member Based** or **Summary Based**. Member Based products support rating at the individual member or family level. Summary Based products support rating at the group summary level.

You can rate up to 30 Summary Based plans and up to 150,000 census members at a time. With Member Based plans you can rate up to 30 plans and 3,000 members at a time. If you need to rate more than 30 plans in a quote, don’t use the Rate All Plans button. Instead, rate the first 30 plans individually by using the Rate Plan button for each plan. Wait for the rating to complete on those 30 plans, and then start rating the next set of up to 30 plans by using the Rate Plan button.

Did this article solve your issue?

Let us know so we can improve!

YesNo