---
title: "Configure Custom Payment Actions"
source: "https://help.salesforce.com/s/articleView?id=ind.insurance_configure_custom_payment_actions_619631.htm&language=en_US&type=5"
scraped: "2026-04-14"
filter: "ind.insurance_"
---# Configure Custom Payment Actions

Configure Custom Payment Actions[](https://help.salesforce.com/s?language=en_US)

You are here:

1.  [Salesforce Help](/s/?language=en_US)
2.  [Docs](/s/products?language=en_US)
3.  [Digital Insurance](https://help.salesforce.com/s/articleView?id=ind.insurance_admin_standard.htm&language=en_US&type=5)

# Configure Custom Payment Actions

Configure custom actions that invoke your own front- and back-end processes when users click specific payment actions. For example, configure a custom **Request Authority** payment action to invoke an integration procedure that changes a payment detail status to **Pending Authority**, and that invokes an approval process.

Before You Begin

Get a head start with the Vlocity Actions DataPack for Payment Actions. It includes a **PaymentDetailRequestAuthorityAction** Vlocity Action that you can customize or use as a template. See [Download and Import Vlocity Actions DataPack for Payment Actions](https://help.salesforce.com/s/articleView?id=ind.insurance_download_and_import_vlocity_actions_datapack_forpayment_actions_619933.htm&language=en_US&type=5 "Get a head-start configuring custom payment actions that invoke your own front- and back-end processes when users click specific payment actions. Download and import a DataPack with Vlocity Actions to customize or use as templates.").

You can also use a **Request Ex Gratia** Vlocity Action included with your org. See [Configure the Request Ex Gratia Payment Action](https://help.salesforce.com/s/articleView?id=ind.insurance_configure_the_request_ex_gratia_payment_action_619782.htm&language=en_US&type=5 "Configure a Request Ex Gratia payment action to streamline requests for ex gratia payments. When users click Request Ex Gratia, the action invokes an integration procedure that changes a payment detail status to Ex Gratia Requested. The action also invokes an approval process. For approved requests, a custom setting lets the limit class allow payments to post if they're over the limit.").

1.  [](https://help.salesforce.com/s?language=en_US)Configure a business process, typically an approval process, for your custom payment action.
    
    For example, if you plan to use the **PaymentDetailRequestAuthorityAction** Vlocity Action, configure an approval process to run when users click **Request Authority**.
    
2.  Create an integration procedure associated with this payment action.
    
    For example, if you're configuring the **PaymentDetailRequestAuthorityAction** Vlocity Action, create an integration procedure that:
    
    [](https://help.salesforce.com/s?language=en_US)
    
    -   [](https://help.salesforce.com/s?language=en_US)
        
        Accept as input either `PaymentId` from the Claim Payment Summary object or `ItemId`  from the Claim Coverage Payment Detail object.
        
        Format the JSON structure like this:
        
        ```json
        {
          "itemIds": [
            {
              "Id": "0l25c000000CalvAAC"
            },
            {
              "Id": "0l25c000000CalvAAC"
            }
          ]
        }
        ```
        
    -   Updates the status of a payment detail record to a value such as **Authority Requested**.
        
    -   Launches your approval process.
        
    
3.  From the App Launcher, find and select **Vlocity Actions**.
4.  Click **New** to add a custom payment action, or click an action in the list to edit it.
5.  Enter details about the payment action.
    
    | 
    **Vlocity Actions Name**
    
     | 
    
    A description of the payment action.
    
     |
    | --- | --- |
    | 
    
    **Applicable Type**
    
     | 
    
    Remove **All** from the Chosen list, and add **ClaimCoveragePaymentDetail**.
    
    [](https://help.salesforce.com/s?language=en_US)If **ClaimCoveragePaymentDetail** is missing from the list, go to Object Manager and open **Vlocity Action**. Then add **ClaimCoveragePaymentDetail** as a picklist value to the **Applicable Type** field.
    
     |
    | 
    
    **Display Label**
    
     | 
    
    The label to show users for this action.
    
     |
    | 
    
    [](https://help.salesforce.com/s?language=en_US)**Filter**
    
     | 
    
    [](https://help.salesforce.com/s?language=en_US)The payment status values that go along with this payment action. Users can click the payment action only if the payment detail status meets the filter criteria.
    
    If you're configuring the **PaymentDetailRequestAuthorityAction** Vlocity Action, specify which unpaid payment detail statuses show the **Request Authority** payment action.
    
    [](https://help.salesforce.com/s?language=en_US)Format: Status IN ('<value>', '<value>', ..., '<value>')
    
    [](https://help.salesforce.com/s?language=en_US)Example: Status IN ('New', 'Open', 'Authority Denied')
    
     |
    | 
    
    **Target URL**
    
    or
    
    [](https://help.salesforce.com/s?language=en_US)**Invocation Class Name**, **Invocation Method Name**
    
     | 
    
    Use these fields to configure either a front-end or back-end process.
    
    -   For a front-end process, for **Target URL**, enter the URL of an OmniScript to launch when the user clicks the payment action.
        
    -   For a back-end process, for **Invocation Class Name** and **Invocation Method Name**, enter the class and method names for the remote action to launch when the user clicks the payment action.
        
    
    If you're configuring the **PaymentDetailRequestAuthorityAction** Vlocity Action, have it call the integration procedure you configured for the **Request Authority** payment action.
    
     |
    
6.  Confirm that the user interface lets users click the payment action for the correct claim payment statuses.
    
    If a claim's **Financials** tab doesn't show the action, clear the session cache and reload the page.
    
    Make sure that individual payment details show the action, and that the action dropdown at the top of the page shows the action only if it applies to all the selected payment details. Also confirm that front- and back-end processes launch as expected for the new action.
    

[](https://help.salesforce.com/s?language=en_US)

Users who process claims can select the payment action if selected claim payment detail statuses meet the filter criteria for that action.

Did this article solve your issue?

Let us know so we can improve!

YesNo