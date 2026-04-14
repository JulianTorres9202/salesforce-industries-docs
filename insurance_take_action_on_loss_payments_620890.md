---
title: "Take Action on Loss Payments"
source: "https://help.salesforce.com/s/articleView?id=ind.insurance_take_action_on_loss_payments_620890.htm&language=en_US&type=5"
scraped: "2026-04-14"
filter: "ind.insurance_"
---# Take Action on Loss Payments

Take Action on Loss Payments[](https://help.salesforce.com/s?language=en_US)

You are here:

1.  [Salesforce Help](/s/?language=en_US)
2.  [Docs](/s/products?language=en_US)
3.  [Digital Insurance](https://help.salesforce.com/s/articleView?id=ind.insurance_admin_standard.htm&language=en_US&type=5)

# Take Action on Loss Payments

A claims adjuster can choose from a full slate of financial actions, from initial payments, through approval processes and payment issuance, to payment cancellations.

1.  On a claim, click the **Financials** tab, and then expand the coverage with the loss item to process.
2.  Take action on one or more losses.
    
    For a single item, click **Pay** or select a different action from the dropdown menu. You can choose from a list of payment actions tailored for each status. For payment cancellations, offsetting tracking entries effectively remove the payment from claim financials and policy term standings.
    
    Don't edit the Coverage field if adjustments have already been made and saved, because this can corrupt the policy term data. To associate the loss item with a new coverage, delete the existing Claim Coverage Payment Detail (CCPD) record and create one.
    
    To pay many losses at once, select them manually or click **Select All Payable Items** in the dropdown menu at the top of the tab. Make sure only losses are selected, then click **Pay** from the same dropdown menu to pay them. Other actions available in the top dropdown menu are those that apply to all selected payment details based on status.
    
    [](https://help.salesforce.com/s?language=en_US)After you take action, the payment detail status changes to reflect the next step in the financial workflow. For example, status can change from **Open** to **Pending Authority**, or from **Authority Approved** to **Paid**.
    
    Note
    
    [](https://help.salesforce.com/s?language=en_US)If any coverage limit is exceeded without ex gratia approval, the page shows an error and none of the selected items get paid. For details about ex gratia configuration, see [Configure the Request Ex Gratia Payment Action](https://help.salesforce.com/s/articleView?id=ind.insurance_configure_the_request_ex_gratia_payment_action_619782.htm&language=en_US&type=5 "Configure a Request Ex Gratia payment action to streamline requests for ex gratia payments. When users click Request Ex Gratia, the action invokes an integration procedure that changes a payment detail status to Ex Gratia Requested. The action also invokes an approval process. For approved requests, a custom setting lets the limit class allow payments to post if they're over the limit.").
    

Did this article solve your issue?

Let us know so we can improve!

YesNo