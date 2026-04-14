---
title: "Coverages in Auto Claims Products"
source: "https://help.salesforce.com/s/articleView?id=ind.insurance_coverages_in_auto_claims_products_omnistudio.htm&language=en_US&type=5"
scraped: "2026-04-14"
filter: "ind.insurance_"
---# Coverages in Auto Claims Products

Coverages in Auto Claims Products[](https://help.salesforce.com/s?language=en_US)

You are here:

1.  [Salesforce Help](/s/?language=en_US)
2.  [Docs](/s/products?language=en_US)
3.  [Digital Insurance](https://help.salesforce.com/s/articleView?id=ind.insurance_admin_standard.htm&language=en_US&type=5)

# Coverages in Auto Claims Products

Coverage specs define the coverages that can be handled by this claim product. On the Product page, the Product Record Type at the top left of the page = Coverage Spec.

All the coverage specs on the Auto Claims product model are the same as those on the Auto Claims Product Model as explained earlier.

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

Rental Car

 | 

autoRental

 | 

Contains the Rental Limit power attribute with a **Currency** value set to 2000.

Contains the Number of Days power attribute with a **Number** value set to 30.

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