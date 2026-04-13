---
title: "Assign Commission Schedules to Producers"
source: "https://help.salesforce.com/s/articleView?id=ind.insurance_assign_commission_schedules_to_producers_624715.htm&language=en_US&type=5"
scraped: "2026-04-13"
filter: "ind.insurance_"
---# Assign Commission Schedules to Producers

Assign Commission Schedules to Producers[](https://help.salesforce.com/s?language=en_US)

You are here:

1.  [Salesforce Help](/s/?language=en_US)
2.  [Docs](/s/products?language=en_US)
3.  [Digital Insurance](https://help.salesforce.com/s/articleView?id=ind.insurance_admin_standard.htm&language=en_US&type=5)

# Assign Commission Schedules to Producers

Commission schedule assignments give you control over who gets commissions, how much, and for what. By viewing commission schedule assignments, producers gain insight into how much they're earning as they issue quotes and close deals.

Before You Begin

-   [Add Commission Schedules and Set Up tabs to records](https://help.salesforce.com/s/articleView?id=ind.insurance_add_commission_schedules_and_set_up_tabs_to_records__624154.htm&language=en_US&type=5 "Add tabs to record pages so your users can configure commission schedules and view commission assignments.").
    
-   [Create commission calculations](https://help.salesforce.com/s/articleView?id=ind.insurance_t_create_commission_calculations_624226.htm&language=en_US&type=5 "Automate complex commission calculations with Decision Matrices, Expression Sets, and Integration Procedures. Your commission schedules either reference these calculations or specify flat amounts or fixed rates.").
    
-   [Create commission schedules](https://help.salesforce.com/s/articleView?id=ind.insurance_t_create_commission_schedules_624454.htm&language=en_US&type=5 "Commission schedules define commission calculations and effective dates. You can create a bunch of commission schedules and have different ones in effect for different producers and insurance products, at different times.").
    

You can assign commission schedules to producers (as described here) and to insurance products (as described in [Assign Commission Schedules to Products](https://help.salesforce.com/s/articleView?id=ind.insurance_assign_commission_schedules_to_products_624588.htm&language=en_US&type=5 "Commission schedule assignments give you control over who gets commissions, how much, and for what. By viewing commission schedule assignments, producers gain insight into how much they're earning as they issue quotes and close deals.")). If you assign the same commission schedule to both a producer and a product, any tweaks you make to the producer's commission schedule assignment take precedence.

[](https://help.salesforce.com/s?language=en_US)You can create as few or as many assignments as you want, though you typically need only three or four per producer. If you add multiple assignments, only one can be associated with the same commissionable event, in the same time period. The assignments reflect terms defined in the commission schedule, and also specify unique information for the producer: minimum and maximum payments, and which events trigger the calculation of a commission. For example:

[](https://help.salesforce.com/s?language=en_US)

-   Quotes
    
-   Sales
    
-   Endorsements
    
-   Renewals
    
-   Payments
    
-   Cancellations, which result in returned commissions ("chargebacks")
    
-   Reinstatements
    

Set up events and transaction types that qualify as commissionable events as picklist values in the Commission Schedule Assignment object. From Setup, in Object Manager, go to the Commission Schedule Assignment object. Then add Quote and your custom transaction types (for example, Sold Policy, Changed/Endorsed, and Cancel Policy) to the Commissionable Event Type field's picklist values.

You can tweak assignments over time, for example, raising the maximum commission amount to motivate producers and promote certain products.

If you don't assign commission schedules to any producers, they earn commissions based on product commission assignments, if any exist.

1.  From the App Launcher, find and select **Producers**.
2.  On the Producers list view, click a **Producer Identifier**.
3.  Click the **Commission Schedules** tab, then click Add.
4.  To add a commission schedule:
    
    (1) Start entering the name of the commission schedule to add.
    
    (2) Select the check box next to it.
    
    (3) Click Select.
    
5.  Edit these values to customize the commission schedule for this producer.
    
    | 
    [](https://help.salesforce.com/s?language=en_US)Effective Start Date
    
     | 
    
    The beginning of the date range for this commission schedule assignment. Use a date on or after the Effective Start Date defined in the underlying commission schedule.
    
     |
    | --- | --- |
    | 
    
    [](https://help.salesforce.com/s?language=en_US)Effective End Date
    
     | 
    
    The end of the date range for this commission schedule assignment. Use a date on or before the Effective End Date defined in the underlying commission schedule.
    
     |
    | 
    
    [](https://help.salesforce.com/s?language=en_US)Min Commission Amount
    
     | 
    
    Minimum commission amount.
    
     |
    | 
    
    [](https://help.salesforce.com/s?language=en_US)Max Commission Amount
    
     | 
    
    Maximum commission amount.
    
     |
    | 
    
    [](https://help.salesforce.com/s?language=en_US)Product ID
    
     | 
    
    Product ID.
    
     |
    | 
    
    [](https://help.salesforce.com/s?language=en_US)Producer ID
    
     | 
    
    The ID of the processing producer.
    
     |
    | 
    
    [](https://help.salesforce.com/s?language=en_US)Production Code
    
     | 
    
    The production code.
    
     |
    | 
    
    [](https://help.salesforce.com/s?language=en_US)Commissionable Event Type
    
     | 
    
    The events that trigger the calculation of a commission for this assignment (for example, Quote, Sold Policy, Changed/Endorsed).
    
     |
    
6.  Click Save.

Did this article solve your issue?

Let us know so we can improve!

YesNo