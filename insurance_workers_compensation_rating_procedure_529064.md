---
title: "Workers Compensation Rating Procedure"
source: "https://help.salesforce.com/s/articleView?id=ind.insurance_workers_compensation_rating_procedure_529064.htm&language=en_US&type=5"
scraped: "2026-04-14"
filter: "ind.insurance_"
---# Workers Compensation Rating Procedure

Workers Compensation Rating Procedure[](https://help.salesforce.com/s?language=en_US)

You are here:

1.  [Salesforce Help](/s/?language=en_US)
2.  [Docs](/s/products?language=en_US)
3.  [Digital Insurance](https://help.salesforce.com/s/articleView?id=ind.insurance_admin_standard.htm&language=en_US&type=5)

# Workers Compensation Rating Procedure

A rating is a risk-based calculation of a premium based on a set of input characteristics. We use rating procedures to price insurance products and health plans. You'll set up, map, and implement rating procedures for all your products and plans.

Each insurer defines how they will calculate prices for their insurance products. This rating procedure provides one realistic example for calculating workers compensation insurance product prices. You can use our example as a guide while you decide how to create your own rating procedure.

[](https://help.salesforce.com/s?language=en_US)

To learn the basics about Vlocity Insurance rating procedures for pricing insurance products, see Rating Procedures.

[](https://help.salesforce.com/s?language=en_US)

## Integration Procedure for Workers Compensation

To rate the Workers Compensation insurance product, we use this Integration procedure:

[](https://help.salesforce.com/s?language=en_US)

-   Type/Subtype - insRating/WorkersCompensationNCCi
    
-   Integration Procedure Name - WorkersCompensationNCCIRating
    

Here are details of what each component in the Integration Procedure does:

| 
Component Name

 | 

Component Type

 | 

What It Does

 | 

What It Calls

 |
| --- | --- | --- | --- |
| 

RatePayrollLinesAction

 | 

Calculation Action

 | 

It uses the service **PricingMatrixCalculationService** to calculate the payroll.

 | 

WorkersCompensationNCCI

 |
| 

addLocationInstanceKeyForSingle

 | 

Set Values

 | 

For a single input, this component sets the premium.

 | 

None

 |
| 

MultipleInputsNoMerge

 | 

Set Values

 | 

For a multiple inputs, this component sets the different premiums.

 | 

None

 |
| 

SingleInputDoMerge

 | 

Set Values

 | 

Merges the results for a single input.

 | 

None

 |
| 

RollUpCoverageAmounts

 | 

Set Values

 | 

Sets the sum of all coverage amounts.

 | 

None

 |
| 

MergeInputsForCoverageB

 | 

List Action

 | 

Arranges Coverage B values in order.

 | 

None

 |
| 

MergeInputs

 | 

Set Values

 | 

Arranges all inputs in an order.

 | 

None

 |
| 

RateCoverageBAndFinal

 | 

Calculation Action

 | 

It uses the service **PricingMatrixCalculationService** to calculate liability and schedule.

 | 

WorkersCompensationLiabilityAndSchedule

 |
| 

MergeRatingResults

 | 

Omnistudio Data Mapper Transform Action

 | 

Merges coverage premiums for different locations.

 | 

Ins\_transRatingWorkerComp\_IP

 |
| 

MergeInProductKeys

 | 

List Action

 | 

Merges the product keys for different locations.

 | 

None

 |
| 

transformOptionalPremium

 | 

Data Mapper Transform Action

 | 

Transforms the data for the optional premiums.

 | 

Ins\_TransWcOptionalPremiums\_RatingIP

 |
| 

SetOutput

 | 

Set Values

 | 

Arranges the output premium values in an order.

 | 

None

 |

The Workers Compensation rating procedure also uses calculation procedures to perform a series of calculations on matrix lookups and user-defined variables and constants. A calculation matrix is a table that looks up information using multiple input dimensions and returns the corresponding output value. The Workers Compensation Integration Procedure calls these calculation procedures:

-   [WorkersCompensationNCCI](https://help.salesforce.com/s/articleView?id=ind.insurance_workerscompensationncci_calculation_procedure_529212.htm&language=en_US&type=5 "The WorkersCompensationNCCI calculation procedure includes variables, constants, and calculation steps. Some of those calculation steps are matrix lookups that call specific calculation matrices.")
    
    Calculates the premiums for payroll.
    
-   [WorkersCompensationLiabilityAndSchedule](https://help.salesforce.com/s/articleView?id=ind.insurance_workerscompensationliabilityandschedule_calculation_procedure_529247.htm&language=en_US&type=5 "The WorkersCompensationLiabilityAndSchedule calculation procedure does this")
    
    Calculates the premium for liability and schedule.
    

-   **[WorkersCompensationNCCI Calculation Procedure](https://help.salesforce.com/s/articleView?id=ind.insurance_workerscompensationncci_calculation_procedure_529212.htm&language=en_US&type=5)**  
    The WorkersCompensationNCCI calculation procedure includes variables, constants, and calculation steps. Some of those calculation steps are matrix lookups that call specific calculation matrices.
-   **[WorkersCompensationLiabilityAndSchedule Calculation Procedure](https://help.salesforce.com/s/articleView?id=ind.insurance_workerscompensationliabilityandschedule_calculation_procedure_529247.htm&language=en_US&type=5)**  
    The WorkersCompensationLiabilityAndSchedule calculation procedure does this

Did this article solve your issue?

Let us know so we can improve!

YesNo