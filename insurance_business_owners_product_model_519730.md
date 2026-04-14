---
title: "Business Owners Product Model"
source: "https://help.salesforce.com/s/articleView?id=ind.insurance_business_owners_product_model_519730.htm&language=en_US&type=5"
scraped: "2026-04-14"
filter: "ind.insurance_"
---# Business Owners Product Model

Business Owners Product Model[](https://help.salesforce.com/s?language=en_US)

You are here:

1.  [Salesforce Help](/s/?language=en_US)
2.  [Docs](/s/products?language=en_US)
3.  [Digital Insurance](https://help.salesforce.com/s/articleView?id=ind.insurance_admin_standard.htm&language=en_US&type=5)

# Business Owners Product Model

To understand how the Business Owners' application works, you need to figure out how it's built. Read on to understand the Business Owners' product model.

The Business Owners line of business offers these products:

-   Economy Business
    
-   Superior Business
    

The Superior Business product offers more coverages and deductibles than the Economy Business product. The Essential Business product is for commercial lines and lets you insure people as well as products.

The product model is like the blueprint of the application. The product model underpins all the business processes used in the Business Owners line of business. To learn about the components of product models in Vlocity Insurance, see the [Insurance and Health Product Models](https://help.salesforce.com/s/articleView?id=ind.insurance_insurance_and_health_product_models_603786.htm&language=en_US&type=5 "An insurance product model is a structured definition of a product that a company sells, then services. A product model acts as a blueprint for an insurance product.").

Here is a high-level product model for both the Economy Business and Superior Business root products. Here, the Business Owners Root Product can be either Economy Business or Superior Business.

[](https://help.salesforce.com/s?language=en_US)

Carry on reading for a closer look into the product model components.

[](https://help.salesforce.com/s?language=en_US)

## Insured Items

The top-level insured items for the Business Owners product model are:

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

smallBusiness

 | 

smallBusiness

 | 

Insured Item Spec

 | 

This item contains all the attributes from the Small Business attribute category.

 |
| 

BusinessOwner

 | 

BusOwner

 | 

Insured Party Spec

 | 

This item contains all the attributes from the Business Owner attribute category.

 |
| 

InsuredBusiness

 | 

InsuredBus

 | 

Insured Item Spec

 | 

This item contains attributes from the Small Business attribute category.

 |
| 

BusinessLocation

 | 

BusLocation

 | 

Insured Item Spec

 | 

This item contains attributes from the Small Business and Property Location attribute category.

 |

Values for these attributes are collected from the customer when they're shopping for insurance. Vlocity Insurance uses many of these attributes to rate the Business Owners product.

Many of these attributes correspond to user inputs in the quote OmniScript and quote UI.

[](https://help.salesforce.com/s?language=en_US)

## Coverages

A coverage spec you create and attach to a product becomes a coverage that your users interact with in quote and policy purchase flows. They define the required and optional coverages on an insurance product.

Note

The Superior Business, Economy Business, and Essential Business product models use the same coverage specs.

The Business Owners product model contains the following coverage specs:

| 
Coverage Spec Name

 | 

Product Code

 | 

Required/Optional

 |
| --- | --- | --- |
| 

Business Property

 | 

bop-BP

 | 

Required

 |
| 

General Liability

 | 

bop-GL

 | 

Required

 |
| 

Tenants Liability

 | 

bop-TL

 | 

Required

 |
| 

Accounts Receivable

 | 

bop-AR

 | 

Optional for Economy Business and Superior Business

Required for Essential Business

 |
| 

Rental Cars

 | 

bop-RentCar

 | 

Optional

 |
| 

Employee Fraud

 | 

bop-EF

 | 

Optional for Economy Business and Superior Business

Required for Essential Business

 |
| 

Electronic Media

 | 

bop-EM

 | 

Optional

 |
| 

Employee Auto Liability

 | 

bop-EmpAuto

 | 

Optional

 |
| 

Valuable Papers

 | 

bop-VP

 | 

Optional

 |
| 

Signage

 | 

bop-Signage

 | 

Optional

 |

Your users interact with coverages in quote and policy flows so it's important that you create them wisely. To learn more about coverage specs, see [Child Specs for Root Products](https://help.salesforce.com/s/articleView?id=ind.insurance_child_specs_for_root_products.htm&language=en_US&type=5 "Child specs are key building blocks for your product models. They're components of the root product specs that Insurance rates, quotes, sells, and administers for your customers.").

[](https://help.salesforce.com/s?language=en_US)

## Root Products

The root product spec is the container for the Superior Business, Economy Business, and Essential Business product models. The system uses the data stored in this product model in downstream business processes, including quoting, issuing policies, and adjudicating claims.

Both the Superior Business, Economy Business, and Essential Business root product spec are structured the same way.

The root products contain a number of coverages, all of which are associated with the root product. This structure makes the Superior Business, Economy Business, and Essential Business products single instance product models. This means that whenever a quote is rated out for this product, if multiple businesses are included, each has the same level of coverage.

But with this structure, we're expecting that our customers will insure only one business per policy. Within the product, you can customize your quotes by adding different coverages and modifying their respective deductibles.

To learn about how to set up root product specs, see [Root Product Specs](https://help.salesforce.com/s/articleView?id=ind.insurance_root_product_specs_605705.htm&language=en_US&type=5 "Root product specs act as the product models that Vlocity uses at runtime to generate quotes and policies.").

[](https://help.salesforce.com/s?language=en_US)

## Attributes

Some product attributes are mapped to rating inputs. Attribute data is collected during a business process like quoting and passed on to product services to calculate prices.

All the attributes used in the Superior Business and Economy Business product models and the insured item spec, insured party spec, and coverage specs are defined in the Vlocity Attribute Designer. Attributes are arranged into Attribute Categories.

Want to see a complete list of the attributes used in the Superior Business and Economy Business product models? See the [Business Owners Attribute Catalog](https://help.salesforce.com/s/articleView?id=ind.insurance_business_owners_attribute_catalog.htm&language=en_US&type=5 "We've listed all the attributes used in the Business Owners application here by the category they fall under.").

In the Vlocity Attribute Designer, basic information is defined for all attributes, such as name and attribute code.

The attribute's value data type, available values, default selected value, rating status, and other specifics are configured on the insured item spec, insured party spec, coverage spec, or root product spec.

[](https://help.salesforce.com/s?language=en_US)

## Simulate Rating the Product

We've set up ratings on the **Simulate** tab on the root product spec to simulate rating the Economy Business, Superior Business, and Essential Business product models. If you want to figure out how we've set these up, see [Business Owners Rating](https://help.salesforce.com/s/articleView?id=ind.insurance_business_owners_rating_520335.htm&language=en_US&type=5 "When we quote and endorse the Business Owners Policy products, our pricing services use the product model data, product rating procedure, and pricing formulas. The services use these components to price the coverages. The services do the following:").

-   **[Business Owners Attribute Catalog](https://help.salesforce.com/s/articleView?id=ind.insurance_business_owners_attribute_catalog.htm&language=en_US&type=5)**  
    We've listed all the attributes used in the Business Owners application here by the category they fall under.

Did this article solve your issue?

Let us know so we can improve!

YesNo