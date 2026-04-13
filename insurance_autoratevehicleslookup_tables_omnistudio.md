---
title: "autoRateVehiclesLookup Tables"
source: "https://help.salesforce.com/s/articleView?id=ind.insurance_autoratevehicleslookup_tables_omnistudio.htm&language=en_US&type=5"
scraped: "2026-04-13"
filter: "ind.insurance_"
---# autoRateVehiclesLookup Tables

autoRateVehiclesLookup Tables[](https://help.salesforce.com/s?language=en_US)

You are here:

1.  [Salesforce Help](/s/?language=en_US)
2.  [Docs](/s/products?language=en_US)
3.  [Digital Insurance](https://help.salesforce.com/s/articleView?id=ind.insurance_admin_standard.htm&language=en_US&type=5)

# autoRateVehiclesLookup Tables

The autoRateVehiclesLookup expression set uses lookup tables to identify ratings for your auto insurance products. You can modify these lookup tables to reflect your ratings.

To learn how to work with lookup tables, see [Lookup Tables](https://help.salesforce.com/s/articleView?id=ind.lookup_tables_when_to_use_which.htm&language=en_US&type=5).

To learn the basics about Vlocity Insurance rating procedures for pricing insurance products, see [](https://help.salesforce.com/s?language=en_US)[Rating Procedures](https://help.salesforce.com/s/articleView?id=ind.insurance_rating_procedures.htm&language=en_US&type=5 "Rating procedures are the backbone of insurance pricing. Learn how services, product models, and rating procedures work together to price insurance products.").

| 
Lookup Table Name

 | 

Description

 |
| --- | --- |
| 

autoCarAltFuel

 | 

Handles customer input that says whether a car uses alternative fuels or not.

Takes a true or false input, and returns percentage outputs.

Cars with alternative fuels rate out at lower prices than cars without.

 |
| 

autoCarBrakes

 | 

Handles customer input that says whether a car has anti-lock brakes or not.

Takes a true or false input, and returns percentage outputs.

Cars with anti-lock brakes rate out at lower prices than cars without anti-lock brakes.

 |
| 

autoCarStability

 | 

Handles customer input that says whether a car has anti-lock brakes or not.

Takes a true or false input, and returns a percentage output.

Cars with stability control rate out slightly lower than cars without it.

 |
| 

autoCarSymbol

 | 

Takes a numeric input. Returns percentage outputs.

 |
| 

autoCarTheft

 | 

Handles customer input that says whether a car has an antitheft device or not.

Takes a true or false input. Returns a percentage output.

 |
| 

autoCarValue

 | 

Takes a numeric input. Returns numeric and percentage outputs.

 |
| 

autoCarYear

 | 

Handles customer input of the car's year.

Takes a numeric input. Returns percentage outputs.

 |
| 

autoDeductCCD

 | 

Handles the deductible a customer chooses.

Takes a numeric input. Returns a percentage output.

The higher the deductible chosen, the lower the rating.

 |
| 

autoLimitBIPD

 | 

Handles limits for bodily injury and property damage a customer chooses.

Takes numeric inputs. Returns a percentage output.

 |
| 

autoLimitMED

 | 

Handles the limit a customer chooses for medical expenses.

Takes a numeric value. Returns a percentage output.

The higher the limit chosen, the higher the rating.

 |
| 

autoLimitUM

 | 

Handles the limit for uninsured motorists a customer chooses.

Takes a split numeric value. Returns a percentage output.

 |
| 

deductCOLL

 | 

Handles the deductible a customer chooses for collision coverage.

Takes a numeric value. Returns a percentage output.

 |

Did this article solve your issue?

Let us know so we can improve!

YesNo