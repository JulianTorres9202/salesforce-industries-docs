---
title: "Automatic Vlocity State Transition Component Refresh"
source: "https://help.salesforce.com/s/articleView?id=ind.insurance_automatic_vlocity_state_transition_component_refresh_2.htm&language=en_US&type=5"
scraped: "2026-04-13"
filter: "ind.insurance_"
---# Automatic Vlocity State Transition Component Refresh

Automatic Vlocity State Transition Component Refresh[](https://help.salesforce.com/s?language=en_US)

You are here:

1.  [Salesforce Help](/s/?language=en_US)
2.  [Docs](/s/products?language=en_US)
3.  [Digital Insurance](https://help.salesforce.com/s/articleView?id=ind.insurance_admin_standard.htm&language=en_US&type=5)

# Automatic Vlocity State Transition Component Refresh

Use a PushTopic to automatically refresh the Vlocity State Transition component when the Status field of a record updates.

This task is optional and should only be completed if you use the Vlocity State Transaction component.

[](https://help.salesforce.com/s?language=en_US)Note If you do not enable a PushTopic for a State Transition component, you must update the component manually when the status of a record updates.

[](https://help.salesforce.com/s?language=en_US)

1.  Click the quick access menu (Setup gear icon), and click **Developer Console**.
2.  From the Debug menu, select **Open Execute Anonymous Window**.
3.  In the Enter Apex Code window, paste in the following Apex code, and replace the object and field names based on which object you want to update.
    
    For example, to enable a PushTopic for the Quote State Transition component, the Apex code would look like this:
    
    ```
    PushTopic pushTopic = new PushTopic();
    pushTopic.Name = 'QuoteStateEvent';
    pushTopic.Query = 'SELECT Id, Status FROM Quote';
    pushTopic.ApiVersion = 51.0;
    pushTopic.NotifyForOperationUpdate = true;
    pushTopic.NotifyForFields = 'Referenced';
    insert pushTopic;
    ```
    
    For the Claim Status State Transition component, it would look like this:
    
    ```
    PushTopic pushTopic = new PushTopic();
    pushTopic.Name = 'ClaimStateEvent';
    pushTopic.Query = 'SELECT Id, Status FROM Claim';
    pushTopic.ApiVersion = 51.0;
    pushTopic.NotifyForOperationUpdate = true;
    pushTopic.NotifyForFields = 'Referenced';
    insert pushTopic;
    ```
    
4.  Click **Execute**.

[](https://help.salesforce.com/s?language=en_US)

The State Transition component updates automatically when the status of the record changes.

SEE ALSO

[_Developer Guide_: PushTopic](https://developer.salesforce.com/docs/atlas.en-us.object_reference.meta/object_reference/sforce_api_objects_pushtopic.htm)

Did this article solve your issue?

Let us know so we can improve!

YesNo