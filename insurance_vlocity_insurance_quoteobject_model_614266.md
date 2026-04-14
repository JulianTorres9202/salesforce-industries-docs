---
title: "Insurance Quote Object Model"
source: "https://help.salesforce.com/s/articleView?id=ind.insurance_vlocity_insurance_quoteobject_model_614266.htm&language=en_US&type=5"
scraped: "2026-04-14"
filter: "ind.insurance_"
---# Insurance Quote Object Model

Insurance Quote Object Model[](https://help.salesforce.com/s?language=en_US)

You are here:

1.  [Salesforce Help](/s/?language=en_US)
2.  [Docs](/s/products?language=en_US)
3.  [Digital Insurance](https://help.salesforce.com/s/articleView?id=ind.insurance_admin_standard.htm&language=en_US&type=5)

# Insurance Quote Object Model

We've extended the Salesforce quote data model to store Insurance-specific data in quotes. When Insurance quoting uses the functionality of both Insurance and Salesforce to store all the data associated with that quote.

Quote data is created, updated, removed, and pulled by the services in the InsQuoteService class. The primary services are:

-   [InsQuoteService:createUpdateQuote](https://help.salesforce.com/s/articleView?id=ind.insurance_insquoteservice__createupdatequote.htm&language=en_US&type=5 "Use this service to create a quote for new business, update an existing quote with new information, or create an endorsement quote. For updates, the quoteId of the quote to be updated must be included in the remote options.")
    
-   [InsQuoteService:cloneQuote](https://help.salesforce.com/s/articleView?id=ind.insurance_insquoteservice__clonequote.htm&language=en_US&type=5 "Use this service to clone a quote.")
    
-   [InsQuoteService:getQuoteDetail](https://help.salesforce.com/s/articleView?id=ind.insurance_insquoteservice__getquotedetail.htm&language=en_US&type=5 "Use this service to get all of the quote details as JSON.")
    
-   [InsQuoteService:removeCoverage](https://help.salesforce.com/s/articleView?id=ind.insurance_insquoteservice__removecoverage.htm&language=en_US&type=5 "Use this service in an OmniScript to remove a specified coverage, as per the product code, from the quote. You can use this service on multiple plans.")
    
-   [InsQuoteService:updateQuotePlans](https://help.salesforce.com/s/articleView?id=ind.insurance_insquoteservice__updatequoteplans.htm&language=en_US&type=5 "Use this service in an OmniScript to add, update, or upsert (add and update) either coverages or attributes for one or more Group Benefit plans across a quote. This service is designed to process only coverages under root products.")
    
-   [InsQuoteService:getPlanSpecs](https://help.salesforce.com/s/articleView?id=ind.insurance_insquoteservice__getplanspecs.htm&language=en_US&type=5 "Use this service to get all the quote line items (that is to say, the plan specs) associated with a specific product.")
    
-   [InsQuoteService:getProductSpecs](https://help.salesforce.com/s/articleView?id=ind.insurance_insquoteservice__getproductspecs.htm&language=en_US&type=5 "Use this service in an OmniScript to get a list of specific product specs used in a quote, at the Quote Line Item level, and which includes product information.")
    
-   [InsQuoteService:calculateTaxesAndFees](https://help.salesforce.com/s/articleView?id=ind.insurance_insquoteservice__calculatetaxesandfees.htm&language=en_US&type=5 "Use this service to calculate and save taxes and fees on a target quote.")
    

These Services are used in OmniScripts and Integration Procedures. OmniScripts and Integration Procedures maintain runtime data in their own Data Object Models (DOMs), formatted in JSON.

When a service is called, all or part of the data from the DOM can be passed to that service. After a service completes execution, JSON-formatted data is returned and the DOM of the OmniScript or Integration Procedure is updated. Other services such as getRatedProduct and repriceProduct pull information from the root product and use the rating engine to price the product being quoted.

If you've set up complete product specs, created a well-formed rating engine, and mapped the rating engine to the product spec correctly, Insurance creates quotes and stores the data according to the data model described in this topic.

A quote object contains information about all the coverages, insured items, and insured parties that are part of the quote.

[](https://help.salesforce.com/s?language=en_US)

## Single Root vs Multi-Root Quote Data

Most Insurance lines of business use a single root product per quote. That means that the quote includes one root product, and can include multiple insured items, insured parties, and coverages.

Group Health lines of business use multiple root products (plans) per quote. That means that one group quote can include lots of root products, plus insured items, insured parties, and coverages for each root product.

Data stored on the quote and quote line items vary between single-root and multi-root quotes.

Single-root quotes:

-   JSON rated data (containing calculated premiums) gets set on the quote object.
    
-   The `PrimaryRootItemId` is set on the quote object. It points to the root quote line item.
    

Multi-root quotes:

-   JSON rated data gets set on the quote line items on a per-product basis.
    
-   No `PrimaryRootItemId` is set
    

[](https://help.salesforce.com/s?language=en_US)

## What's in the Quote Object

The quote object contains these major areas where data is stored:

-   Insurance quote details
    
-   Insurance quote line items
    
-   Quote pricing adjustments
    
    [](https://help.salesforce.com/s?language=en_US)Quote pricing adjustments are populated by the [calculateTaxesAndFees](https://help.salesforce.com/s/articleView?id=ind.insurance_inspolicyservice__calculatetaxesandfees.htm&language=en_US&type=5 "Use this service to calculate and save taxes and fees on a target asset (policy).") service, usually when it's used in a flow that calculates taxes and fees separately from generating a quote.
    
    [](https://help.salesforce.com/s?language=en_US)To get to the Quote Pricing Adjustments, click the **Related** tab on the quote record, then scroll down to **Quote Pricing Adjustments**.
    
    [](https://help.salesforce.com/s?language=en_US)Each line item shows the pricing adjustment's Id (name), amount, and source of the tax or fee. You can click the **Tax/Fee** ID of any adjustment to see where it comes from.
    
-   Insurance Quote Item Relationship Object
    
-   Insurance coverages
    
-   Insurance insured items
    

[](https://help.salesforce.com/s?language=en_US)

## Quote Data Model

To see the full quote >data model, see [Insurance and Financial Services Data Model](https://help.salesforce.com/s/articleView?id=ind.insurance_vlocity_insurance_and_financial_services_data_model_651683.htm&language=en_US&type=5 "The Insurance and Financial Services data model is a comprehensive data model designed to address the complexities and challenges faced by cloud-based insurance and financial services systems across insurance markets.").

-   **[Insurance Quote Details](https://help.salesforce.com/s/articleView?id=ind.insurance_vlocity_insurance_quote_details_614380.htm&language=en_US&type=5)**  
    The header information for a quote is populated by the InsQuoteService:createUpdateQuote service. You can see it in the Quote object's Details tab.
-   **[Insurance Quote Line Items](https://help.salesforce.com/s/articleView?id=ind.insurance_vlocity_insurance_quote_line_items_614459.htm&language=en_US&type=5)**  
    Quote line items are stored as separate objects that are associated with and linked to their associated quote object.
-   **[Insurance Quote Item Relationships Object](https://help.salesforce.com/s/articleView?id=ind.insurance_vlocity_insurance_quote_item_relationshipsobject_614611.htm&language=en_US&type=5)**  
    The Quote Item Relationships object is an object that holds the table that's used for many-to-many quote line item relationships only. It creates a structure that lets Vlocity store driver data only one time.
-   **[Insurance Coverages](https://help.salesforce.com/s/articleView?id=ind.insurance_vlocity_insurance_coverages_614643.htm&language=en_US&type=5)**  
    Vlocity uses the root product(s) as the basis for storing coverages and creating relationships between coverages, insured items, and root products in the quote data model.
-   **[Insurance Insured Items](https://help.salesforce.com/s/articleView?id=ind.insurance_vlocity_insurance_insured_items_614670.htm&language=en_US&type=5)**  
    The insured item data in the quote gets pulled from the insured item specs associated with the root product that's been quoted.

Did this article solve your issue?

Let us know so we can improve!

YesNo