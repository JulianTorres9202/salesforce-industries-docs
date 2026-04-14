---
title: "Configure the Request Ex Gratia Payment Action"
source: "https://help.salesforce.com/s/articleView?id=ind.insurance_configure_the_request_ex_gratia_payment_action_619782.htm&language=en_US&type=5"
scraped: "2026-04-14"
filter: "ind.insurance_"
---# Configure the Request Ex Gratia Payment Action

Configure the Request Ex Gratia Payment Action[](https://help.salesforce.com/s?language=en_US)

You are here:

1.  [Salesforce Help](/s/?language=en_US)
2.  [Docs](/s/products?language=en_US)
3.  [Digital Insurance](https://help.salesforce.com/s/articleView?id=ind.insurance_admin_standard.htm&language=en_US&type=5)

# Configure the Request Ex Gratia Payment Action

Configure a **Request Ex Gratia** payment action to streamline requests for ex gratia payments. When users click **Request Ex Gratia**, the action invokes an integration procedure that changes a payment detail status to **Ex Gratia Requested**. The action also invokes an approval process. For approved requests, a custom setting lets the limit class allow payments to post if they're over the limit.

Before You Begin

Get a head start with the Vlocity Actions DataPack for Payment Actions. It includes a **PaymentDetailRequestExGratiaAction** Vlocity Action that you can customize or use as a template. See [Download and Import Vlocity Actions DataPack for Payment Actions](https://help.salesforce.com/s/articleView?id=ind.insurance_download_and_import_vlocity_actions_datapack_forpayment_actions_619933.htm&language=en_US&type=5 "Get a head-start configuring custom payment actions that invoke your own front- and back-end processes when users click specific payment actions. Download and import a DataPack with Vlocity Actions to customize or use as templates.").

Your configuration includes:

[](https://help.salesforce.com/s?language=en_US)

-   A business process, typically an approval process, to run when users click **Request Ex Gratia**.
    
-   An integration procedure that updates the status of a payment detail record, and that launches your approval process.
    
-   A custom setting called **PayOverLimitStatuses** that specifies which payment detail statuses let the limit class allow payments to post if they're over the limit.
    
-   [](https://help.salesforce.com/s?language=en_US)The **PaymentDetailRequestExGratiaAction** Vlocity Action, which calls your integration procedure. This action also specifies which payment detail statuses show the **Request Ex Gratia** payment action.
    

1.  [](https://help.salesforce.com/s?language=en_US)Configure a business process, typically an approval process, to run when users click **Request Ex Gratia**.
2.  Create an integration procedure that:
    
    [](https://help.salesforce.com/s?language=en_US)
    
    -   [](https://help.salesforce.com/s?language=en_US)
        
        Accept as inputs either `PaymentId` from the Claim Payment Summary object or  `ItemId`  from the Claim Coverage Payment Detail object.
        
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
        
    -   Updates the status of a payment detail record to a value such as **Ex Gratia Requested**.
        
    -   Launches your approval process.
        
    
3.  From Setup, in the Quick Find box, enter Custom Settings, and then select **Custom Settings**.
4.  Next to **Insurance Configuration Setup**, click **Manage**.
5.  Click **New**.
6.  Configure a custom setting called PayOverLimitStatuses.
    
    For **Setup Value**, enter Ex Gratia Approved.
    
7.  From the App Launcher, find and select **Vlocity Actions**.
8.  Click **PaymentDetailRequestExGratiaAction**.
9.  Enter details about the payment action.
    
    | 
    **Vlocity Actions Name**
    
     | 
    
    **PaymentDetailRequestExGratiaAction**.
    
     |
    | --- | --- |
    | 
    
    **Applicable Type**
    
     | 
    
    **ClaimCoveragePaymentDetail**.
    
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
    
    [](https://help.salesforce.com/s?language=en_US)The payment status values that go along with this payment action. Users can click the payment action only if the claim payment status meets the filter criteria.
    
    [](https://help.salesforce.com/s?language=en_US)Let users click **Request Ex Gratia** only for unpaid payment detail records, not paid ones.
    
    [](https://help.salesforce.com/s?language=en_US)Format: Status IN (<value>, <value>, ..., <value>)
    
    [](https://help.salesforce.com/s?language=en_US)Example: Status IN (New, Open, Authority Denied)
    
     |
    | 
    
    [](https://help.salesforce.com/s?language=en_US)**Invocation Class Name**, **Invocation Method Name**
    
     | 
    
    Enter values that call the integration procedure you configured for the **Request Ex Gratia** payment action.
    
     |
    
10.  Confirm that the user interface lets users click the **Request Ex Gratia** payment action for the correct payment detail statuses.
     
     If a claim's **Financials** tab doesn't show the action as expected, clear the session cache and reload the page.
     
     Make sure that individual payment details show the action, and that the action dropdown at the top of the page shows the action only if it applies to all the selected payment details. Also confirm that the approval process launches as expected for the new action.
     

Did this article solve your issue?

Let us know so we can improve!

YesNo