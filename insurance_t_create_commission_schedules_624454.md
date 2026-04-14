---
title: "Create Commission Schedules"
source: "https://help.salesforce.com/s/articleView?id=ind.insurance_t_create_commission_schedules_624454.htm&language=en_US&type=5"
scraped: "2026-04-14"
filter: "ind.insurance_"
---# Create Commission Schedules

Create Commission Schedules[](https://help.salesforce.com/s?language=en_US)

You are here:

1.  [Salesforce Help](/s/?language=en_US)
2.  [Docs](/s/products?language=en_US)
3.  [Digital Insurance](https://help.salesforce.com/s/articleView?id=ind.insurance_admin_standard.htm&language=en_US&type=5)

# Create Commission Schedules

Commission schedules define commission calculations and effective dates. You can create a bunch of commission schedules and have different ones in effect for different producers and insurance products, at different times.

Before You Begin

-   [Add Commission Schedules and Set Up tabs to records](https://help.salesforce.com/s/articleView?id=ind.insurance_add_commission_schedules_and_set_up_tabs_to_records__624154.htm&language=en_US&type=5 "Add tabs to record pages so your users can configure commission schedules and view commission assignments.").
    
-   [Create commission calculations](https://help.salesforce.com/s/articleView?id=ind.insurance_t_create_commission_calculations_624226.htm&language=en_US&type=5 "Automate complex commission calculations with Decision Matrices, Expression Sets, and Integration Procedures. Your commission schedules either reference these calculations or specify flat amounts or fixed rates.").
    

[](https://help.salesforce.com/s?language=en_US)You get to choose which objects can use a commission schedule, for example Quote, InsurancePolicy, Contract, and Producer objects.

1.  From the App Launcher, find and select **Commission Schedules**.
2.  Click **New**.
3.  Enter these values.
    
    | 
    [](https://help.salesforce.com/s?language=en_US)Name
    
     | 
    
    Name of the schedule.
    
     |
    | --- | --- |
    | 
    
    [](https://help.salesforce.com/s?language=en_US)Description
    
     | 
    
    Description.
    
     |
    | 
    
    [](https://help.salesforce.com/s?language=en_US)Active
    
     | 
    
    Select this check box to make the commission schedule available to use.
    
     |
    | 
    
    [](https://help.salesforce.com/s?language=en_US)Effective Start Date
    
     | 
    
    The beginning of the date range for this schedule.
    
     |
    | 
    
    [](https://help.salesforce.com/s?language=en_US)Effective End Date
    
     | 
    
    The end of the date range for this schedule.
    
     |
    | 
    
    [](https://help.salesforce.com/s?language=en_US)Calculation Type
    
     | 
    
    How to calculate the commission. You can use a Decision Matrix, Expression Set, Calculation Matrix, Calculation Procedure, Integration Procedure, a flat Amount, or a Rate.
    
    Note If you're new to Insurance in Summer '23 or later and are using the Business Rule Engine (BRE) license, use Expression Set and Decision Matrix instead of Calculation Procedure and Calculation Matrix.
    
    
    
    
    
     |
    | 
    
    Calculation Process Name
    
     | 
    
    The name of the calculation process to reference for the Decision Matrix, Expression Set, Calculation Matrix, Calculation Procedure, and Integration Procedure types.
    
     |
    | 
    
    [](https://help.salesforce.com/s?language=en_US)Commission Amount
    
     | 
    
    An amount for the Amount type.
    
     |
    | 
    
    Commission Rate
    
     | 
    
    A percentage for the Rate type.
    
     |
    | 
    
    [](https://help.salesforce.com/s?language=en_US)Commission Structure
    
     | 
    
    Flat or Tiered for the Decision Matrix and Calculation Matrix types.
    
     |
    | 
    
    [](https://help.salesforce.com/s?language=en_US)Applicable Object
    
     | 
    
    The objects that can be assigned this commission schedule (for example, Quote, InsurancePolicy, Contract, Producer).
    
     |
    | 
    
    Calculation Process Input Mapping
    
     | 
    
    A field value to use as input for the commission calculation for the Decision Matrix, Expression Set, Calculation Matrix, Calculation Procedure, and Integration Procedure types.
    
    To edit input mappings after you save a commission schedule, click **Add New** to add a new field value, or click the trash icon to delete an existing one.
    
     |
    | 
    
    Calculation Process Output
    
     | 
    
    A field value and formula to apply to the commission calculation output for the Decision Matrix, Expression Set, Calculation Matrix, Calculation Procedure, and Integration Procedure types.
    
    To edit process output after you save a commission schedule, click **Add New** to add a new field value and formula, or click the trash icon to delete an existing field and formula.
    
     |
    
4.  Click **Save**.

[](https://help.salesforce.com/s?language=en_US)[](https://help.salesforce.com/s?language=en_US)

-   [Assign Commission Schedules to Products](https://help.salesforce.com/s/articleView?id=ind.insurance_assign_commission_schedules_to_products_624588.htm&language=en_US&type=5 "Commission schedule assignments give you control over who gets commissions, how much, and for what. By viewing commission schedule assignments, producers gain insight into how much they're earning as they issue quotes and close deals.")
    
-   [Assign Commission Schedules to Producers](https://help.salesforce.com/s/articleView?id=ind.insurance_assign_commission_schedules_to_producers_624715.htm&language=en_US&type=5 "Commission schedule assignments give you control over who gets commissions, how much, and for what. By viewing commission schedule assignments, producers gain insight into how much they're earning as they issue quotes and close deals.")
    

Did this article solve your issue?

Let us know so we can improve!

YesNo