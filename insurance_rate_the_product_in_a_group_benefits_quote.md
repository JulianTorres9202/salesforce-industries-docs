---
title: "Rate the Product in a Group Benefits Quote"
source: "https://help.salesforce.com/s/articleView?id=ind.insurance_rate_the_product_in_a_group_benefits_quote.htm&language=en_US&type=5"
scraped: "2026-04-14"
filter: "ind.insurance_"
---# Rate the Product in a Group Benefits Quote

Rate the Product in a Group Benefits Quote[](https://help.salesforce.com/s?language=en_US)

You are here:

1.  [Salesforce Help](/s/?language=en_US)
2.  [Docs](/s/products?language=en_US)
3.  [Digital Insurance](https://help.salesforce.com/s/articleView?id=ind.insurance_admin_standard.htm&language=en_US&type=5)

# Rate the Product in a Group Benefits Quote

After uploading and correcting census data, rate the selected products. If census data continues to change, the rate automatically gets recalculated.

1.  To rate a product for the first time, click **Rate Now**.
    
    Later, if you upload a new census or change group member and dependent values such as birthdate and gender, the rate is adjusted based on the new data.
    
2.  After the quote is approved and the customer signs a contract, use an OmniScript to create a contract. In the background, the `createUpdateContract` method runs and creates a new Contract Group Plan.
3.  Take the next step in the Group Benefits flow: Enrollment.

Did this article solve your issue?

Let us know so we can improve!

YesNo