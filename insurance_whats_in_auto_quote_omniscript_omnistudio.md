---
title: "What's in Auto Quote OmniScript"
source: "https://help.salesforce.com/s/articleView?id=ind.insurance_whats_in_auto_quote_omniscript_omnistudio.htm&language=en_US&type=5"
scraped: "2026-04-14"
filter: "ind.insurance_"
---# What's in Auto Quote OmniScript

What's in Auto Quote OmniScript[](https://help.salesforce.com/s?language=en_US)

You are here:

1.  [Salesforce Help](/s/?language=en_US)
2.  [Docs](/s/products?language=en_US)
3.  [Digital Insurance](https://help.salesforce.com/s/articleView?id=ind.insurance_admin_standard.htm&language=en_US&type=5)

# What's in Auto Quote OmniScript

The Auto Quote is LWC Enabled. It's built using LWCs you can learn about in.[](https://help.salesforce.com/s?language=en_US)Insurance Lightning Web Component UI Development Kit

This is the complete structure of the Auto Quote OmniScript:

Here's a look at each component of the Auto Quote OmniScript, including the component type, the purpose of the component, and what the component calls:

1.  Set Defaults
    
    -   Component type: Set Values
        
    -   What it does: Sets default values
        
    -   Calls: None
        
2.  getContextType
    
    [](https://help.salesforce.com/s?language=en_US)
    -   Component type: Omnistudio Data Mapper Extract Action
        
    -   What it does: Extracts account Id, contact Id, and RecordType
        
    -   Calls: auto\_ExtRecordType Data Mapper
        
3.  readAccount
    
    [](https://help.salesforce.com/s?language=en_US)
    -   Component type: Data Mapper Extract Action
        
    -   What it does: Extracts an account Id
        
    -   Calls: auto\_ExtrPersAcctDetails\_QuoteOS Data Mapper
        
4.  readProducer
    
    [](https://help.salesforce.com/s?language=en_US)
    -   Component type: Data Mapper Extract Action
        
    -   What it does: Extracts a producer Id
        
    -   Calls: auto\_ExtrProducer\_QuoteOS
        
5.  intro
    
    [](https://help.salesforce.com/s?language=en_US)
    -   Component type: Step > Text Block
        
    -   What it does: Shows users intro text about auto insurance
        
    -   Calls: None
        
6.  ReusableDriverInput1
    
    [](https://help.salesforce.com/s?language=en_US)
    -   Component type: OmniScript
        
    -   What it does: Gathers information about each driver to be insured
        
    -   Calls: auto/ReusableDriverInput OmniScript
        
7.  ReusableVehicleInputNoServiceIntegration1
    
    [](https://help.salesforce.com/s?language=en_US)
    -   Component type: OmniScript
        
    -   What it does: Gathers information about each vehicle to be insured
        
    -   Calls: auto/ReusableVehicleInput
        
8.  AutoInsuredItems
    
    [](https://help.salesforce.com/s?language=en_US)
    -   Component type: Integration Procedure Action
        
    -   What it does: Merges the data about the drivers and vehicles
        
    -   Calls: Auto\_MergeInsuredItems Integration Procedure
        
9.  createUserInputs
    
    [](https://help.salesforce.com/s?language=en_US)
    -   Component type: Data Mapper Transform Action
        
    -   What it does: Formats the data JSON so that the InsProductService:getRatedProducts service can take it as input and rate the insurance product(s)
        
    -   Calls: auto\_TransForGetRatedProducts\_QuoteOS
        
10.  configure > configureProduct
     
     [](https://help.salesforce.com/s?language=en_US)
     -   Component type: Step > Custom LWC
         
     -   What it does: Provides a UI that lets the user configure the insured items, insured parties, and coverages on the rated product.
         
     -   Calls: vlocity\_ins\_\_insOsMultiInstanceGrandchildren LWC
         
11.  createUpdateQuote
     
     [](https://help.salesforce.com/s?language=en_US)
     -   Component type: Integration Procedure Action
         
     -   What it does: Creates a quote record.
         
     -   Calls: Auto\_CreateUpdateQuote Integration Procedure
         
12.  deCryptQuote
     
     [](https://help.salesforce.com/s?language=en_US)
     -   Component type: Remote Action
         
     -   What it does: Decrypts the data, if necessary.
         
     -   Calls: decryptIfNecessary
         
13.  readQuote
     
     [](https://help.salesforce.com/s?language=en_US)
     -   Component type: Data Mapper Extract Action
         
     -   What it does: Extracts data from the quote record just created.
         
     -   Calls: auto\_ReadQuote\_QuoteOS Data Mapper
         
14.  confirmQuote
     
     -   Component type: Step, which contains six components
         
     -   What it does: Several things, listed step-by-step below
         
     -   Calls: None at the Step level
         
     
     1.  txtThankYou
         
         -   Component type: Text Block
             
         -   What it does: Posts text thanking the user for getting a quote
             
         -   Calls: None
             
     2.  quoteConfirm
         
         [](https://help.salesforce.com/s?language=en_US)
         -   Component type: Custom LWC
             
         -   What it does: Displays information about the quote to the user
             
         -   Calls: vlocity\_ins\_\_insOsConfirmation LWC
             
     3.  txtUnderwritingReview
         
         [](https://help.salesforce.com/s?language=en_US)
         -   Component type: Text Block
             
         -   What it does: Tells the user that an underwriter needs to review their information before a quote can be given.
             
         -   Calls: None
             
     4.  underwritingRules
         
         [](https://help.salesforce.com/s?language=en_US)
         -   Component type: Custom LWC
             
         -   What it does: Runs the underwriting rules on the quote data to determine whether this quote needs to be reviewed by an underwriter.
             
         -   Calls: insOsProductRulesReviewExtended LWC
             
     5.  txtFooter
         
         [](https://help.salesforce.com/s?language=en_US)
         -   Component type: Text Block
             
         -   What it does: Gives the user contact info for the insurer.
             
         -   Calls: None
             
     6.  viewQuote
         
         [](https://help.salesforce.com/s?language=en_US)
         -   Component type: Navigate Action
             
         -   What it does: Lets the user navigate to see the full details fo the quote.
             
         -   Calls: None
             

Did this article solve your issue?

Let us know so we can improve!

YesNo