---
title: "Quote Proposal OmniScript"
source: "https://help.salesforce.com/s/articleView?id=ind.insurance_quote_proposal_omniscript_omnistudio.htm&language=en_US&type=5"
scraped: "2026-04-14"
filter: "ind.insurance_"
---# Quote Proposal OmniScript

Quote Proposal OmniScript[](https://help.salesforce.com/s?language=en_US)

You are here:

1.  [Salesforce Help](/s/?language=en_US)
2.  [Docs](/s/products?language=en_US)
3.  [Digital Insurance](https://help.salesforce.com/s/articleView?id=ind.insurance_admin_standard.htm&language=en_US&type=5)

# Quote Proposal OmniScript

For the lines of business that need documents that contain the details of a quote (rather than or in addition to showing the quote details on the UI), this OmniScript can create quote documents.

This OmniScript isn't meant to be used alone. It's called by other OmniScripts or UIs in the Property & Casualty Application Suites. They are:

-   Homeowners Quote OmniScript
    

[](https://help.salesforce.com/s?language=en_US)

## How It Works

The Quote Proposal OmniScript takes the quote data (created by previous steps in the flow that uses this OmniScript), creates a quote proposal document, and makes it available for emailing to the proposed customer either as a PDF or as a Word/PowerPoint document.

Here's what it looks like in the Homeowners Quote OmniScript:

[](https://help.salesforce.com/s?language=en_US)

## What's in It

The components are:

1.  drGetTemplateId
    
    -   Component type: Omnistudio Data Mapper Extract Action
        
    -   What it does: Gets the document template that the OmniScript will use to create the quote documents.
        
    -   Calls: **ins\_ExtDocumentTemplateId\_QuoteProposalOS**
        
2.  setRequiredValues
    
    -   Component type: Set Values
        
    -   What it does: Maps values for elements that will be used to create and populate the document contents
        
    -   Calls: None
        
3.  setGenerationOptions
    
    -   Component type: Set Values
        
    -   What it does: Maps values for elements that will be used to create and display the document files in different formats
        
    -   Calls: None
        
4.  generateDocument
    
    1.  GenerateDocumentWord
        
        -   Component type: Custom Lighting Web Component
            
        -   What it does: Uses Vlocity CLM to generate a Word document
            
        -   Calls: **vlocity\_ins\_\_clmOsDocxGenerateDocument**
            
    2.  EmailWordDocument
        
        -   Component type: Email Action
            
        -   What it does: Creates a button that on-click emails the Word format quote document to the specified contact list, in this case %proposalRecipientEmail%
            
        -   Calls: None
            
    3.  EmailPDFDocument
        
        -   Component type: Email Action
            
        -   What it does: Creates a button that on-click emails the PDF format quote document to the specified contact list, in this case %proposalRecipientEmail%
            
        -   Calls: None
            

Did this article solve your issue?

Let us know so we can improve!

YesNo