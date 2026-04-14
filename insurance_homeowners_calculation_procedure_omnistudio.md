---
title: "Homeowners Calculation Procedure"
source: "https://help.salesforce.com/s/articleView?id=ind.insurance_homeowners_calculation_procedure_omnistudio.htm&language=en_US&type=5"
scraped: "2026-04-14"
filter: "ind.insurance_"
---# Homeowners Calculation Procedure

Homeowners Calculation Procedure[](https://help.salesforce.com/s?language=en_US)

You are here:

1.  [Salesforce Help](/s/?language=en_US)
2.  [Docs](/s/products?language=en_US)
3.  [Digital Insurance](https://help.salesforce.com/s/articleView?id=ind.insurance_admin_standard.htm&language=en_US&type=5)

# Homeowners Calculation Procedure

This calculation procedure rates all the coverages for a quote generate using the Homeowners root product.

[](https://help.salesforce.com/s?language=en_US)

This calculation procedure includes variables, constants, and calculation steps. Some of those calculation steps are matrix lookups that call specific calculation matrices.

We expect that you'll create your own calculation procedure to rate your homeowners products. You can use **propHO3RatingProcedure\_ho3** as a model, and make changes to it so you can see how calculation procedures work.

[](https://help.salesforce.com/s?language=en_US)

[](https://help.salesforce.com/s?language=en_US)To learn more about creating and editing calculation procedures in general, see [Calculation Procedures and Matrices](https://help.salesforce.com/s/articleView?id=xcloud.os_calculation_procedures_and_matrices.htm&language=en_US&type=5). To learn more about Expression Sets, the replacement for calculation procedures in later releases, see [Business Rules Engine](https://help.salesforce.com/s/articleView?id=ind.business_rules_engine.htm&language=en_US&type=5).

The meat of the calculation procedure is its calculation steps. Here's what each step of the **propHO3RatingProcedure\_ho3** calculation procedure does:

1.  Does a matrix lookup to get the base rates by county the property is in.
    
2.  Does a first calculation for the AOP\_AmountCoverageFactor.
    
3.  Does a second calculation for the AOP\_AmountCoverageFactor.
    
4.  Does a third calculation for the AOP\_AmountCoverageFactor.
    
5.  Does a first calculation for the HUR\_AmountCoverageFactor.
    
6.  Does a second calculation for the HUR\_AmountCoverageFactor.
    
7.  Does a matrix lookup to get information pertaining to the year the property was built.
    
8.  Does a matrix lookup to get information about the protection measures on the property.
    
9.  Does a matrix lookup to get information about the local building codes.
    
10.  Does a matrix lookup to get information about the property's fire alarm.
     
11.  Does a matrix lookup to get information about the property's burglar alarm.
     
12.  Calculates the premium for the Dwelling coverage.
     
13.  Does a matrix lookup for other structures (besides the dwelling) on the property.
     
14.  Calculates the premium for the Other Structures coverage.
     
15.  Does a matrix lookup for personal property.
     
16.  Calculates the premium for the Personal Property coverage.
     
17.  Does a matrix lookup for sewer backup.
     
18.  Calculates the premium for Sewer backup coverage.
     
19.  Does a matrix lookup for liability.
     
20.  Calculates the premium for the Liability coverage.
     
21.  Does a matrix lookup for medical payments.
     
22.  Calculates the premium for the Medical Payments coverage.
     
23.  Does a matrix lookup for loss of use rates.
     
24.  Calculates the premium for the Loss of Use coverage.
     
25.  Does a matrix lookup for the building ordinance.
     
26.  Calculates the premium for the Building Ordinance coverage.
     
27.  Calculates the premium for the Fine Arts coverage.
     
28.  Calculates the premium for the Bike coverage.
     
29.  Calculates the premium for the Camera coverage.
     
30.  Calculates the premium for the Jewelry coverage.
     
31.  Calculates the total premium for the Scheduled Items.
     

[](https://help.salesforce.com/s?language=en_US)

## Calculation Matrices

The following calculation matrices are called by **propHO3RatingProcedure\_ho3**:

| 
Calculation Matrix Name

 | 

Description

 |
| --- | --- |
| 

**propFLCountyBaseRates\_ho3**

 | 

Handles the location of the property within the state of Florida.

Takes a text input and returns text and numeric outputs.

 |
| 

**propYearBuiltFactors\_ho3**

 | 

Handles information about the year the home was built.

Takes a numeric (year) input and returns percentage outputs.

 |
| 

**propProtectionClassFactors\_ho3**

 | 

Handles information about how the home is built to withstand damage.

Takes numeric and text inputs and returns percentage outputs.

 |
| 

**propBuildingCodeEffectivenessFactors\_ho3**

 | 

Handles the level of building code requirements met by a property.

Takes a numeric inputs and returns percentage outputs.

The lower the number of the input, the more effective the building is at withstanding natural disasters and other damage events. Thus, the lower the rating level for the building.

 |
| 

**propFireAlarmFactors\_ho3**

 | 

Handles whether and what type of fire alarms the property has.

Takes a text input and returns a percentage output.

 |
| 

**propBurglarAlarmFactors\_ho3**

 | 

Handles whether and what type of burglar alarm a property has.

Takes a text input and returns a percentage output.

 |
| 

**propOtherStructuresRateFactors\_ho3**

 | 

Handles the amount of coverage the customer specifies for other structures on the property.

Takes a percentage input and returns a percentage output.

 |
| 

**propPersonalPropertyRateFactors\_ho3**

 | 

Handles the amount of coverage the customer specifies for personal property (contents).

Takes a percentage input and returns percentage outputs.

 |
| 

**propSewerBackupAdditionalPremium\_ho3**

 | 

Handles information about optional sewer backup coverage.

Takes a numeric input and returns a numeric output.

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

**propLossOfUseFactors\_ho3**

 | 

Handles the amount of loss-of-use coverage the customer wants for the property.

Takes a percentage input and returns a percentage output.

 |
| 

**propBuildingOrdinanceFactors\_ho3**

 | 

Handles the building ordinance factors.

Take a numeric input and returns a numeric output.

 |

Did this article solve your issue?

Let us know so we can improve!

YesNo