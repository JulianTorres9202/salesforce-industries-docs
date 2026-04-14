---
title: "Services that Call Rating Integration Procedures"
source: "https://help.salesforce.com/s/articleView?id=ind.insurance_services_that_call_rating_integration_procedures_610740.htm&language=en_US&type=5"
scraped: "2026-04-14"
filter: "ind.insurance_"
---# Services that Call Rating Integration Procedures

Services that Call Rating Integration Procedures[](https://help.salesforce.com/s?language=en_US)

You are here:

1.  [Salesforce Help](/s/?language=en_US)
2.  [Docs](/s/products?language=en_US)
3.  [Digital Insurance](https://help.salesforce.com/s/articleView?id=ind.insurance_admin_standard.htm&language=en_US&type=5)

# Services that Call Rating Integration Procedures

When you create a rating Integration Procedure, think about what services call it. The services inform how you create the Integration Procedure and the structure of input and output data.

Some common services that rate products are:

-   InsProductService:getRatedProducts
    
    This service fetches products and rates them, then returns them to the caller. It's often the service that first rates a product during a quote flow.
    
    To learn about the options that can be set that could impact the rating Integration Procedure, see [InsProductService:getRatedProducts](https://help.salesforce.com/s/articleView?id=ind.insurance_insproductservice__getratedproducts.htm&language=en_US&type=5 "Use this service to get an array of one or more products, priced using rating procedures attached to those products. This service also includes extra features such as tax and fee calculations, filtering, and performance optimization.").
    
-   InsProductService:getRatedGroupProducts
    
    This service fetches large group and small group products and rates them, then returns them to the caller. It's often the service that first rates a product during a quote flow. To learn about the service options that can impact the rating Integration Procedure, see [InsProductService:getRatedGroupProducts](https://help.salesforce.com/s/articleView?id=ind.insurance_insproductservice__getratedgroupproducts.htm&language=en_US&type=5 "This service is used only with small group products that use a census. The service allows the products to be kept with the product service.").
    
-   InsProductService:repriceProduct
    
    This service calls the rating procedure to rerate products when a user makes changes to the insured items and coverages on a quote. To learn about the service options that can impact the rating Integration Procedure, see [InsProductService:repriceProduct](https://help.salesforce.com/s/articleView?id=ind.insurance_insproductservice__repriceproduct.htm&language=en_US&type=5 "Use this service to price one product using the rating procedure attached to that product. This service is usually called when a user selects a product and customizes its coverage.").
    
-   InsQuoteService:priceRootItem
    
    This service rates a target root item on a quote. To learn about it, see [InsQuoteService:priceRootItem](https://help.salesforce.com/s/articleView?id=ind.insurance_insquoteservice__pricerootitem.htm&language=en_US&type=5 "Use this service to calculate the price (and optionally, taxes and fees) for a target root item and its children under a Quote.").
    
-   InsQuoteService:updateQuoteLine
    
    If the `reprice` option is set to `true` on this service, it calls the rating procedure. To learn about it, see [InsQuoteService:updateQuoteLine](https://help.salesforce.com/s/articleView?id=ind.insurance_insquoteservice__updatequoteline.htm&language=en_US&type=5 "Use this service to update items on the quote.").
    
-   InsEnrollmentService:getRatedProducts
    
    This service fetches products and rates them for a specific enrollee and their dependents, then returns them to the caller. To learn about the service options that can impact the rating Integration Procedure, see [InsEnrollmentService:getRatedProducts](https://help.salesforce.com/s/articleView?id=ind.insurance_insenrollmentservice__getratedproducts.htm&language=en_US&type=5 "Use the service to return a list of eligible products for a given enrollee and their dependents. The rate band prices for each product are displayed when the plan's rate type is Composite.").
    

Did this article solve your issue?

Let us know so we can improve!

YesNo