---
title: "Set up the Google Maps API Key"
source: "https://help.salesforce.com/s/articleView?id=ind.insurance_set_up_the_google_maps_api_key_omnistudio.htm&language=en_US&type=5"
scraped: "2026-04-14"
filter: "ind.insurance_"
---# Set up the Google Maps API Key

Set up the Google Maps API Key[](https://help.salesforce.com/s?language=en_US)

You are here:

1.  [Salesforce Help](/s/?language=en_US)
2.  [Docs](/s/products?language=en_US)
3.  [Digital Insurance](https://help.salesforce.com/s/articleView?id=ind.insurance_admin_standard.htm&language=en_US&type=5)

# Set up the Google Maps API Key

Did you know that the Group Voluntary Benefits Application supports Google Map APIs to automatically populate address fields?

[](https://help.salesforce.com/s?language=en_US)Note

The Google Map API functionality is not bundled with Group Voluntary Benefits Application.

[](https://help.salesforce.com/s?language=en_US)However, by default, this functionality is disabled for all OmniScripts. To enable the Google Map API functionality:

1.  Enable location services in your browser.
2.  In the App Launcher, search for OmniScript and open **Vlocity OmniScript Designer**.
3.  Using the Find in page bar, search for the OmniScript you want to modify and open its active version.
4.  Click **Deactivate Version**. This will take a couple of minutes.
5.  Locate the Type Ahead Block component that you want to enable the functionality for and open its **Properties**.
6.  Scroll down the Properties tab and deselect **Use data JSON**.
7.  In **GOOGLE MAPS AUTOCOMPLETE** , select **Enable Google Maps Autocomplete**.
8.  Enter the API Key in the **Google Maps API Key** field.
9.  Click **Activate Version**. And that's all there is to it!
    
    [](https://help.salesforce.com/s?language=en_US)Here's a list of the OmniScripts and their respective components that support this functionality in the Group Voluntary Benefits application.
    
    | 
    Type/SubType
    
     | 
    
    OmniScript Name
    
     | 
    
    Element Name
    
     |
    | --- | --- | --- |
    | 
    
    **InsAccount/UpdateBillingAddress**
    
     | 
    
    **AccountUpdateBillingAddress**
    
     | 
    
    **CurrentAddress**
    
    **Billing Address**
    
     |
    

Did this article solve your issue?

Let us know so we can improve!

YesNo