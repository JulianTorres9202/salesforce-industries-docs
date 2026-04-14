---
title: "Add Claim Loss Item Payments"
source: "https://help.salesforce.com/s/articleView?id=ind.insurance_claim_add_loss_item.htm&language=en_US&type=5"
scraped: "2026-04-14"
filter: "ind.insurance_"
---# Add Claim Loss Item Payments

Add Claim Loss Item Payments[](https://help.salesforce.com/s?language=en_US)

You are here:

1.  [Salesforce Help](/s/?language=en_US)
2.  [Docs](/s/products?language=en_US)
3.  [Digital Insurance](https://help.salesforce.com/s/articleView?id=ind.insurance_admin_standard.htm&language=en_US&type=5)

# Add Claim Loss Item Payments

Claims adjusters enter payment details when they intend to issue a payment for an item or injury involved in a claim.

### Required Editions

<table class="slds-table slds-table_bordered slds-m-bottom_small edition" lwc-3eigj2skqo3=""><colgroup lwc-3eigj2skqo3=""><col style="width:100%" lwc-3eigj2skqo3=""></colgroup><tbody lwc-3eigj2skqo3=""><tr class="" lwc-3eigj2skqo3=""><td style="vertical-align:top;" class="slds-cell-wrap" lwc-3eigj2skqo3=""><a title="Give users access to Claims Management features. Review the supported edition and permission sets for Claims Management." href="https://help.salesforce.com/s/articleView?id=ind.insurance_claim_perm_set_licenses.htm&amp;language=en_US&amp;type=5" lwc-3eigj2skqo3="">View supported editions.</a></td></tr></tbody></table>

| User Permissions Needed |
| --- |
| [View user permissions.](https://help.salesforce.com/s/articleView?id=ind.insurance_claim_perm_set_licenses.htm&language=en_US&type=5 "Give users access to Claims Management features. Review the supported edition and permission sets for Claims Management.") |

1.  From the App Launcher, find and select **Claims**.
2.  Select a claim from the list view.
3.  Navigate to the Claim Financials tab.
4.  Click the **Losses** tab.
5.  Select a coverage and click **Add Loss Item** .
6.  Enter the loss item details:
    
    | field | Description |
    | --- | --- |
    | Coverage | The related open coverage. |
    | Description | A brief description of the loss item. |
    | Payee | The person who receives a payment. |
    | Currency ISO Code | In orgs with multiple currencies enabled, the currency of the payment detail record. This currency applies to both the claim amount and the adjusted amount. |
    | Claimed Amount | The claimed amount for this loss. When you press Tab to advance from Claim Amount to the next field, Vlocity calculates the Adjusted Amount, taking into account any deductibles or limits that apply to this loss. The Adjustment Reason field (read-only) describes why the adjustment occurred to the claim amount. |
    | Adjusted Amount | The amount to pay when a payment is issued for the payment detail. Typically the adjusted amount is the claim amount minus any adjustments. Click **Calculate**. The system invokes the Calculate Adjustments API to automatically fill the final adjusted amount based on the configured logic and taking into account any deductibles or limits that apply to this loss. |
    | Adjustment Reason | The Adjustment Reason field (read-only) describes why the adjustment occurred to the claim amount. |
    
7.  Save your changes.

Did this article solve your issue?

Let us know so we can improve!

YesNo