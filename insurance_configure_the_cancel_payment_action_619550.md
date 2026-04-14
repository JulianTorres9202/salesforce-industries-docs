---
title: "Configure the Cancel Payment Action"
source: "https://help.salesforce.com/s/articleView?id=ind.insurance_configure_the_cancel_payment_action_619550.htm&language=en_US&type=5"
scraped: "2026-04-14"
filter: "ind.insurance_"
---# Configure the Cancel Payment Action

Configure the Cancel Payment Action[](https://help.salesforce.com/s?language=en_US)

You are here:

1.  [Salesforce Help](/s/?language=en_US)
2.  [Docs](/s/products?language=en_US)
3.  [Digital Insurance](https://help.salesforce.com/s/articleView?id=ind.insurance_admin_standard.htm&language=en_US&type=5)

# Configure the Cancel Payment Action

Configure your org with custom settings and an integration procedure to support canceling the payment made for a payment detail record.

Your configuration includes:

-   An integration procedure called `ClaimInitiateCancelPaymentIP`.
    
-   A custom setting called `ClaimInitiateCancelPaymentIP`.
    
-   A custom setting called `CancelButtonDisplayStatuses`.
    

After you complete configuration tasks, the `InsClaimItemService: cancelPayments` service can create offsetting tracking entries that effectively remove payments from claim financials and policy term standings.

1.  [](https://help.salesforce.com/s?language=en_US)Configure an integration procedure called `ClaimInitiateCancelPaymentIP`. Have this integration procedure accept as inputs either `PaymentId` from the Claim Payment Summary object or `ItemId` from the Claim Coverage Payment Detail object.
    
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
    
    Additionally, have the integration procedure invoke the appropriate processes when a user cancels a loss or expense payment. For example, the procedure can send a message to a payment gateway to notify the bank of the cancellation.
    
    Note the **Type** and **SubType** of your `ClaimInitiateCancelPaymentIP` integration procedure. You enter these values in a custom setting that you create next.
    
2.  From Setup, in the Quick Find box, enter Custom Settings, and then select **Custom Settings**.
3.  Next to **Insurance Configuration Setup**, click **Manage**.
4.  Click **New**.
5.  Configure a custom setting called `ClaimInitiateCancelPaymentIP`.
    
    For **Setup Value**, enter the **Type** and **SubType** of your **ClaimInitiateCancelPaymentIP** integration procedure. Use the format <`Type_SubType`\>.
    
6.  Click **Save**.
7.  Click **Back to List**, and then click **New** again.
8.  [](https://help.salesforce.com/s?language=en_US)Configure a custom setting called **CancelButtonDisplayStatuses**.
    
    For **Setup Value**, enter **Paid**. With this configuration, only payment detail records with a status of Paid show **Cancel Payment** in the payment action dropdown menu.
    
9.  Confirm that the user interface lets users click the **Cancel Payment** payment action new payment action only for the **Paid** payment detail status.
    
    If a claim's **Financials** tab doesn't show the action as expected, clear the session cache and reload the page.
    
    Make sure that individual payment details show the correct action, and that the action dropdown at the top of the page shows the action only if it applies to all the selected payment details. Also confirm that the cancellation process launches as expected for the new action.
    

Did this article solve your issue?

Let us know so we can improve!

YesNo