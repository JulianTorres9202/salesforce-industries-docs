---
title: "Create Inbound Quote from An External System"
source: "https://help.salesforce.com/s/articleView?id=ind.insurance_create_inbound_quote_from_an_external_system.htm&language=en_US&type=5"
scraped: "2026-04-14"
filter: "ind.insurance_"
---# Create Inbound Quote from An External System

Create Inbound Quote from An External System[](https://help.salesforce.com/s?language=en_US)

You are here:

1.  [Salesforce Help](/s/?language=en_US)
2.  [Docs](/s/products?language=en_US)
3.  [Digital Insurance](https://help.salesforce.com/s/articleView?id=ind.insurance_admin_standard.htm&language=en_US&type=5)

# Create Inbound Quote from An External System

Use `InsQuoteService:createUpdateQuoteFromExternal` service to create a quote or update an existing quote with new information through an inbound API call from an external policy admin system.

**When:** This feature is available from Vlocity Insurance Winter '22.

**Why:** You can now integrate an external policy admin system with the Salesforce insurance platform.

**How:** You can use both the simplified or the normal quote json. Use the `[InsQuoteService:createUpdateQuote](https://help.salesforce.com/s/articleView?id=ind.insurance_insquoteservice__createupdatequote.htm&language=en_US&type=5 "Use this service to create a quote for new business, update an existing quote with new information, or create an endorsement quote. For updates, the quoteId of the quote to be updated must be included in the remote options.")` if you aren’t using the simplified json. To get the simplified JSON structure that the external system must map to, set these newly introduced parameters in the `[InsQuoteService:getQuoteDetail](https://help.salesforce.com/s/articleView?id=ind.insurance_insquoteservice__getquotedetail.htm&language=en_US&type=5 "Use this service to get all of the quote details as JSON.")` service:

-   `isForExternal` = true
    
-   `action` = submit or reprice
    

Did this article solve your issue?

Let us know so we can improve!

YesNo