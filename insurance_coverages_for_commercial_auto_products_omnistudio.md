---
title: "Coverages for Commercial Auto Products"
source: "https://help.salesforce.com/s/articleView?id=ind.insurance_coverages_for_commercial_auto_products_omnistudio.htm&language=en_US&type=5"
scraped: "2026-04-14"
filter: "ind.insurance_"
---# Coverages for Commercial Auto Products

Coverages for Commercial Auto Products[](https://help.salesforce.com/s?language=en_US)

You are here:

1.  [Salesforce Help](/s/?language=en_US)
2.  [Docs](/s/products?language=en_US)
3.  [Digital Insurance](https://help.salesforce.com/s/articleView?id=ind.insurance_admin_standard.htm&language=en_US&type=5)

# Coverages for Commercial Auto Products

Coverage specs define the required and optional coverages on an insurance product. On the Product page, the Product Record Type at the top left of the page = Coverage Spec.

The Commercial Auto product model contains the following coverage specs:

To learn more about coverage specs, see [](https://help.salesforce.com/s?language=en_US)[Child Specs for Root Products](https://help.salesforce.com/s/articleView?id=ind.insurance_child_specs_for_root_products.htm&language=en_US&type=5 "Child specs are key building blocks for your product models. They're components of the root product specs that Insurance rates, quotes, sells, and administers for your customers.").

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

Did this article solve your issue?

Let us know so we can improve!

YesNo