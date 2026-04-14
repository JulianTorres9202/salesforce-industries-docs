---
title: "WorkersCompensationNCCI Calculation Procedure"
source: "https://help.salesforce.com/s/articleView?id=ind.insurance_workerscompensationncci_calculation_procedure_529212.htm&language=en_US&type=5"
scraped: "2026-04-14"
filter: "ind.insurance_"
---# WorkersCompensationNCCI Calculation Procedure

WorkersCompensationNCCI Calculation Procedure[](https://help.salesforce.com/s?language=en_US)

You are here:

1.  [Salesforce Help](/s/?language=en_US)
2.  [Docs](/s/products?language=en_US)
3.  [Digital Insurance](https://help.salesforce.com/s/articleView?id=ind.insurance_admin_standard.htm&language=en_US&type=5)

# WorkersCompensationNCCI Calculation Procedure

The WorkersCompensationNCCI calculation procedure includes variables, constants, and calculation steps. Some of those calculation steps are matrix lookups that call specific calculation matrices.

[](https://help.salesforce.com/s?language=en_US)We expect that you'll create your own calculation procedure to rate your Workers Compensation products. You can use **WorkersCompensationNCCI** as an example, and make changes to this procedure so you can see how calculation procedures work.

[](https://help.salesforce.com/s?language=en_US)

[](https://help.salesforce.com/s?language=en_US)To learn more about creating and editing calculation procedures in general, see [Calculation Procedures and Matrices](https://help.salesforce.com/s/articleView?id=xcloud.os_calculation_procedures_and_matrices.htm&language=en_US&type=5). To learn more about Expression Sets, the replacement for calculation procedures in later releases, see [Business Rules Engine](https://help.salesforce.com/s/articleView?id=ind.business_rules_engine.htm&language=en_US&type=5).

[](https://help.salesforce.com/s?language=en_US)Here's what each step of the **WorkersCompensationNCCI** calculation procedure does:

[](https://help.salesforce.com/s?language=en_US)

1.  Does matrix lookups to get the rate factor and minimum amount for NCCI.
    
2.  Calculates the payroll line.
    
3.  Calculates the tentative payroll line premium amount.
    
4.  Does a matrix lookup to get the cost multiplier for any loss.
    
5.  Calculates the actual payroll line premium amount.
    
6.  Calculates the waiver of subrogation coverage amount.
    
7.  Calculates the Longshore and Harbor Workers' Compensation Act coverage amount.
    

[](https://help.salesforce.com/s?language=en_US)

## Aggregation Steps

WorkersCompensationNCCI includes aggregation steps that calculate aggregated premiums for specific coverages:

1.  Calculates the aggregate premium for Coverage A by taking the sum of final rate for payroll line premium outputs from each run of the calculation steps.
    
2.  Calculates the aggregate premium for waiver of subrogation by taking the sum of final rate for waiver of subrogation outputs from each run of the calculation steps.
    
3.  Calculates the aggregate premium for Longshore and Harbor Workers' Compensation Act coverage by taking the sum of final rate for Longshore and Harbor Workers' Compensation Act coverage outputs from each run of the calculation steps.
    

Did this article solve your issue?

Let us know so we can improve!

YesNo