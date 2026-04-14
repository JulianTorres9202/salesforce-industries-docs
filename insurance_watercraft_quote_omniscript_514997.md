---
title: "Watercraft Quote OmniScript"
source: "https://help.salesforce.com/s/articleView?id=ind.insurance_watercraft_quote_omniscript_514997.htm&language=en_US&type=5"
scraped: "2026-04-14"
filter: "ind.insurance_"
---# Watercraft Quote OmniScript

Watercraft Quote OmniScript[](https://help.salesforce.com/s?language=en_US)

You are here:

1.  [Salesforce Help](/s/?language=en_US)
2.  [Docs](/s/products?language=en_US)
3.  [Digital Insurance](https://help.salesforce.com/s/articleView?id=ind.insurance_admin_standard.htm&language=en_US&type=5)

# Watercraft Quote OmniScript

Look under the hood of the Watercraft quote process with details of the quote OmniScript.

[](https://help.salesforce.com/s?language=en_US)

All our screenshots are currently in Lightning style. Your spin may look different because it's using the Newport style in the Broker Portal and Customer Portal.

The name of the watercraft quote OmniScript is:

-   Type/SubType: **watercraft/multiVesselQuote**
    
-   OmniScript name: **Marine - Multi Vessel**
    

[](https://help.salesforce.com/s?language=en_US)

You can launch this OmniScript from the following applications, where it can be accessed by the types of users described:

[](https://help.salesforce.com/s?language=en_US)

-   Broker Portal (Newport)
    
    For use by brokers and agents
    
-   Interaction Console (Lightning)
    
    Internal insurance agent
    
-   Vlocity Admin Lighting Experience (Newport)
    
    -   Internal insurance agent
        
    -   Vlocity admin
        

[](https://help.salesforce.com/s?language=en_US)

## How It Works

This section describes how someone who goes through the Marine Multi Vessel OmniScript to create a quote will see and interact with it.

The Marine Multi Vessel OmniScript starts with an intro page:

First, we gather information about the boats that will be insured. The fields in the form correspond to attributes in the insured item spec in the product model. In addition to basic info about each vessel, we ask questions that could have an impact on the rating. These questions also correspond to attributes on the insured item spec.

You can click **AutoFill** to fill out data quickly to test and learn about this flow.

The **Policy Start Date** defaults to today's date.

The next step gathers information about the marine operators who will be insured. The fields and choices here correspond to attributes on the insured party spec in the product model.

After all the info about vessels and the operator is complete, the OmniScript transforms the data to get it into the right format for the [InsProductService:getRatedProducts](https://help.salesforce.com/s/articleView?id=ind.insurance_insproductservice__getratedproducts.htm&language=en_US&type=5 "Use this service to get an array of one or more products, priced using rating procedures attached to those products. This service also includes extra features such as tax and fee calculations, filtering, and performance optimization.") service to use. It also calls Omnistudio Data Mapper transform actions to create or update the relevant account record.

Next, the insOsMultiInstanceGrandchildren Vlocity Lightning Web Component calls the [InsProductService:getRatedProducts](https://help.salesforce.com/s/articleView?id=ind.insurance_insproductservice__getratedproducts.htm&language=en_US&type=5 "Use this service to get an array of one or more products, priced using rating procedures attached to those products. This service also includes extra features such as tax and fee calculations, filtering, and performance optimization.") service and returns the rated insurance product. The user sees each vessel, with the quoted price.

On this page, users can open each vessel and configure attribute values on coverages. Each time a user changes an attribute value, the quoted price for the vessel is dynamically updated.

Still on the same page, users can select (and deselect) optional coverages.

At the bottom, this page shows the total price for the quote. The price changes dynamically every time the user makes a change to an attribute value or an optional coverage.

After you've finished, the OmniScript uses a Data Mapper transform action to transform the data into the right format for the [InsQuoteService:createUpdateQuote](https://help.salesforce.com/s/articleView?id=ind.insurance_insquoteservice__createupdatequote.htm&language=en_US&type=5 "Use this service to create a quote for new business, update an existing quote with new information, or create an endorsement quote. For updates, the quoteId of the quote to be updated must be included in the remote options.") service. Next, the OmniScript calls the [InsQuoteService:createUpdateQuote](https://help.salesforce.com/s/articleView?id=ind.insurance_insquoteservice__createupdatequote.htm&language=en_US&type=5 "Use this service to create a quote for new business, update an existing quote with new information, or create an endorsement quote. For updates, the quoteId of the quote to be updated must be included in the remote options.") service to generate a quote.

Finally, it displays a quote confirmation, which includes the quoted premium price.

[](https://help.salesforce.com/s?language=en_US)

## What's In It

The Marine Multi Vessel OmniScript is LWC Enabled.

Here's a look at each component of the Marine - Multi Vessel OmniScript, including the component type, the purpose of the component, and what the component calls:

1.  ipGetQuoteContext
    
    [](https://help.salesforce.com/s?language=en_US)
    -   Component type: Integration Procedure Action
        
    -   What it does: For the given account Id, extracts the context type. Context Id can be Person Account, Producer, or Business Account.
        
    -   Calls: ins\_GetQuoteContext
        
2.  readAccount
    
    [](https://help.salesforce.com/s?language=en_US)
    -   Component type: Data Mapper Extract Action
        
    -   What it does: Extracts an account Id when the context type is Person Account.
        
    -   Calls: wi\_ExtrPersAcctDetails\_QuoteOS
        
3.  readProducer
    
    [](https://help.salesforce.com/s?language=en_US)
    -   Component type: Data Mapper Extract Action
        
    -   What it does: Extracts a producer Id when the context type is Producer.
        
    -   Calls: wi\_ExtrProducer\_QuoteOS
        
4.  intro
    
    [](https://help.salesforce.com/s?language=en_US)
    -   Component type: Step > Text Block
        
    -   What it does: Shows users intro text about auto insurance.
        
    -   Calls: None
        
5.  crafts
    
    [](https://help.salesforce.com/s?language=en_US)
    -   Component type: Step
        
    -   What it does: Gathers information about the vessels to be insured. Includes various components that allow information to be entered in specific formats. Also includes the AutoFillVessels Set Values component to allow sample vessel details to be entered for test or demo purposes.
        
    -   Calls: None
        
6.  operator
    
    [](https://help.salesforce.com/s?language=en_US)
    -   Component type: Step
        
    -   What it does: Gathers information about the operator to be insured. Includes various components that allow information to be entered in specific formats. Also includes the AutoFillOperator Set Values component to allow sample operator details to be entered for test or demo purposes.
        
    -   Calls: None
        
7.  transformInsuredItems
    
    [](https://help.salesforce.com/s?language=en_US)
    -   Component type: Data Mapper Transform Action
        
    -   What it does: Formats the data JSON.
        
    -   Calls: wi\_TransInsureditems\_QuoteOS
        
8.  upsertPersAcctOppty
    
    -   Component type: Data Mapper Post Action
        
    -   What it does: Creates an account and an opportunity. This step is used when the corresponding person account doesn't already exist so both the account and the opportunity must be created.
        
    -   Calls: wi\_PostPersAcctOppty\_QuoteOS
        
9.  upsertPersOppty
    
    -   Component type: Data Mapper Post Action
        
    -   What it does: Creates an opportunity. This step is used when the corresponding person account already exists and only the opportunity must be created.
        
    -   Calls: wi\_PostPersOppty\_QuoteOS
        
10.  createUserInputs
     
     [](https://help.salesforce.com/s?language=en_US)
     -   Component type: Data Mapper Transform Action
         
     -   What it does: Formats the data JSON so that the [InsProductService:getRatedProducts](https://help.salesforce.com/s/articleView?id=ind.insurance_insproductservice__getratedproducts.htm&language=en_US&type=5 "Use this service to get an array of one or more products, priced using rating procedures attached to those products. This service also includes extra features such as tax and fee calculations, filtering, and performance optimization.") service can take it as input and rate the insurance product(s)
         
     -   Calls: wi\_TransForPrice\_QuoteOS
         
11.  configureCoverages > configureProduct
     
     [](https://help.salesforce.com/s?language=en_US)
     -   Component type: Step > Custom LWC
         
     -   What it does: Provides a UI that lets the user configure the insured items, insured parties, and coverages on the rated product.
         
     -   Calls: vlocity\_ins\_\_insOsMultiInstanceGrandchildren, which invokes the [AttributeRatingHandler:getRatedProducts](https://help.salesforce.com/s/articleView?id=ind.insurance_insproductservice__getratedproducts.htm&language=en_US&type=5 "Use this service to get an array of one or more products, priced using rating procedures attached to those products. This service also includes extra features such as tax and fee calculations, filtering, and performance optimization.") service
         
12.  transformtoQuote
     
     -   Component type: Data Mapper Transform Action
         
     -   What it does: Format the data JSON so that the [InsQuoteService:createUpdateQuote](https://help.salesforce.com/s/articleView?id=ind.insurance_insquoteservice__createupdatequote.htm&language=en_US&type=5 "Use this service to create a quote for new business, update an existing quote with new information, or create an endorsement quote. For updates, the quoteId of the quote to be updated must be included in the remote options.") service can take it as input and create the quote
         
     -   Calls: wi\_TransForQuote\_QuoteOS
         
13.  createQuote
     
     [](https://help.salesforce.com/s?language=en_US)
     -   Component type: Remote Action
         
     -   What it does: Creates a quote record.
         
     -   Calls: [InsQuoteService:createUpdateQuote](https://help.salesforce.com/s/articleView?id=ind.insurance_insquoteservice__createupdatequote.htm&language=en_US&type=5 "Use this service to create a quote for new business, update an existing quote with new information, or create an endorsement quote. For updates, the quoteId of the quote to be updated must be included in the remote options.")
         
14.  setStateTransition
     
     [](https://help.salesforce.com/s?language=en_US)
     -   Component type: Set Values
         
     -   What it does: Sets the state of the policy based on the status field of the quote object.
         
     -   Calls: auto\_ReadQuote\_QuoteOS Data Mapper
         
15.  QuoteWrapUp1
     
     -   Component type: OmniScript
         
     -   What it does: Invokes rules and displays the quote details and confirmation message.
         
     -   Calls: ins\_QuoteWrapUp
         

Did this article solve your issue?

Let us know so we can improve!

YesNo