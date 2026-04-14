---
title: "Set Up an Integration Procedure to Call an External Rating System"
source: "https://help.salesforce.com/s/articleView?id=ind.insurance_set_up_an_integration_procedure_to_call_an_external_rating_system_613940.htm&language=en_US&type=5"
scraped: "2026-04-14"
filter: "ind.insurance_"
---# Set Up an Integration Procedure to Call an External Rating System

Set Up an Integration Procedure to Call an External Rating System[](https://help.salesforce.com/s?language=en_US)

You are here:

1.  [Salesforce Help](/s/?language=en_US)
2.  [Docs](/s/products?language=en_US)
3.  [Digital Insurance](https://help.salesforce.com/s/articleView?id=ind.insurance_admin_standard.htm&language=en_US&type=5)

# Set Up an Integration Procedure to Call an External Rating System

To use Vlocity Insurance Open Quoting Architecture you need to create an integration procedure that gathers the important information your external policy administration system can use to rate or price the quote. This integration procedure is included in the product and is triggered when a quote with that product included is rerated using the Rate Now button.

Before You Begin

Make sure that your org is set up to call out to the external system’s endpoint by adding the site to the [Remote Site Settings](https://developer.salesforce.com/docs/atlas.en-us.apexcode.meta/apexcode/apex_callouts_remote_site_settings.htm).

1.  Create an [Integration Procedure](https://help.salesforce.com/s/articleView?id=xcloud.os_omnistudio_integration_procedures_48334.htm&language=en_US&type=5).
    
    Tip
    
    Make note of the Type/SubType. You need to add this information to the product you create.
    
2.  Use a Remote Action to invoke **InsQuoteService.getQuoteDetail** with the Remote Option Key/Value pair `isForExternal=true` to prepare the Quote JSON to send to the external system.
3.  Send the Quote JSON to the external system for the rating in one of these two ways:
    
    -   Use a Remote Action to call an Apex class that sends the request to the external system.
        
    -   Use an HTTP Action in the integration Procedure.
        
        Note
        
        When using an HTTP Action, the result might not include `“error”: “OK”` which `InsQuoteService:createUpdateQuoteFromExternal` or `InsQuoteService:createUpdateQuote` is expecting.
        
        You can manually add this through the Additional Output option of the HTTP Action.
        
    
4.  Use a Remote Action to invoke InsQuoteService:createUpdateQuoteFromExternal.
    
    This service takes the Input JSON data returned from the external system, and returns the `Quote.Id` of the created or updated quote in the output JSON and the list of errors encountered.
    
5.  Add a Response Action to return the Quote JSON with the pricing updates from the external system to the quoting flow. This is what is used to update the Quote details.
    
    The data returned from the external system must be in this format:
    
    ```json
    1 {
    2  "result": {
    3    "quote": {
    4      // Updated JSON returned
    5    },
    6    "errorCode": "INVOKE-200",
    7    "error": "OK"
    8  }
    9 }
    ```
    

[](https://help.salesforce.com/s?language=en_US)

[Set Up a Product for External Rating](https://help.salesforce.com/s/articleView?id=ind.insurance_set_up_a_product_for_external_rating_614013.htm&language=en_US&type=5 "External policy administration systems can help you manage your insurance product offerings. Vlocity Insurance Open Quoting Architecture uses a product record in the internal Vlocity Insurance system to link quoting information in the quoting flow to the correct product in your external system.")

Did this article solve your issue?

Let us know so we can improve!

YesNo