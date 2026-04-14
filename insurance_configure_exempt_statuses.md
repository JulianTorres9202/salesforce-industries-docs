---
title: "Exempt Statuses from Pending Payment Calculation"
source: "https://help.salesforce.com/s/articleView?id=ind.insurance_configure_exempt_statuses.htm&language=en_US&type=5"
scraped: "2026-04-14"
filter: "ind.insurance_"
---# Exempt Statuses from Pending Payment Calculation

Exempt Statuses from Pending Payment Calculation[](https://help.salesforce.com/s?language=en_US)

You are here:

1.  [Salesforce Help](/s/?language=en_US)
2.  [Docs](/s/products?language=en_US)
3.  [Digital Insurance](https://help.salesforce.com/s/articleView?id=ind.insurance_admin_standard.htm&language=en_US&type=5)

# Exempt Statuses from Pending Payment Calculation

Configure your org with custom settings to manage how pending payments in Claim Coverage Payment Detail (CCPD) records are calculated. Then, use these settings to make sure that the pending amount isn’t calculated for specific statuses. For example, you can configure a custom setting so that payment detail records in Approved for Payment status aren’t considered when calculating the pending amount.

### Required Editions

<table class="slds-table slds-table_bordered slds-m-bottom_small edition" lwc-3eigj2skqo3=""><colgroup lwc-3eigj2skqo3=""><col style="width:100%" lwc-3eigj2skqo3=""></colgroup><tbody lwc-3eigj2skqo3=""><tr class="" lwc-3eigj2skqo3=""><td style="vertical-align:top;" class="slds-cell-wrap" lwc-3eigj2skqo3="">Available in: Lightning Experience</td></tr><tr class="" lwc-3eigj2skqo3=""><td style="vertical-align:top;" class="slds-cell-wrap" lwc-3eigj2skqo3="">Available in: <strong lwc-3eigj2skqo3="">Professional</strong>, <strong lwc-3eigj2skqo3="">Enterprise</strong>, and <strong lwc-3eigj2skqo3="">Unlimited</strong> Editions with the Insurance Industries managed package and the Insurance Industries Extension managed package.</td></tr></tbody></table>

1.  From Setup, in the Quick Find box, find and select **Custom Settings**.
2.  Next to Insurance Configuration Setup, click **Manage**.
3.  Next to ExcludeStatusesForPayment, click **Edit**.
4.  For Setup Value, enter the payment detail statuses that are exempted from the pending amount calculation. Separate values with a comma. For example, your value can be Paid,Closed W/O Pay,Approved for Payment,Cancelled,Stopped,Voided.
    -   Use the API name of the status when specifying Setup Value.
    -   There are no restrictions on defining the API name if you plan to create a status other than the ones covered in this list. Use the default API names for these statuses: Paid,Closed W/O Pay,Cancelled,Stopped,Voided,Reverted,Authority Approved,Approved for Payment.
5.  Confirm that Policy Term Standing entries reflect accurate calculations for Used, Pending, and Remaining amounts.
6.  If a claim's Financials tab doesn't show the correct pending payment amount based on the excluded statuses, clear the session cache and reload the page.

Did this article solve your issue?

Let us know so we can improve!

YesNo