---
title: "Set Up a Product for External Rating"
source: "https://help.salesforce.com/s/articleView?id=ind.insurance_set_up_a_product_for_external_rating_614013.htm&language=en_US&type=5"
scraped: "2026-04-14"
filter: "ind.insurance_"
---# Set Up a Product for External Rating

Set Up a Product for External Rating[](https://help.salesforce.com/s?language=en_US)

You are here:

1.  [Salesforce Help](/s/?language=en_US)
2.  [Docs](/s/products?language=en_US)
3.  [Digital Insurance](https://help.salesforce.com/s/articleView?id=ind.insurance_admin_standard.htm&language=en_US&type=5)

# Set Up a Product for External Rating

External policy administration systems can help you manage your insurance product offerings. Vlocity Insurance Open Quoting Architecture uses a product record in the internal Vlocity Insurance system to link quoting information in the quoting flow to the correct product in your external system.

Each product in your external policy administration systems needs a corresponding product in your Vlocity Insurance org.

A product used with your external rating system must include three things:

1.  An External ID: This ID must match the product ID in your external system.
    
2.  A Rating Procedure Type: Set as Integration Procedure.
    
3.  A Rating Procedure Name: Set to the Type and Subtype of the Integration Procedure you created in [Set Up an Integration Procedure to Call an External Rating System](https://help.salesforce.com/s/articleView?id=ind.insurance_set_up_an_integration_procedure_to_call_an_external_rating_system_613940.htm&language=en_US&type=5 "To use Vlocity Insurance Open Quoting Architecture you need to create an integration procedure that gathers the important information your external policy administration system can use to rate or price the quote. This integration procedure is included in the product and is triggered when a quote with that product included is rerated using the Rate Now button.").
    
    Tip
    
    The input format for this field is: Type\_Subtype.
    

Did this article solve your issue?

Let us know so we can improve!

YesNo