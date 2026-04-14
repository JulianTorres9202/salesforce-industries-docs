---
title: "General Liability Calculation Procedure"
source: "https://help.salesforce.com/s/articleView?id=ind.insurance_general_liability_calculation_procedure_526547.htm&language=en_US&type=5"
scraped: "2026-04-14"
filter: "ind.insurance_"
---# General Liability Calculation Procedure

General Liability Calculation Procedure[](https://help.salesforce.com/s?language=en_US)

You are here:

1.  [Salesforce Help](/s/?language=en_US)
2.  [Docs](/s/products?language=en_US)
3.  [Digital Insurance](https://help.salesforce.com/s/articleView?id=ind.insurance_admin_standard.htm&language=en_US&type=5)

# General Liability Calculation Procedure

The General Liability calculation procedure rates all the coverages for the quote. This calculation procedure includes variables, constants, and calculation steps. Some of those calculation steps are matrix lookups that call specific calculation matrices.

[](https://help.salesforce.com/s?language=en_US)We expect that you'll create your own calculation procedure to rate your general liability products. You can use **RateGeneralLiability** as an example, and make changes to this procedure so you can see how calculation procedures work.

[](https://help.salesforce.com/s?language=en_US)

[](https://help.salesforce.com/s?language=en_US)To learn more about creating and editing calculation procedures in general, see [Calculation Procedures and Matrices](https://help.salesforce.com/s/articleView?id=xcloud.os_calculation_procedures_and_matrices.htm&language=en_US&type=5). To learn more about Expression Sets, the replacement for calculation procedures in later releases, see [Business Rules Engine](https://help.salesforce.com/s/articleView?id=ind.business_rules_engine.htm&language=en_US&type=5).

[](https://help.salesforce.com/s?language=en_US)The meat of the calculation procedure is its calculation steps. Here's what each step of the **RateGeneralLiability** calculation procedure does:

[](https://help.salesforce.com/s?language=en_US)

1.  Does matrix lookups to get the liability rate of the premises.
    
2.  Does matrix lookups to get the property damage rate.
    
3.  Does matrix lookups to get the medical expense rate.
    
4.  Does matrix lookups to get the bodily injury rate.
    
5.  Does matrix lookups to get the deductible per occurrence of property damage.
    
6.  Does matrix lookups to get the deductible per claim of bodily injury.
    
7.  Does matrix lookups to get the per claim limit for property damage.
    
8.  Does matrix lookups to get the per claim limit for bodily injury.
    
9.  Does matrix lookups to get the per claim deductible for property damage.
    
10.  Does matrix lookups to get the per claim deductible for bodily injury.
     
11.  Does matrix lookups to get the liability medical rate for the location.
     
12.  Does matrix lookups to get the liability rate for the location.
     
13.  Does matrix lookups to get the coverage based on medical expense.
     
14.  Does matrix lookups to get the aggregated limit for medical expense.
     
15.  Calculates the final rate for medical expense.
     
16.  Calculates the final rate for property damage.
     
17.  Does matrix lookups to get the claim limit for bodily injury.
     
18.  Does matrix lookups to get the claim deductible for bodily injury.
     
19.  Calculates the final rate for premise liability.
     
20.  Calculates the final rate for bodily injury.
     
21.  Calculates the final rate for location liability.
     
22.  Calculates the General Liability premium.
     

[](https://help.salesforce.com/s?language=en_US)

## Aggregation Steps

RateGeneralLiability includes aggregation steps that calculate aggregated premiums for specific coverages:

1.  Calculates the aggregate premium for medical expense by taking the sum of final rate for medical expense outputs from each run of the calculation steps.
    
2.  Calculates the aggregate premium for property damage by taking the sum of final rate for property damage outputs from each run of the calculation steps.
    
3.  Calculates the aggregate premium for bodily injury by taking the sum of final rate for bodily injury outputs from each run of the calculation steps.
    
4.  Calculates the aggregate premium for location liability by taking the sum of final rate for location liability outputs from each run of the calculation steps.
    
5.  Calculates the policy premium by taking the sum of all final premium outputs from each run of the calculation steps.
    

Did this article solve your issue?

Let us know so we can improve!

YesNo