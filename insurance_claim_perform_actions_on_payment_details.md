---
title: "Perform Actions on Payment Details"
source: "https://help.salesforce.com/s/articleView?id=ind.insurance_claim_perform_actions_on_payment_details.htm&language=en_US&type=5"
scraped: "2026-04-14"
filter: "ind.insurance_"
---# Perform Actions on Payment Details

Perform Actions on Payment Details[](https://help.salesforce.com/s?language=en_US)

You are here:

1.  [Salesforce Help](/s/?language=en_US)
2.  [Docs](/s/products?language=en_US)
3.  [Digital Insurance](https://help.salesforce.com/s/articleView?id=ind.insurance_admin_standard.htm&language=en_US&type=5)

# Perform Actions on Payment Details

A claim adjuster can pay, cancel, or delete payment details for a coverage.

### Required Editions

<table class="slds-table slds-table_bordered slds-m-bottom_small edition" lwc-3eigj2skqo3=""><colgroup lwc-3eigj2skqo3=""><col style="width:100%" lwc-3eigj2skqo3=""></colgroup><tbody lwc-3eigj2skqo3=""><tr class="" lwc-3eigj2skqo3=""><td style="vertical-align:top;" class="slds-cell-wrap" lwc-3eigj2skqo3=""><a title="Give users access to Claims Management features. Review the supported edition and permission sets for Claims Management." href="https://help.salesforce.com/s/articleView?id=ind.insurance_claim_perm_set_licenses.htm&amp;language=en_US&amp;type=5" lwc-3eigj2skqo3="">View supported editions.</a></td></tr></tbody></table>

| User Permissions Needed |
| --- |
| [View user permissions.](https://help.salesforce.com/s/articleView?id=ind.insurance_claim_perm_set_licenses.htm&language=en_US&type=5 "Give users access to Claims Management features. Review the supported edition and permission sets for Claims Management.") |

-   For Loss type claims, the Cancel action invokes the Cancel CCPD API that reverses the insurance policy limit tracking data to roll back the policy limit consumption. In addition to this, the API also deactivates any Claim Coverage Payment Adjustment (CCPA) records created due to the initial adjustments.
-   The Pay action handles the processing of payments for CCPD records. It invokes the Pay CCPD API that updates the CCPD status to Paid and checks policy limits to ensure the adjusted amount doesn't exceed the available limits. If the limits are within the threshold, the API processes the payment, creates Insurance Policy Limit Tracking records to account for limit consumption, and updates the payment summary. If any limit-based attribute is exceeded, the system blocks the payment.
-   The Delete action invokes the Delete CCPD API that removes the unpaid claim coverage payment details by updating the CCPD record status to Deleted. It also reverses the insurance policy limit tracking data to roll back consumption for the type Loss. In addition to this, it also deactivates any CCPAs created due to the initial adjustments.
-   For loss type claims, the Edit action calls the Edit Claim Coverage Payment Detail API that recalculates the adjusted amount and policy limit consumption. The API creates insurance policy limit tracking records to roll back previous consumption and track the revised consumption, deactivates old claim coverage payment adjustment records and creates new records for revised adjustment. Finally, the API updates the details in the claim coverage payment detail record. For expense type claims, the API updates the details in the claim coverage payment detail record without recalculating the adjustments or limits.
-   For loss type claims, the Pay Ex Gratia action calls the Pay Ex Gratia API. The API creates insurance policy limit tracking records to track limit consumption up to the permitted threshold. In the claim coverage payment detail record, the API saves the excess amount or units authorized and the reason that the adjuster provides, and sets the status of the record to Paid Ex Gratia.

1.  From the App Launcher, find and select **Claims**.
2.  Select a claim from the list view.
3.  Navigate to the Claim Financials tab.
4.  Click the **Losses** or **Expenses** tab.
5.  Click the action dropdown on a specific CCPD row.
6.  Select an available action such as Pay, Cancel, or Delete.
    
    After you take action, the loss or expense item status changes to reflect the next step in the financial workflow.
    

Actions can be conditional based on the status of the claim coverage payment detail record. For example, Cancel appears only if the record status is Paid. The Edit and Pay Ex Gratia actions only apply if the record status is Draft.

Did this article solve your issue?

Let us know so we can improve!

YesNo