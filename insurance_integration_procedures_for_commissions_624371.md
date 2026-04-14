---
title: "Integration Procedures for Commissions"
source: "https://help.salesforce.com/s/articleView?id=ind.insurance_integration_procedures_for_commissions_624371.htm&language=en_US&type=5"
scraped: "2026-04-14"
filter: "ind.insurance_"
---# Integration Procedures for Commissions

Integration Procedures for Commissions[](https://help.salesforce.com/s?language=en_US)

You are here:

1.  [Salesforce Help](/s/?language=en_US)
2.  [Docs](/s/products?language=en_US)
3.  [Digital Insurance](https://help.salesforce.com/s/articleView?id=ind.insurance_admin_standard.htm&language=en_US&type=5)

# Integration Procedures for Commissions

If a commission calculation requires data from multiple sources, use Integration Procedures to pull all the necessary data together. You can incorporate matrix lookups into an Integration Procedure, have the Integration Procedure use an Omnistudio Data Mapper to fetch data from another source, and then factor that data into the calculation.

Example: You can pay an additional commission based on how many policies a producer sold in the last six months.

For a $10,000 premium:

[](https://help.salesforce.com/s?language=en_US)

1.  Use a flat matrix to calculate the base commission rate.
    
    [](https://help.salesforce.com/s?language=en_US)Looking up the $10,000 premium on the matrix, a 15% rate applies. So multiply $10,000 by 15%.
    
    [](https://help.salesforce.com/s?language=en_US)$10,000 x 15% = $1,500 base commission
    
2.  Use a Data Mapper to calculate the number of policies sold by the producer in last six months.
    
    Let's say it's 10 policies.
    
3.  Use another matrix to calculate an add-on commission based on the base commission and the number of policies sold.
    
    Looking up 10 policies, a 5% rate applies. So multiply the $1,500 base commission by 5%.
    
    $1,500 x 5% = $75 add-on commission
    
    | 
    Number of Policies Low
    
     | 
    
    Number of Policies High
    
     | 
    
    Rate
    
     |
    | --- | --- | --- |
    | 
    
    0
    
     | 
    
    5
    
     | 
    
    4%
    
     |
    | 
    
    6
    
     | 
    
    10
    
     | 
    
    5%
    
     |
    | 
    
    11
    
     | 
    
    20
    
     | 
    
    7%
    
     |
    | 
    
    21
    
     | 
    
    1,000
    
     |  |
    
4.  Add the base commission to the add-on commission to get the total commission.
    
    $1,500 + $75 = $1,575 total commission
    

Did this article solve your issue?

Let us know so we can improve!

YesNo