---
title: "Auto Rating"
source: "https://help.salesforce.com/s/articleView?id=ind.insurance_auto_rating_omnistudio.htm&language=en_US&type=5"
scraped: "2026-04-13"
filter: "ind.insurance_"
---# Auto Rating

Auto Rating[](https://help.salesforce.com/s?language=en_US)

You are here:

1.  [Salesforce Help](/s/?language=en_US)
2.  [Docs](/s/products?language=en_US)
3.  [Digital Insurance](https://help.salesforce.com/s/articleView?id=ind.insurance_admin_standard.htm&language=en_US&type=5)

# Auto Rating

When we quote and endorse Auto products, our pricing services use the product model data, product rating procedure, and pricing formulas. The services use these components to price the coverages, vehicles, and total premium. 

The service does the following to price the product:

1.  Pulls data from the Multi Auto product model to form the rating input data.
    
2.  Calls the rating procedure and rating input data to calculate the coverage prices. The rating procedure is mapped to the vehicle (Insured Item Spec) for the Multi Auto product.
    
3.  Takes the coverage price data returned by the rating procedure, then inserts it into the product model.
    
4.  Rolls up the coverage prices to the vehicles using the vehicle pricing formula.
    
5.  Rolls up the vehicle prices to the total (quoted) premium price.
    

Here's what that looks like for the Multi Auto product:

For details of the rating procedure of Auto products, see:

-   [Multi Auto Rating](https://help.salesforce.com/s/articleView?id=ind.insurance_multi_auto_rating_omnistudio.htm&language=en_US&type=5 "The rating procedure we use is the auto_MultiInstanceRating Integration Procedure. It calculates the coverage prices for the Multi Auto product. Any time a broker or customer service rep generates a quote for a potential customer, the quote business process calls this rating procedure to calculate the price for that quote.")
    
    [](https://help.salesforce.com/s?language=en_US)The rating procedure we use is the auto\_MultiInstanceRating Integration Procedure. It calculates the coverage prices for the Multi Auto product. Any time a broker or customer service rep generates a quote for a potential customer, the quote business process calls this rating procedure to calculate the price for that quote.
    
-   [Commercial Auto Rating](https://help.salesforce.com/s/articleView?id=ind.insurance_commercial_auto_rating_omnistudio.htm&language=en_US&type=5 "When we quote and endorse Auto products, our pricing services use the product model data, product rating procedure, and pricing formulas. The services use these components to price the coverages, vehicles, and total premium.")
    
    When we quote and endorse Auto products, our pricing services use the product model data, product rating procedure, and pricing formulas. The services use these components to price the coverages, vehicles, and total premium.
    

-   **[Multi Auto Rating](https://help.salesforce.com/s/articleView?id=ind.insurance_multi_auto_rating_omnistudio.htm&language=en_US&type=5)**  
    The rating procedure we use is the auto\_MultiInstanceRating Integration Procedure. It calculates the coverage prices for the Multi Auto product. Any time a broker or customer service rep generates a quote for a potential customer, the quote business process calls this rating procedure to calculate the price for that quote.
-   **[Commercial Auto with OmniStudio](https://help.salesforce.com/s/articleView?id=ind.insurance_commercial_auto_with_omnistudio.htm&language=en_US&type=5)**  
    The Commercial line of business gives you a fully functional example of the Commercial Auto product models, rating procedures, and business processes for quoting and issuing policies.

Did this article solve your issue?

Let us know so we can improve!

YesNo