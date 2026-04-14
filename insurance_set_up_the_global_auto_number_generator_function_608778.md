---
title: "Set Up the Global Auto-Number Generator Function"
source: "https://help.salesforce.com/s/articleView?id=ind.insurance_set_up_the_global_auto_number_generator_function_608778.htm&language=en_US&type=5"
scraped: "2026-04-14"
filter: "ind.insurance_"
---# Set Up the Global Auto-Number Generator Function

Set Up the Global Auto-Number Generator Function[](https://help.salesforce.com/s?language=en_US)

You are here:

1.  [Salesforce Help](/s/?language=en_US)
2.  [Docs](/s/products?language=en_US)
3.  [Digital Insurance](https://help.salesforce.com/s/articleView?id=ind.insurance_admin_standard.htm&language=en_US&type=5)

# Set Up the Global Auto-Number Generator Function

If you plan to use Vlocity's auto-number generator function as part of your custom numbers, you must add it to Custom Settings.

1.  On the Setup page, go to Custom Settings.
2.  Click **Global Auto Number Setting** > **Manage**.
3.  Next to GlobalAutoNumber, click **Edit**.
4.  Review and if needed enter new values into the following fields:
    
    -   Name
        
        Leave the name **GlobalAutoNumber**.
        
    -   Increment
        
        The integer by which you want Vlocity to increment its auto-generated numbers.
        
    -   LastGeneratedNumber
        
        Enter the number you want Vlocity to use to start auto-generating numbers.
        
    -   LeftPad
        
        The digit or letter you want Vlocity to use to pad numbers that are shorter than the Minimum Length.
        
    -   Minimum Length
        
        The minimum length of auto-generated numbers.
        
    -   Prefix
        
        Any prefix you want to add before the auto-generated number.
        
    -   Separator
        
        A character you want to separate the prefix from the number. Leave this field blank if you don't want to add a separator.
        
    
5.  Click **Save**.

[](https://help.salesforce.com/s?language=en_US)

[](https://help.salesforce.com/s?language=en_US)As an example, if you set the GlobalAutoNumber settings like this:

[](https://help.salesforce.com/s?language=en_US)

-   Name:**GlobalAutoNumber**.
    
-   Increment: 1
    
-   LastGeneratedNumber: 27
    
-   LeftPad: 0
    
-   Minimum Length: 6
    
-   Prefix: VL
    
-   Separator: \-
    

The next number Vlocity generates is VL-000028.

Did this article solve your issue?

Let us know so we can improve!

YesNo