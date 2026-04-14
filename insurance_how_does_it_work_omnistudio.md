---
title: "How Does Quote Creation from the Broker Experience Site Work?"
source: "https://help.salesforce.com/s/articleView?id=ind.insurance_how_does_it_work_omnistudio.htm&language=en_US&type=5"
scraped: "2026-04-14"
filter: "ind.insurance_"
---# How Does Quote Creation from the Broker Experience Site Work?

How Does Quote Creation from the Broker Experience Site Work?[](https://help.salesforce.com/s?language=en_US)

You are here:

1.  [Salesforce Help](/s/?language=en_US)
2.  [Docs](/s/products?language=en_US)
3.  [Digital Insurance](https://help.salesforce.com/s/articleView?id=ind.insurance_admin_standard.htm&language=en_US&type=5)

# How Does Quote Creation from the Broker Experience Site Work?

Quote creation is powered by our Create Quote OmniScript. You can find the Create Quote OmniScript in the OmniScript Designer listed under:

-   Type/SubType - insBroker/CreateQuote
    
-   OmniScript Name - Create Quote
    

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

LWCMatchorCreateAccount1

 | 

OmniScript

 | 

Creates a new account or finds an existing account to be used to create the new quote.

 | 

LWCMatchorCreateAccount

 |
| 

quoteDetailsSection

 | 

Step

 | 

Gathers information from the user about effective date, term, and address.

 | 

None

 |
| 

createAccountOppty

 | 

Omnistudio Data Mapper Post Action

 | 

Creates an opportunity for the account.

 | 

ins\_createAccountOppty\_CreateQuote

 |
| 

getAccOppInformation

 | 

Data Mapper Extract Action

 | 

Extracts the account and opportunity details to create the quote.

 | 

Ins\_ReadAccountAndOpportunityDetails\_QuoteCreationOS

 |
| 

getRatedProductsDetails

 | 

Remote Action

 | 

Calls the getRatedProducts method to retrieve a list of available products

 | 

None

 |
| 

setEditBlockWithPrefilledValues

 | 

Set Values

 | 

Sets the values of the available products that were retrieved by getRatedProducts method

 | 

None

 |
| 

selectProduct

 | 

Step

 | 

Displays the available products for the quote

 | 

None

 |
| 

createQuote

 | 

Integration Procedure Action

 | 

Creates a quote record and updates the product details in the quote

 | 

QuoteCreation

 |
| 

confirmQuote

 | 

Step

 | 

Displays a confirmation when the quote is created.

 | 

None

 |

Did this article solve your issue?

Let us know so we can improve!

YesNo