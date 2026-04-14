---
title: "Configure Payment Actions Based on Claim Payment Status"
source: "https://help.salesforce.com/s/articleView?id=ind.insurance_configure_payment_actions_based_on_claim_payment_status_619416.htm&language=en_US&type=5"
scraped: "2026-04-14"
filter: "ind.insurance_"
---# Configure Payment Actions Based on Claim Payment Status

Configure Payment Actions Based on Claim Payment Status[](https://help.salesforce.com/s?language=en_US)

You are here:

1.  [Salesforce Help](/s/?language=en_US)
2.  [Docs](/s/products?language=en_US)
3.  [Digital Insurance](https://help.salesforce.com/s/articleView?id=ind.insurance_admin_standard.htm&language=en_US&type=5)

# Configure Payment Actions Based on Claim Payment Status

Use a flexible framework to provide a full slate of financial actions to claims adjusters. The framework supports standard and custom financial workflows based on the status of claim payments. Configure payment actions to support initial payments, approval processes and payment issuance, and payment cancellations.

-   **[Configure Pay, Edit, and Delete Payment Actions](https://help.salesforce.com/s/articleView?id=ind.insurance_configure_payeditand_delete_payment_actions_619451.htm&language=en_US&type=5)**  
    Configure your org with custom settings for **Pay**, **Edit**, and **Delete** payment actions. These settings specify which payment details statuses show each payment action.
-   **[Configure the Cancel Payment Action](https://help.salesforce.com/s/articleView?id=ind.insurance_configure_the_cancel_payment_action_619550.htm&language=en_US&type=5)**  
    Configure your org with custom settings and an integration procedure to support canceling the payment made for a payment detail record.
-   **[Exempt Statuses from Pending Payment Calculation](https://help.salesforce.com/s/articleView?id=ind.insurance_configure_exempt_statuses.htm&language=en_US&type=5)**  
    Configure your org with custom settings to manage how pending payments in Claim Coverage Payment Detail (CCPD) records are calculated. Then, use these settings to make sure that the pending amount isn’t calculated for specific statuses. For example, you can configure a custom setting so that payment detail records in Approved for Payment status aren’t considered when calculating the pending amount.
-   **[Configure Custom Payment Actions](https://help.salesforce.com/s/articleView?id=ind.insurance_configure_custom_payment_actions_619631.htm&language=en_US&type=5)**  
    Configure custom actions that invoke your own front- and back-end processes when users click specific payment actions. For example, configure a custom **Request Authority** payment action to invoke an integration procedure that changes a payment detail status to **Pending Authority**, and that invokes an approval process.
-   **[Configure the Request Ex Gratia Payment Action](https://help.salesforce.com/s/articleView?id=ind.insurance_configure_the_request_ex_gratia_payment_action_619782.htm&language=en_US&type=5)**  
    Configure a **Request Ex Gratia** payment action to streamline requests for ex gratia payments. When users click **Request Ex Gratia**, the action invokes an integration procedure that changes a payment detail status to **Ex Gratia Requested**. The action also invokes an approval process. For approved requests, a custom setting lets the limit class allow payments to post if they're over the limit.
-   **[Download and Import Vlocity Actions DataPack for Payment Actions](https://help.salesforce.com/s/articleView?id=ind.insurance_download_and_import_vlocity_actions_datapack_forpayment_actions_619933.htm&language=en_US&type=5)**  
    Get a head-start configuring custom payment actions that invoke your own front- and back-end processes when users click specific payment actions. Download and import a DataPack with Vlocity Actions to customize or use as templates.

Did this article solve your issue?

Let us know so we can improve!

YesNo