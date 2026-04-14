---
title: "Expression Sets for Commissions"
source: "https://help.salesforce.com/s/articleView?id=ind.insurance_expression_sets_for_commissions_624353.htm&language=en_US&type=5"
scraped: "2026-04-14"
filter: "ind.insurance_"
---# Expression Sets for Commissions

Expression Sets for Commissions[](https://help.salesforce.com/s?language=en_US)

You are here:

1.  [Salesforce Help](/s/?language=en_US)
2.  [Docs](/s/products?language=en_US)
3.  [Digital Insurance](https://help.salesforce.com/s/articleView?id=ind.insurance_admin_standard.htm&language=en_US&type=5)

# Expression Sets for Commissions

Expression Sets give you the flexibility to perform multiple steps to arrive at a commission amount. You can incorporate a Decision Matrix lookup into an Expression Set.

Example: To pay override commissions to high performers, you use one matrix to calculate a base commission, and a second matrix to calculate an override commission.

For a $10,000 premium:

[](https://help.salesforce.com/s?language=en_US)

1.  Use a flat matrix to calculate the base commission.
    
    Looking up the $10,000 premium on the matrix, a 15% rate applies. So multiply $10,000 by 15%.
    
    $10,000 x 15% = $1,500 base commission
    
2.  Use a tiered matrix to calculate the override commission based on the base commission amount.
    
    Looking up the $1,500 base commission on the matrix, 5% applies to the first $999, and 10% applies to the remaining $501.
    
    ($999 x 5%) + ($501 x 10%) = $49.95 + $50.10 = $100.05 override commission
    
3.  Add the base commission to the override commission to get the total commission.
    
    $1,500 base + $100.05 override = $1,600.05 total commission
    

Did this article solve your issue?

Let us know so we can improve!

YesNo