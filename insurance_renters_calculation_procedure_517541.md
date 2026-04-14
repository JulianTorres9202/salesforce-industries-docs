---
title: "Renters Calculation Procedure"
source: "https://help.salesforce.com/s/articleView?id=ind.insurance_renters_calculation_procedure_517541.htm&language=en_US&type=5"
scraped: "2026-04-14"
filter: "ind.insurance_"
---# Renters Calculation Procedure

Renters Calculation Procedure[](https://help.salesforce.com/s?language=en_US)

You are here:

1.  [Salesforce Help](/s/?language=en_US)
2.  [Docs](/s/products?language=en_US)
3.  [Digital Insurance](https://help.salesforce.com/s/articleView?id=ind.insurance_admin_standard.htm&language=en_US&type=5)

# Renters Calculation Procedure

This calculation procedure rates all the coverages for a quote generate using the Renters root product.

[](https://help.salesforce.com/s?language=en_US)

This calculation procedure includes variables, constants, and calculation steps. Some of those calculation steps are matrix lookups that call specific calculation matrices.

[](https://help.salesforce.com/s?language=en_US)We expect that you'll create your own calculation procedure to rate coverages for your renters insurance products. You can use **propHO4RatingProcedure\_ho4** as a model, and make changes to it so you can see how calculation procedures work.

The meat of the calculation procedure is its calculation steps. Here's what each step of the **propHO4RatingProcedure\_ho4** calculation procedure does:

[](https://help.salesforce.com/s?language=en_US)

1.  Does a matrix lookup to get the base rates by county the property is in.
    
2.  Does a matrix lookup to get information about the protection measures on the property.
    
3.  Does a matrix lookup to get information about the property's burglar alarm.
    
4.  Does a matrix lookup to get information about the property's fire alarm.
    
5.  Calculates the premium for the contents (Personal Property) coverage.
    
6.  Does a matrix lookup for liability.
    
7.  Calculates the premium for the Liability coverage.
    
8.  Does a matrix lookup for medical payments.
    
9.  Calculates the premium for the Medical Payments coverage.
    
10.  Calculates the premium for the Fine Arts coverage.
     
11.  Calculates the premium for the Bike coverage.
     
12.  Calculates the premium for the Camera coverage.
     
13.  Calculates the premium for the Musical Equipment coverage.
     
14.  Calculates the premium for the Jewelry coverage.
     
15.  Calculates the total premium for the Scheduled Items.
     
16.  Does a matrix lookup for loss of use.
     

[](https://help.salesforce.com/s?language=en_US)

## Calculation Matrices

The following calculation matrices are called by **propHO4RatingProcedure\_ho4**:

| 
Calculation Matrix Name

 | 

Description

 |
| --- | --- |
| 

**propFLCountyBaseRates\_ho4**

 | 

Handles the location of the property within the state of Florida.

Takes a text input and returns text and numeric outputs.

 |
| 

**propProtectionClassFactors\_ho3**

 | 

Handles information about how the home is built to withstand damage.

Takes numeric and text inputs and returns percentage outputs.

 |
| 

**propBurglarAlarmFactors\_ho3**

 | 

Handles whether and what type of burglar alarm a property has.

Takes a text input and returns a percentage output.

 |
| 

**propFireAlarmFactors\_ho3**

 | 

Handles whether and what type of fire alarms the property has.

Takes a text input and returns a percentage output.

 |
| 

**propLiabilityAdditionalPremium\_ho3**

 | 

Handles information that affects the liability coverage premium.

Takes text and numeric inputs and returns a numeric output.

 |
| 

**propMedPayAdditionalPremium\_ho3**

 | 

Handles the amount the customer specifies for the medical payment coverage.

Takes a numeric input and returns a numeric output.

 |
| 

**propLossOfUseFactors\_ho4**

 | 

Handles the amount of loss-of-use coverage the customer wants for the property.

Takes a numeric input and returns a numeric output.

 |

Did this article solve your issue?

Let us know so we can improve!

YesNo