---
title: "Create Quote from Account"
source: "https://help.salesforce.com/s/articleView?id=ind.insurance_t_create_quote_from_account_517945.htm&language=en_US&type=5"
scraped: "2026-04-14"
filter: "ind.insurance_"
---# Create Quote from Account

Create Quote from Account[](https://help.salesforce.com/s?language=en_US)

You are here:

1.  [Salesforce Help](/s/?language=en_US)
2.  [Docs](/s/products?language=en_US)
3.  [Digital Insurance](https://help.salesforce.com/s/articleView?id=ind.insurance_admin_standard.htm&language=en_US&type=5)

# Create Quote from Account

If you are a broker or an internal user who creates policies for others, then we have some great news for you! You can now quickly create an Auto, Marine or Property quote from the account page with just a few clicks. Read on to see how it works.

You can create a quote in two ways:

-   OmniScript Flow
    
-   Quote UI Object
    

[](https://help.salesforce.com/s?language=en_US)

## OmniScript Flow

The OmniScript can be accessed from the OmniScript Designer under:

-   Type - **insWC/CreateQuote**
    
-   Version - **create Oppty and Quote**
    

You can launch the OmniScript from certain application where it can be accessed by:

| 
Application

 | 

Accessed By

 |
| --- | --- |
| 

Interaction Console

 | 

Internal Insurance Agent

 |
| 

Admin Lightning Experience

 | 

Internal Insurance Agent

Vlocity Admin

 |

[](https://help.salesforce.com/s?language=en_US)

## What's In It

Here's what goes on behind the scenes of the OmniScript:

| 
Component

 | 

What It Is

 | 

What It Does

 | 

What It Calls

 |
| --- | --- | --- | --- |
| 

readPersonAccount

 | 

Omnistudio Data Mapper Extract Action

 | 

Retrieves details from the person account.

 | 

ReadPersonAccount

 |
| 

newOpportunity

 | 

Step

 | 

Gathers details about the opportunity.

 | 

None

 |
| 

setProductCode

 | 

Set Values

 | 

Based on the details entered, this component sets the value of the product code.

 | 

None

 |
| 

setDefaults

 | 

Set Values

 | 

Sets values for the account ID and the product.

 | 

None

 |
| 

createQuoteandOppty

 | 

Integration Procedure

 | 

Retrieves the rated products, creates the opportunity and quote.

 | 

createQuoteandOppty

 |
| 

viewQuote

 | 

Navigate Action

 | 

Navigates to the newly created quote

 | 

None

 |

## Quote UI Object

To create a quote from the UI, go to Actions on the account of the person you want to create a quote for, then click Create Quote. Enter all the required information and click Done.The quote is created and you can proceed with adding products and policies.

Did this article solve your issue?

Let us know so we can improve!

YesNo