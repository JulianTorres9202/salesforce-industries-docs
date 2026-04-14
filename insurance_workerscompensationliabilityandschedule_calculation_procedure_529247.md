---
title: "WorkersCompensationLiabilityAndSchedule Calculation Procedure"
source: "https://help.salesforce.com/s/articleView?id=ind.insurance_workerscompensationliabilityandschedule_calculation_procedure_529247.htm&language=en_US&type=5"
scraped: "2026-04-14"
filter: "ind.insurance_"
---# WorkersCompensationLiabilityAndSchedule Calculation Procedure

WorkersCompensationLiabilityAndSchedule Calculation Procedure[](https://help.salesforce.com/s?language=en_US)

You are here:

1.  [Salesforce Help](/s/?language=en_US)
2.  [Docs](/s/products?language=en_US)
3.  [Digital Insurance](https://help.salesforce.com/s/articleView?id=ind.insurance_admin_standard.htm&language=en_US&type=5)

# WorkersCompensationLiabilityAndSchedule Calculation Procedure

The WorkersCompensationLiabilityAndSchedule calculation procedure does this

[](https://help.salesforce.com/s?language=en_US)We expect that you'll create your own calculation procedure to rate your workers compensation products. You can use **WorkersCompensationLiabilityAndSchedule** as an example, and make changes to this procedure so you can see how calculation procedures work.

[](https://help.salesforce.com/s?language=en_US)Here's what each step of the **WorkersCompensationLiabilityAndSchedule** calculation procedure does:

[](https://help.salesforce.com/s?language=en_US)

1.  Does matrix lookups to get the rate factor and minimum amount for employer's liability.
    
2.  Calculates the employer's liability.
    
3.  Calculates the premium for the employer's liability.
    
4.  Calculates the location coverage.
    
5.  Calculates the scheduled discount amount.
    
6.  Calculates the scheduled discount amount.
    
7.  Calculates the scheduled experience rating mod.
    

Did this article solve your issue?

Let us know so we can improve!

YesNo