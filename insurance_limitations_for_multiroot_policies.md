---
title: "Considerations and Limitations"
source: "https://help.salesforce.com/s/articleView?id=ind.insurance_limitations_for_multiroot_policies.htm&language=en_US&type=5"
scraped: "2026-04-14"
filter: "ind.insurance_"
---# Considerations and Limitations

Considerations and Limitations[](https://help.salesforce.com/s?language=en_US)

You are here:

1.  [Salesforce Help](/s/?language=en_US)
2.  [Docs](/s/products?language=en_US)
3.  [Digital Insurance](https://help.salesforce.com/s/articleView?id=ind.insurance_admin_standard.htm&language=en_US&type=5)

# Considerations and Limitations

Here are some things to keep in mind about multiroot policies.

[](https://help.salesforce.com/s?language=en_US)

-   Ensure that each product within a multiroot parent policy is ‌unique with a unique product code.
    
-   To calculate rollup term amounts for a multiroot quote, make sure that the product Term field is configured with a value. Alternatively, you can also input the value by using the Term\_\_c field in the input JSON of the InsQuoteService:createUpdateQuote service.
-   Enter the effective date in the specified date format.
    
-   Enter the values for the additionalFields option in JSON format.
    
-   You can’t configure the payment schedule for multiroot policies.
    
-   Multiroot services don’t provide transaction breakdown data.
    
-   Multiroot policies don’t support cancellation, reinstatement, renewal, and out-of-service-endorsement transactions.
    

Did this article solve your issue?

Let us know so we can improve!

YesNo