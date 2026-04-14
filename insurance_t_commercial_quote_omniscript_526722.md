---
title: "Commercial Quote OmniScript"
source: "https://help.salesforce.com/s/articleView?id=ind.insurance_t_commercial_quote_omniscript_526722.htm&language=en_US&type=5"
scraped: "2026-04-14"
filter: "ind.insurance_"
---# Commercial Quote OmniScript

Commercial Quote OmniScript[](https://help.salesforce.com/s?language=en_US)

You are here:

1.  [Salesforce Help](/s/?language=en_US)
2.  [Docs](/s/products?language=en_US)
3.  [Digital Insurance](https://help.salesforce.com/s/articleView?id=ind.insurance_admin_standard.htm&language=en_US&type=5)

# Commercial Quote OmniScript

Commercial quoting is powered by the Commercial Quote OmniScript. It uses Rating Procedures, Integration Procedures, Omnistudio Data Mappers, LWCs, and FlexCards to create the guided flow.

You can find the Commercial Quoting OmniScript in OmniStudio OmniScripts under:

[](https://help.salesforce.com/s?language=en_US)

-   Type/Subtype: InsCommercial/QuoteCreation
    
-   OmniScript Name: Commercial Quote Creation
    

Here's a deeper look into its components:

| 
Component Name

 | 

Component Type

 | 

What It Does

 | 

What It Calls

 |
| --- | --- | --- | --- |
| 

getAccOppInformation

 | 

Data Mapper Extract Action

 | 

It extracts details of the opportunity, the associated account, producer, and record ID.

 | 

Ins\_ReadAccountAndOpportunityDetails\_CommercialQuoteOS

 |
| 

quoteDetailsSection

 | 

Step

 | 

Displays the screen for the user to enter quote information.

 | 

None

 |
| 

getRatedProductsDetails

 | 

Remote Action

 | 

Calls the getRatedProducts method to get an array of one or more products.

 | 

[InsProductService:getRatedProducts](https://help.salesforce.com/s/articleView?id=ind.insurance_insproductservice__getratedproducts.htm&language=en_US&type=5 "Use this service to get an array of one or more products, priced using rating procedures attached to those products. This service also includes extra features such as tax and fee calculations, filtering, and performance optimization.")

 |
| 

setEditBlockWithPrefilledValues

 | 

Set Values

 | 

Prefills values for the products returned in the previous step.

 | 

None

 |
| 

selectProduct

 | 

Step

 | 

Displays the screen for the user to select a product for the quote.

 | 

None

 |
| 

actionBlock

 | 

Action Block

 | 

Uses an integration procedure to create the quote.

 | 

Commercial Quote Creation

 |
| 

confirmQuote

 | 

Step

 | 

Displays the confirmation screen with the details of the newly created quote.

 | 

None

 |

Did this article solve your issue?

Let us know so we can improve!

YesNo