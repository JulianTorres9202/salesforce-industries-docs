---
title: "Configure Financial Workflows with Claim Payment Actions"
source: "https://help.salesforce.com/s/articleView?id=ind.insurance_configure_financial_workflows_with_claim_payment_actions.htm&language=en_US&type=5"
scraped: "2026-04-14"
filter: "ind.insurance_"
---# Configure Financial Workflows with Claim Payment Actions

Configure Financial Workflows with Claim Payment Actions[](https://help.salesforce.com/s?language=en_US)

You are here:

1.  [Salesforce Help](/s/?language=en_US)
2.  [Docs](/s/products?language=en_US)
3.  [Digital Insurance](https://help.salesforce.com/s/articleView?id=ind.insurance_admin_standard.htm&language=en_US&type=5)

# Configure Financial Workflows with Claim Payment Actions

A flexible framework supports standard and custom financial workflows based on the status of claim payments. Use the framework to provide a full slate of financial actions to claims adjusters, from initial payments, through approval processes and payment issuance, to payment cancellations.

Administrators can:

-   Configure payment detail status values: Open, Pending Authority, Authority Approved, Ex Gratia Approved, and Paid.
    
-   Configure relevant payment actions to show users for each payment detail status: Edit, Delete, Pay, Request Financial Authority, Request Ex Gratia Approval, and Cancel Payment.
    
-   Launch a back-end process or user interface when users click a specific payment action. For example, an integration procedure can change a payment detail status to Pending Authority, and then invoke an approval process.
    
-   Seamlessly embed workflows into the existing Claim Financials user interface.
    

After everything is configured, claims adjusters can choose from a list of payment actions tailored for each status. Approval requests and payment cancellation processes kick off automatically.

[](https://help.salesforce.com/s?language=en_US)**Where:** Available in Spring '22 and later releases.

**Why:** Folding your financial processes into the claims workflow can reduce project implementation costs, tighten financial controls, and improve user adoption of claims financial tools.

**How:** Configure payment detail statuses and payment actions for each status. Then configure processes to run when users click a specific payment action.

Claims adjusters see the appropriate payment actions for each payment detail. If a user selects several payment details, the only actions available to click are those that apply to all selected payment details based on status.

## See Also

[Configure Payment Actions Based on Claim Payment Status](https://help.salesforce.com/s/articleView?id=ind.insurance_configure_payment_actions_based_on_claim_payment_status_619416.htm&language=en_US&type=5 "Use a flexible framework to provide a full slate of financial actions to claims adjusters. The framework supports standard and custom financial workflows based on the status of claim payments. Configure payment actions to support initial payments, approval processes and payment issuance, and payment cancellations.")

Did this article solve your issue?

Let us know so we can improve!

YesNo