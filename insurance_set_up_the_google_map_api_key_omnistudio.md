---
title: "Set up the Google Map API Key"
source: "https://help.salesforce.com/s/articleView?id=ind.insurance_set_up_the_google_map_api_key_omnistudio.htm&language=en_US&type=5"
scraped: "2026-04-14"
filter: "ind.insurance_"
---# Set up the Google Map API Key

Set up the Google Map API Key[](https://help.salesforce.com/s?language=en_US)

You are here:

1.  [Salesforce Help](/s/?language=en_US)
2.  [Docs](/s/products?language=en_US)
3.  [Digital Insurance](https://help.salesforce.com/s/articleView?id=ind.insurance_admin_standard.htm&language=en_US&type=5)

# Set up the Google Map API Key

Use Google Map APIs to automatically populate address fields in the Property and Casualty application.

[](https://help.salesforce.com/s?language=en_US)Note

The Google Map API functionality is not bundled with Property and Casualty Application.

[](https://help.salesforce.com/s?language=en_US)

1.  Enable location services in your browser.
2.  In the App Launcher, search for OmniScript and open **Vlocity OmniScript Designer**.
3.  Using the Find in page bar, search for the OmniScript you want to modify and open its active version.
4.  Click **Deactivate Version**. This will take a couple of minutes.
5.  Locate the Type Ahead Block component that you want to enable the functionality for and open its **Properties**.
    
    For information on which OmniScripts and components you can modify in the Property and Casualty application, see this [table](https://help.salesforce.com/s/articleView?id=ind.insurance_set_up_the_google_map_api_key_omnistudio.htm&language=en_US&type=5#insurance_set_up_the_google_map_api_key_omnistudio__uuid-aa5fa92d-bd84-b35c-3c84-02e7e88977b0_informaltable-idm2663226938833078)
    
6.  Scroll down the Properties tab and deselect **Use data JSON**.
7.  In **GOOGLE MAPS AUTOCOMPLETE** , select **Enable Google Maps Autocomplete**.
8.  Enter the API Key in the **Google Maps API Key** field.
9.  [](https://help.salesforce.com/s?language=en_US)Click **Activate Version**.
    
    Here's a list of the OmniScripts and their respective components that support this functionality in the Property and Casualty application. By default, this functionality is disabled for all OmniScripts.
    
    | 
    Type/SubType
    
     | 
    
    OmniScript Name
    
     | 
    
    Element Name
    
     |
    | --- | --- | --- |
    | 
    
    **Account/EstablishAccount**
    
     | 
    
    **MatchorCreateAccountContacts**
    
     | 
    
    **AccountSearch**
    
    **newAddress**
    
     |
    | 
    
    **ins/SetupPaymentPlan**
    
     | 
    
    **PaymentPlanSetUp**
    
     | 
    
    **billingAddress**
    
     |
    | 
    
    **lwcAccount/UpdateBillingAddress**
    
     | 
    
    **AccountUpdateBillingAddress**
    
     | 
    
    **CurrentAddress**
    
    **BillingAddress**
    
     |
    | 
    
    **property/HomeQuote**
    
     | 
    
    **Homeowners Quote**
    
     | 
    
    **propertyAddress**
    
     |
    | 
    
    **watercraft/multiVesselQuote**
    
     | 
    
    **Marine - Multi Vessel**
    
     | 
    
    **mopAddress**
    
     |
    

Did this article solve your issue?

Let us know so we can improve!

YesNo