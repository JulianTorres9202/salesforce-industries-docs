---
title: "Contract Proposal OmniScript"
source: "https://help.salesforce.com/s/articleView?id=ind.insurance_contract_proposal_omniscript_omnistudio.htm&language=en_US&type=5"
scraped: "2026-04-14"
filter: "ind.insurance_"
---# Contract Proposal OmniScript

Contract Proposal OmniScript[](https://help.salesforce.com/s?language=en_US)

You are here:

1.  [Salesforce Help](/s/?language=en_US)
2.  [Docs](/s/products?language=en_US)
3.  [Digital Insurance](https://help.salesforce.com/s/articleView?id=ind.insurance_admin_standard.htm&language=en_US&type=5)

# Contract Proposal OmniScript

For the lines of business that need documents that contain the details of a contract (rather than or in addition to showing the contract details on the UI), this OmniScript can create proposal documents.

This OmniScript isn't meant to be used alone. It's called by the Contract Creation OmniScript in Group Voluntary Benefits Application.

[](https://help.salesforce.com/s?language=en_US)

## How It Works

The Contract Proposal OmniScript takes the contract data (created by previous steps in the flow that uses this OmniScript), creates a contract proposal document, and then makes it available to be emailed to the customer either as a PDF or as a Word/PowerPoint document.

[](https://help.salesforce.com/s?language=en_US)

## What's In It?

You can find the Contract Proposal OmniScript in the Vlocity OmniScript Designer as:

-   Type - InsGVB
    
-   Subtype - ContractProposal
    
-   OmniScript Name - Contract Proposal
    

Here's what the Contract Proposal OmniScript looks like:

Read on for more information about each of the components.

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

drGetTemplateId

 | 

Omnistudio Data Mapper Extract Action

 | 

Gets the document template that the OmniScript will use to create the contract documents.

 | 

Ins\_ReadDocumentTemplateId\_ContractProposalOS

 |
| 

setRequiredValues

 | 

Set Values

 | 

Maps values for elements that will be used to create and populate the document contents

 | 

None

 |
| 

setGenerationOptions

 | 

Set Values

 | 

Maps values for elements that will be used to create and display the document files in different formats

 | 

None

 |
| 

generateDocument > GenerateDocumentWord

 | 

Custom Lighting Web Component

 | 

Uses Vlocity CLM to generate a Word document

 | 

vlocity\_ins\_\_clmOsDocxGenerateDocument

 |
| 

generateDocument > EmailWordDocument

 | 

Email Action

 | 

Creates a button that on-click emails the Word format quote document to the specified contact list, in this case %EmployerInfromation:Email%

 | 

None

 |
| 

generateDocument > EmailPDFDocument

 | 

Email Action

 | 

Creates a button that on-click emails the PDF format quote document to the specified contact list, in this case %EmployerInfromation:Email%

 | 

None

 |

Did this article solve your issue?

Let us know so we can improve!

YesNo