---
title: "Commercial Auto Product Model"
source: "https://help.salesforce.com/s/articleView?id=ind.insurance_commercial_auto_product_model_526841.htm&language=en_US&type=5"
scraped: "2026-04-14"
filter: "ind.insurance_"
---# Commercial Auto Product Model

Commercial Auto Product Model[](https://help.salesforce.com/s?language=en_US)

You are here:

1.  [Salesforce Help](/s/?language=en_US)
2.  [Docs](/s/products?language=en_US)
3.  [Digital Insurance](https://help.salesforce.com/s/articleView?id=ind.insurance_admin_standard.htm&language=en_US&type=5)

# Commercial Auto Product Model

The Commercial Auto product is a single-instance product model that lets businesses create quotes for multiple vehicles that are tied to a single location.

[](https://help.salesforce.com/s?language=en_US)

## Insured Items

The insured items in Commercial Auto product are:

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

Vehicle

 | 

autoVehicle

 | 

Insured Item Spec

 | 

This item contains attributes from the Auto Vehicle attribute category.

 |

To learn more about insured item specs, see [Child Specs for Root Products](https://help.salesforce.com/s/articleView?id=ind.insurance_child_specs_for_root_products.htm&language=en_US&type=5 "Child specs are key building blocks for your product models. They're components of the root product specs that Insurance rates, quotes, sells, and administers for your customers.").

[](https://help.salesforce.com/s?language=en_US)

## Coverages

Coverage specs define the required and optional coverages on an insurance product. On the Product page, the Product Record Type at the top left of the page = Coverage Spec.

The Commercial Auto product model contains the following coverage specs:

| 
Coverage Spec Name

 | 

Product Code

 | 

Configuration

 |
| --- | --- | --- |
| 

Collision

 | 

autoCollision

 | 

Contains the Collision Deductible power attribute, configured with **Currency Dropdown** values.

 |
| 

Comprehensive

 | 

autoComp

 | 

Contains the Comp Deductible power attribute, configured with **Currency Dropdown** values.

 |
| 

Medical Payments

 | 

autoMedical

 | 

Contains the Med Pay Person Limit power attribute, configured with **Currency Dropdown** values.

 |
| 

Uninsured Motorist

 | 

autoUM

 | 

Contains the UM Limit power attribute, configured as a **Picklist Dropdown**.

 |
| 

Bodily Injury & Property Damage

 | 

autoBIPD

 | 

Contains the BIPD Limit power attribute, set up as a **Multivalue Picklist** with a list of split-limit values.

 |

To learn more about coverage specs, see [Child Specs for Root Products](https://help.salesforce.com/s/articleView?id=ind.insurance_child_specs_for_root_products.htm&language=en_US&type=5 "Child specs are key building blocks for your product models. They're components of the root product specs that Insurance rates, quotes, sells, and administers for your customers.").

[](https://help.salesforce.com/s?language=en_US)

## Commercial Auto Root Product

The root product spec is the container for the Commercial Auto product model. The system uses the data stored in this product model in downstream business processes, including quoting, and issuing policies.

The Vehicle insured item spec is a child of the Location insured item spec, which makes Vehicle a grandchild of the Commercial Auto root product. This hierarchy creates a parent > children > grandchildren product structure. When the Commercial Auto product is rated out for quoting and a policy gets issued, multiple vehicles can be associated with one location. The vehicle records are stored only once, despite being associated with multiple locations.

The Commercial Auto root product contains a number of coverages, all of which are associated with the Location insured item as a parent insured item. This structure makes Commercial Auto a multi-instance product model. This means that whenever a quote is rated out for this product, each location in the quote can have its own different levels of coverage.

To learn about how to set up root product specs, see [Root Product Specs](https://help.salesforce.com/s/articleView?id=ind.insurance_root_product_specs_605705.htm&language=en_US&type=5 "Root product specs act as the product models that Vlocity uses at runtime to generate quotes and policies.").

[](https://help.salesforce.com/s?language=en_US)

## Attributes

All the attributes used in the CommercialAuto insurance product and the insured item spec, insured party spec, and coverage specs are defined in the Vlocity Attribute Designer. Attributes are arranged into Attribute Categories.

Want to see a complete list of the attributes used in the Multi Auto product model? Visit the [Auto Attribute Catalog](https://help.salesforce.com/s/articleView?id=ind.insurance_auto_attribute_catalog.htm&language=en_US&type=5 "In this catalog, all attributes used for the Auto line of business are listed by Attribute Category. Each Attribute Category has its own table, which includes attribute codes and the product specs the attributes are used by.").

In the Vlocity Attribute Designer, basic information is defined for all attributes, such as name and attribute code.

For specific limit and deductible attributes that we use to describe policy terms, more information is defined:

-   Attribute Class
    
-   Attribute Scope
    
-   Applicable Actions
    
-   Applicable Item
    
-   Value Type
    

Attributes that have these fields set are called power attributes. Power attributes are defined for policy terms so that the claims system can track them.

To learn more about power attributes, including when to use them and how to set them up, see [Policy Terms as Power Attributes](https://help.salesforce.com/s/articleView?id=ind.insurance_policy_terms_as_power_attributes_617749.htm&language=en_US&type=5 "Enforce policy terms such as limits and deductibles by using power attributes. The \"power\" in power attributes comes from the extra metadata that you can configure for them. Insurance uses this metadata to track attributes as policy terms, from the product model to the policy record, and then on to claims against the policy.").

[](https://help.salesforce.com/s?language=en_US)

## Simulate Rating

The Simulate tab on the root product spec has the ratings set up to simulate rating the Multi Auto product model. To learn about this setup, see [Auto Rating](https://help.salesforce.com/s/articleView?id=ind.insurance_auto_rating_511129.htm&language=en_US&type=5 "When we quote and endorse Auto products, our pricing services use the product model data, product rating procedure, and pricing formulas. The services use these components to price the coverages, vehicles, and total premium.  The service does the following to price the product:").

Did this article solve your issue?

Let us know so we can improve!

YesNo