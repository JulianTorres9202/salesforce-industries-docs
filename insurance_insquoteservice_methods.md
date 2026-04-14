---
title: "InsQuoteService Methods"
source: "https://help.salesforce.com/s/articleView?id=ind.insurance_insquoteservice_methods.htm&language=en_US&type=5"
scraped: "2026-04-14"
filter: "ind.insurance_"
---# InsQuoteService Methods

InsQuoteService Methods[](https://help.salesforce.com/s?language=en_US)

You are here:

1.  [Salesforce Help](/s/?language=en_US)
2.  [Docs](/s/products?language=en_US)
3.  [Digital Insurance](https://help.salesforce.com/s/articleView?id=ind.insurance_admin_standard.htm&language=en_US&type=5)

# InsQuoteService Methods

These are the available InsQuoteService methods.

-   **[InsQuoteService:addInsuredItem](https://help.salesforce.com/s/articleView?id=ind.insurance_insquoteservice__addinsureditem.htm&language=en_US&type=5)**  
    Use this service to add insured items to quotes.
-   **[InsQuoteService:calculateTaxesAndFees](https://help.salesforce.com/s/articleView?id=ind.insurance_insquoteservice__calculatetaxesandfees.htm&language=en_US&type=5)**  
    Use this service to calculate and save taxes and fees on a target quote.
-   **[InsQuoteService:cloneQuote](https://help.salesforce.com/s/articleView?id=ind.insurance_insquoteservice__clonequote.htm&language=en_US&type=5)**  
    Use this service to clone a quote.
-   **[InsQuoteService:createEndorsementQuote](https://help.salesforce.com/s/articleView?id=ind.insurance_insquoteservice_createendorsementquote.htm&language=en_US&type=5)**  
    Use this service to create an endorsement quote with quote line items for single-root and multi-root policies.
-   **[InsQuoteService:createUpdateQuote](https://help.salesforce.com/s/articleView?id=ind.insurance_insquoteservice__createupdatequote.htm&language=en_US&type=5)**  
    Use this service to create a quote for new business, update an existing quote with new information, or create an endorsement quote. For updates, the `quoteId` of the quote to be updated must be included in the remote options.
-   **[InsQuoteService:createUpdateQuoteFromExternal](https://help.salesforce.com/s/articleView?id=ind.insurance_insquoteservice__createupdatequotefromexternal.htm&language=en_US&type=5)**  
    Creates a quote or updates an existing quote with new information through an inbound API call from an external system.
-   **[InsQuoteService:getAccountQuotes](https://help.salesforce.com/s/articleView?id=ind.insurance_insquoteservice__getaccountquotes.htm&language=en_US&type=5)**  
    Use this service to retrieve quote records associated with an `accountId`.
-   **[InsQuoteService:getPlanSpecs](https://help.salesforce.com/s/articleView?id=ind.insurance_insquoteservice__getplanspecs.htm&language=en_US&type=5)**  
    Use this service to get all the quote line items (that is to say, the plan specs) associated with a specific product.
-   **[InsQuoteService:getProductSpecs](https://help.salesforce.com/s/articleView?id=ind.insurance_insquoteservice__getproductspecs.htm&language=en_US&type=5)**  
    Use this service in an OmniScript to get a list of specific product specs used in a quote, at the Quote Line Item level, and which includes product information.
-   **[InsQuoteService:getQuoteVersions](https://help.salesforce.com/s/articleView?id=ind.insurance_insquoteservice__getquoteversions.htm&language=en_US&type=5)**  
    Use this service to retrieve different versions of a quote based on its Opportunity Id, and then return a list of quotes based on the Quote field set **QuoteCompareHeader**.
-   **[InsQuoteService:getQuoteDetail](https://help.salesforce.com/s/articleView?id=ind.insurance_insquoteservice__getquotedetail.htm&language=en_US&type=5)**  
    Use this service to get all of the quote details as JSON.
-   **[InsQuoteService:getRuleLogs](https://help.salesforce.com/s/articleView?id=ind.insurance_insquoteservice_getrulelogs.htm&language=en_US&type=5)**  
    This service retrieves rule logs for a target quote, sorted by execution date in ascending order.
-   **[InsQuoteService:invokeProductRules](https://help.salesforce.com/s/articleView?id=ind.insurance_insquoteservice__invokeproductrules.htm&language=en_US&type=5)**  
    Use this service in quote flows to invoke underwriting rules you've added to a product.
-   **[InsQuoteService:invokeRules](https://help.salesforce.com/s/articleView?id=ind.insurance_insquoteservice__invokerules.htm&language=en_US&type=5)**  
    Use this service to Invoke state transition rules associated with a target state transition on a target quote.
-   **[InsQuoteService:priceLargeGroupRootItems](https://help.salesforce.com/s/articleView?id=ind.insurance_insquoteservicepricelargegrouprootitems.htm&language=en_US&type=5)**  
    This service calculates the price, and optionally taxes and fees, for a specific root item or all root items for a large group quote.
-   **[InsQuoteService:priceRootItem](https://help.salesforce.com/s/articleView?id=ind.insurance_insquoteservice__pricerootitem.htm&language=en_US&type=5)**  
    Use this service to calculate the price (and optionally, taxes and fees) for a target root item and its children under a Quote.
-   **[InsQuoteService:recalculateRollupFormulas](https://help.salesforce.com/s/articleView?id=ind.insurance_insquoteservice__recalculaterollupformulas.htm&language=en_US&type=5)**  
    Use this service to sum the price at the child or grandchild quote line item level and recalculates it to the parent quote line item level.
-   **[InsQuoteService:removeCoverage](https://help.salesforce.com/s/articleView?id=ind.insurance_insquoteservice__removecoverage.htm&language=en_US&type=5)**  
    Use this service in an OmniScript to remove a specified coverage, as per the product code, from the quote. You can use this service on multiple plans.
-   **[InsQuoteService:updateQuoteLine](https://help.salesforce.com/s/articleView?id=ind.insurance_insquoteservice__updatequoteline.htm&language=en_US&type=5)**  
    Use this service to update items on the quote.
-   **[InsQuoteService:updateQuotePlans](https://help.salesforce.com/s/articleView?id=ind.insurance_insquoteservice__updatequoteplans.htm&language=en_US&type=5)**  
    Use this service in an OmniScript to add, update, or upsert (add and update) either coverages or attributes for one or more Group Benefit plans across a quote. This service is designed to process only coverages under root products.

Did this article solve your issue?

Let us know so we can improve!

YesNo