---
title: "Change the API Keys for Google Map"
source: "https://help.salesforce.com/s/articleView?id=ind.insurance_change_the_api_keys_for_google_map_2.htm&language=en_US&type=5"
scraped: "2026-04-14"
filter: "ind.insurance_"
---# Change the API Keys for Google Map

Change the API Keys for Google Map[](https://help.salesforce.com/s?language=en_US)

You are here:

1.  [Salesforce Help](/s/?language=en_US)
2.  [Docs](/s/products?language=en_US)
3.  [Digital Insurance](https://help.salesforce.com/s/articleView?id=ind.insurance_admin_standard.htm&language=en_US&type=5)

# Change the API Keys for Google Map

You'll probably need to change the API key for the Google Map and weather objects on this component. You do this in the Integration Procedure.

1.  On the **SetAPIKeys** step of the Integration Procedure and change the value to the API keys for `googleMapsAPIKey` and `weatherAPIKey`.
2.  Verify that the **SetResponseValues** step still follows the JSON structure shown above.
    1.  Click **Edit as JSON** to see the full JSON response.
    2.  Verify that the structure remains correct.

Did this article solve your issue?

Let us know so we can improve!

YesNo