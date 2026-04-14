---
title: "General Liability Product Model"
source: "https://help.salesforce.com/s/articleView?id=ind.insurance_general_liability_product_model_526108.htm&language=en_US&type=5"
scraped: "2026-04-14"
filter: "ind.insurance_"
---# General Liability Product Model

General Liability Product Model[](https://help.salesforce.com/s?language=en_US)

You are here:

1.  [Salesforce Help](/s/?language=en_US)
2.  [Docs](/s/products?language=en_US)
3.  [Digital Insurance](https://help.salesforce.com/s/articleView?id=ind.insurance_admin_standard.htm&language=en_US&type=5)

# General Liability Product Model

To understand how the General Liability application works, you need to figure out how the General Liability product is built.

[](https://help.salesforce.com/s?language=en_US)

The product model is like the blueprint of the application. The product model underpins all the business processes used in the General Liability line of business. To learn about the components of product models in Vlocity Insurance, see the [Insurance and Health Product Models](https://docs.vlocity.com/en/insurance-and-health-product-models.html).

Here is a high-level product model for the General Liability root product:

[](https://help.salesforce.com/s?language=en_US)

Carry on reading for a closer look into the product model components.

[](https://help.salesforce.com/s?language=en_US)

## Insured Items

The top-level insured items for the General Liability product model are:

| 
Name

 | 

Product Code

 | 

Product Type

 | 

Description

 |
| --- | --- | --- | --- |
| 

Business

 | 

business

 | 

Insured Item Spec

 | 

This item contains all the attributes from the Applicant Business Terms attribute category.

 |
| 

Location

 | 

location

 | 

Insured Item Spec

 | 

This item contains all the attributes from the Hazards and Location Terms attribute category.

 |
| 

Building

 | 

building

 | 

Insured Item Spec

 | 

This item contains attributes from the Small Building Terms attribute category.

 |

Values for these attributes are collected from the customer when they're shopping for insurance. Vlocity Insurance uses many of these attributes to rate the General Liability product.

Many of these attributes correspond to user inputs in the quote OmniScript and quote UI.

[](https://help.salesforce.com/s?language=en_US)

## Coverages

A coverage spec you create and attach to a product becomes a coverage that your users interact with in quote and policy purchase flows. They define the required and optional coverages on an insurance product.

The General Liability product model contains the following coverage specs:

| 
Coverage Spec Name

 | 

Product Code

 | 

Required/Optional

 |
| --- | --- | --- |
| 

Medical Expense

 | 

medExpense

 | 

Required

 |
| 

Property Damage

 | 

propDamage

 | 

Required

 |
| 

Bodily Injury

 | 

bodInjury

 | 

Required

 |
| 

Premise Liability

 | 

premiseLiability

 | 

Required

 |
| 

Location Coverage

 | 

locCoverage

 | 

Required

 |

Your users interact with coverages in quote and policy flows so it's important that you create them wisely. To learn more about coverage specs, see [Child Specs for Root Products](https://help.salesforce.com/s/articleView?id=ind.insurance_child_specs_for_root_products.htm&language=en_US&type=5 "Child specs are key building blocks for your product models. They're components of the root product specs that Insurance rates, quotes, sells, and administers for your customers.").

[](https://help.salesforce.com/s?language=en_US)

## Root Products

The root product spec is the container for the General Liability product models. The system uses the data stored in this product model in downstream business processes, including quoting, issuing policies, and adjudicating claims.

The root products contain a number of coverages, all of which are associated with the root product. This structure makes the General Liability product a single instance product model. This means that whenever a quote is rated out for this product, if multiple businesses are included, each has the same level of coverage.

But with this structure, we're expecting that our customers will insure only one business per policy. Within the product, you can customize your quotes by adding different coverages and modifying their respective deductibles.

To learn about how to set up root product specs, see [Root Product Specs](https://help.salesforce.com/s/articleView?id=ind.insurance_root_product_specs_605705.htm&language=en_US&type=5 "Root product specs act as the product models that Vlocity uses at runtime to generate quotes and policies.").

[](https://help.salesforce.com/s?language=en_US)

## Attributes

Some product attributes are mapped to rating inputs. Attribute data is collected during a business process like quoting and passed on to product services to calculate prices.

All the attributes used in the General Liability product models and the insured item spec, insured party spec, and coverage specs are defined in the Vlocity Attribute Designer. Attributes are arranged into Attribute Categories.

Want to see a complete list of the attributes used in the General Liability product model? See the [General Liability Attribute Catalog](https://help.salesforce.com/s/articleView?id=ind.insurance_general_liability_attribute_catalog_526235.htm&language=en_US&type=5 "We've listed all the attributes used in the General Liability application here by the category they fall under.").

In the Vlocity Attribute Designer, basic information is defined for all attributes, such as name and attribute code.

The attribute's value data type, available values, default selected value, rating status, and other specifics are configured on the insured item spec, insured party spec, coverage spec, or root product spec.

[](https://help.salesforce.com/s?language=en_US)

## Simulate Rating the Product

We've set up ratings on the **Simulate** tab on the root product spec to simulate rating the General Liability product model. If you want to figure out how we've set these up, see [General Liability Rating](https://help.salesforce.com/s/articleView?id=ind.insurance_general_liability_rating_526478.htm&language=en_US&type=5 "When we quote and endorse the General Liability products, our pricing services use the product model data, product rating procedure, and pricing formulas. The services use these components to price the coverages. The services do the following:").

Did this article solve your issue?

Let us know so we can improve!

YesNo