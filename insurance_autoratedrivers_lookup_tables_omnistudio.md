---
title: "autoRateDrivers Lookup Tables"
source: "https://help.salesforce.com/s/articleView?id=ind.insurance_autoratedrivers_lookup_tables_omnistudio.htm&language=en_US&type=5"
scraped: "2026-04-13"
filter: "ind.insurance_"
---# autoRateDrivers Lookup Tables

autoRateDrivers Lookup Tables[](https://help.salesforce.com/s?language=en_US)

You are here:

1.  [Salesforce Help](/s/?language=en_US)
2.  [Docs](/s/products?language=en_US)
3.  [Digital Insurance](https://help.salesforce.com/s/articleView?id=ind.insurance_admin_standard.htm&language=en_US&type=5)

# autoRateDrivers Lookup Tables

The autoRateDrivers expression set uses lookup tables to identify drivers.

| 
Lookup Table Name

 | 

Description

 |
| --- | --- |
| 

autoDriverClass

 | 

Handles a combination of characteristics of drivers as entered by customers:

-   Years experience
    
-   Gender
    
-   Marital Status
    
-   Good Student
    

Takes inputs that vary per characteristic. These inputs are outputs of other lookup tables. Returns percentage outputs.

 |
| 

autoDriverGoodStudent

 | 

Handles the GPA of a student driver entered by a customer.

Takes a numeric value. Returns a Y or N value.

 |
| 

autoDriverPoints

 | 

Handles the points on the driver's record, entered by a customer.

Takes a numeric input. Returns a number of percentage outputs.

 |
| 

autoDriverSafe

 | 

Handles user data about whether a driver is rated as safe.

Takes a Y or N input. Returns a number of percentage outputs.

 |
| 

autoSafeDriver

 | 

Handles data about a driver's safety record.

Takes a numeric input. Returns a Y or N output.

 |

Did this article solve your issue?

Let us know so we can improve!

YesNo