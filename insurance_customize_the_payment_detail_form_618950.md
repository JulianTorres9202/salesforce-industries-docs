---
title: "Customize the Claim Loss Payment Detail Form"
source: "https://help.salesforce.com/s/articleView?id=ind.insurance_customize_the_payment_detail_form_618950.htm&language=en_US&type=5"
scraped: "2026-04-14"
filter: "ind.insurance_"
---# Customize the Claim Loss Payment Detail Form

Customize the Claim Loss Payment Detail Form[](https://help.salesforce.com/s?language=en_US)

You are here:

1.  [Salesforce Help](/s/?language=en_US)
2.  [Docs](/s/products?language=en_US)
3.  [Digital Insurance](https://help.salesforce.com/s/articleView?id=ind.insurance_admin_standard.htm&language=en_US&type=5)

# Customize the Claim Loss Payment Detail Form

Each line of business can involve different processes and data entry requirements. Account for these differences by configuring payment detail processes at the coverage spec level. Corresponding payment detail forms can then guide claims adjusters through expected interactions logically and consistently.

The payment detail form shows fields in this order:

-   **Description** and **Payee**, along with **Benefit Type** if it’s part of the coverage spec. Don't include these fields in custom field sets.
    
-   Custom fields configured in custom field sets.
    
-   **Claim Amount** or a **Calculate** button, as appropriate, and **Adjusted Amount**. Don't include **Adjusted Amount** in custom field sets.
    

Here's an example of payment details for Rental Car coverage. The Rental Car coverage spec is associated with a custom field set that has **Limit Unit Count** and **Limit Unit of Measure** fields, but not **Claim Amount**.

[](https://help.salesforce.com/s?language=en_US)This is an example of payment details for Bodily Injury & Property Damage coverage. The Bodily Injury & Property Damage coverage spec isn't associated with a custom field set.

Tip: You can configure the Add Payee button in the Payee field.

In Lightning App Builder, open the Claims Record page. On the Financials tab, select the Vlocity Claim Items component. For Add Payee OmniScript, enter the OmniScript that adds a payee.

If a coverage spec has attributes that use the **Benefit Type** field, the form displays a **Benefit Type** picklist.

Customizing the form involves:

-   Configuring a custom field set on the **Claim Coverage Payment Detail** object.
    
-   Using the **Insurance Configuration Setup** custom setting to associate the custom field set with a coverage spec.
    

Important

Don't edit the default Claim Coverage Payment Detail field set.

1.  Review your coverage specs and decide which ones require custom fields on the payment detail form.
    
    Note the coverage codes. You enter these codes when you link custom field sets to the coverage specs.
    
2.  From Setup, in Object Manager, find and select **Claim Coverage Payment Detail**.
3.  Click **Field Sets**, then click **New**.
4.  Enter a label and description.
5.  Drag fields to the field set list.
    
    Don't add **Description**, **Payee**, **Benefit Type** or **Adjusted Amount** to the field set.
    
6.  Click **Save**.
7.  In the Quick Find box, enter Custom Settings, and then select **Custom Settings**.
8.  Select **Insurance Configuration Setup**. Click **Manage**, then click **New**.
9.  Enter setting details and save changes.
    
    <table class="slds-table slds-table_bordered slds-m-bottom_small" lwc-3eigj2skqo3=""><colgroup lwc-3eigj2skqo3=""><col style="width:50%" lwc-3eigj2skqo3=""><col style="width:50%" lwc-3eigj2skqo3=""></colgroup><tbody lwc-3eigj2skqo3=""><tr class="" lwc-3eigj2skqo3=""><td style="vertical-align:top;" class="slds-cell-wrap" lwc-3eigj2skqo3=""><p style="margin-bottom:0;" lwc-3eigj2skqo3=""><strong class="uicontrol" lwc-3eigj2skqo3="">Name</strong></p></td><td style="vertical-align:top;" class="slds-cell-wrap" lwc-3eigj2skqo3=""><p style="margin-bottom:0;" lwc-3eigj2skqo3="">Enter <kbd lwc-3eigj2skqo3="">ClaimCoverage:</kbd> followed by a coverage spec code. For example, for a Rental Car coverage, enter <kbd lwc-3eigj2skqo3="">ClaimCoverage:autoRental</kbd> .</p></td></tr><tr class="" lwc-3eigj2skqo3=""><td style="vertical-align:top;" class="slds-cell-wrap" lwc-3eigj2skqo3=""><p style="margin-bottom:0;" lwc-3eigj2skqo3=""><strong class="uicontrol" lwc-3eigj2skqo3="">Setup Value</strong></p></td><td style="vertical-align:top;" class="slds-cell-wrap" lwc-3eigj2skqo3=""><p style="margin-bottom:0;" lwc-3eigj2skqo3="">Enter the name of the custom field set to associate with the coverage spec.</p></td></tr></tbody></table>
    

[](https://help.salesforce.com/s?language=en_US)

After you complete configuration tasks, the payment detail form shows the custom fields associated with the selected coverage.

Did this article solve your issue?

Let us know so we can improve!

YesNo