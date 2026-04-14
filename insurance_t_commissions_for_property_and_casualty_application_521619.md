---
title: "Commissions for Property and Casualty Application"
source: "https://help.salesforce.com/s/articleView?id=ind.insurance_t_commissions_for_property_and_casualty_application_521619.htm&language=en_US&type=5"
scraped: "2026-04-14"
filter: "ind.insurance_"
---# Commissions for Property and Casualty Application

Commissions for Property and Casualty Application[](https://help.salesforce.com/s?language=en_US)

You are here:

1.  [Salesforce Help](/s/?language=en_US)
2.  [Docs](/s/products?language=en_US)
3.  [Digital Insurance](https://help.salesforce.com/s/articleView?id=ind.insurance_admin_standard.htm&language=en_US&type=5)

# Commissions for Property and Casualty Application

You can now track commissions for agents and insurance products, and gain insight into commissions associated with each stage of the customer journey.

**Quotes**

As commissionable events occur, services calculate commissions and save them to quotes. You can see the estimated quote commission in the **Details** for each quote.

**Products**

You can add tabs to product pages so your users can configure commission schedules and view commission assignments. For instructions on how to do configure commission schedules, see [Add Commission Schedules and Set Up Tabs to Records](https://help.salesforce.com/s/articleView?id=ind.insurance_add_commission_schedules_and_set_up_tabs_to_records__624154.htm&language=en_US&type=5 "Add tabs to record pages so your users can configure commission schedules and view commission assignments.").

**Policies and Endorsements**

Commissions on policies and endorsements are visible in the policy **Details**.

You can also see all the producer commissions for each policy in the **Related** section.

**Producers**

Producers can see all their commissions information in the **Commissions** tab.

[](https://help.salesforce.com/s?language=en_US)

## Commission Calculations

In our flow, we've used the **Producer Commissions** calculation procedure to calculate commissions. Commission schedules either reference these calculations, or specify flat amounts or fixed rates. For instructions on how to create Commission calculation procedures, see [Create Commission Calculations](https://help.salesforce.com/s/articleView?id=ind.insurance_t_create_commission_calculations_624226.htm&language=en_US&type=5 "Automate complex commission calculations with Decision Matrices, Expression Sets, and Integration Procedures. Your commission schedules either reference these calculations or specify flat amounts or fixed rates.").

Here's what our calculation procedure does:

1.  Performs a matrix lookup to check the rate.
    
2.  Calculates the base commission using the premium and rate.
    
3.  Performs a matrix lookup of the Producer Premium to determine the commission rate.
    
4.  Calculates the override commission using the base commission and commission rate.
    
5.  Calculates the final commission using the base commission and override commission.
    

[](https://help.salesforce.com/s?language=en_US)

## Assign Commission Schedules to Products

Commission schedule assignments give you control over who gets commissions, how much, and for what. You can create as few or as many assignments as you want, though you typically need only three or four per product. If you add multiple assignments, only one can be associated with the same commissionable event, in the same time period.

To assign a commission schedule to a product, see the instructions in [Assign Commission Schedules to Products](https://help.salesforce.com/s/articleView?id=ind.insurance_assign_commission_schedules_to_products_624588.htm&language=en_US&type=5 "Commission schedule assignments give you control over who gets commissions, how much, and for what. By viewing commission schedule assignments, producers gain insight into how much they're earning as they issue quotes and close deals.").

[](https://help.salesforce.com/s?language=en_US)

## Assign Commission Schedules to Producers

By viewing commission schedule assignments, producers gain insight into how much they're earning as they issue quotes and close deals.

Your org comes with three commission schedules that we've created and used in our workflows:

-   EstimatedCommisions - for quoting
    
-   Flat Commissions
    
-   Policy Commissions
    

We then assigned these commission schedules to our producer persona. The assignments reflect terms defined in the commission schedule, and also specify unique information for the producer: minimum and maximum payments, and which events trigger the calculation of a commission. For example:

-   Quotes
    
-   Sales
    
-   Endorsements
    
-   Renewals
    
-   Payments
    
-   Cancellations, which result in returned commissions ("chargebacks")
    

To assign a commission schedule to a producer, see the instructions in [Assign Commission Schedules to Producers](https://help.salesforce.com/s/articleView?id=ind.insurance_assign_commission_schedules_to_producers_624715.htm&language=en_US&type=5 "Commission schedule assignments give you control over who gets commissions, how much, and for what. By viewing commission schedule assignments, producers gain insight into how much they're earning as they issue quotes and close deals.").

Did this article solve your issue?

Let us know so we can improve!

YesNo