---
title: "Add Claim Loss Payments"
source: "https://help.salesforce.com/s/articleView?id=ind.insurance_add_claim_loss_payments_620796.htm&language=en_US&type=5"
scraped: "2026-04-13"
filter: "ind.insurance_"
---# Add Claim Loss Payments

Add Claim Loss Payments[](https://help.salesforce.com/s?language=en_US)

You are here:

1.  [Salesforce Help](/s/?language=en_US)
2.  [Docs](/s/products?language=en_US)
3.  [Digital Insurance](https://help.salesforce.com/s/articleView?id=ind.insurance_admin_standard.htm&language=en_US&type=5)

# Add Claim Loss Payments

Claims adjusters enter payment details when they intend to issue a payment for an item or injury involved in a claim.

1.  On a claim, click the **Financials** tab, and then click **New Loss Item**.
2.  Enter loss item details.
    
    <table class="slds-table slds-table_bordered slds-m-bottom_small" lwc-3eigj2skqo3=""><colgroup lwc-3eigj2skqo3=""><col style="width:50%" lwc-3eigj2skqo3=""><col style="width:50%" lwc-3eigj2skqo3=""></colgroup><tbody lwc-3eigj2skqo3=""><tr class="" lwc-3eigj2skqo3=""><td style="vertical-align:top;" class="slds-cell-wrap" lwc-3eigj2skqo3=""><p style="margin-bottom:0;" lwc-3eigj2skqo3=""><strong class="uicontrol" lwc-3eigj2skqo3="">Coverage</strong></p></td><td style="vertical-align:top;" class="slds-cell-wrap" lwc-3eigj2skqo3=""><p style="margin-bottom:0;" lwc-3eigj2skqo3="">The related open coverage.</p></td></tr><tr class="" lwc-3eigj2skqo3=""><td style="vertical-align:top;" class="slds-cell-wrap" lwc-3eigj2skqo3=""><p style="margin-bottom:0;" lwc-3eigj2skqo3=""><strong class="uicontrol" lwc-3eigj2skqo3="">Description</strong></p></td><td style="vertical-align:top;" class="slds-cell-wrap" lwc-3eigj2skqo3=""><p style="margin-bottom:0;" lwc-3eigj2skqo3="">A brief description of the loss item.</p></td></tr><tr class="" lwc-3eigj2skqo3=""><td style="vertical-align:top;" class="slds-cell-wrap" lwc-3eigj2skqo3=""><p style="margin-bottom:0;" lwc-3eigj2skqo3=""><strong class="uicontrol" lwc-3eigj2skqo3="">Payee</strong></p></td><td style="vertical-align:top;" class="slds-cell-wrap" lwc-3eigj2skqo3=""><p style="margin-bottom:0;" lwc-3eigj2skqo3="">The person who receives a payment.</p></td></tr><tr class="" lwc-3eigj2skqo3=""><td style="vertical-align:top;" class="slds-cell-wrap" lwc-3eigj2skqo3=""><p style="margin-bottom:0;" lwc-3eigj2skqo3=""><strong class="uicontrol" lwc-3eigj2skqo3="">Benefit Type</strong></p></td><td style="vertical-align:top;" class="slds-cell-wrap" lwc-3eigj2skqo3=""><p lwc-3eigj2skqo3="">If benefit types are available for this claim coverage, the benefit type that applies.</p><p id="insurance_add_claim_loss_payments_620796__uuid-6916db8e-9130-13ea-44bb-6a1532c260f0_para-idm3304931058107129" style="margin-bottom:0;" lwc-3eigj2skqo3=""><a name="insurance_add_claim_loss_payments_620796__uuid-6916db8e-9130-13ea-44bb-6a1532c260f0_para-idm3304931058107129" lwc-3eigj2skqo3="" href="https://help.salesforce.com/s?language=en_US"></a>If there aren't benefit types available for this claim coverage, the <strong class="uicontrol" lwc-3eigj2skqo3="">Benefit Type</strong> field doesn't appear on the UI.</p></td></tr><tr class="" lwc-3eigj2skqo3=""><td style="vertical-align:top;" class="slds-cell-wrap" lwc-3eigj2skqo3=""><p style="margin-bottom:0;" lwc-3eigj2skqo3=""><strong class="uicontrol" lwc-3eigj2skqo3="">Currency</strong></p></td><td style="vertical-align:top;" class="slds-cell-wrap" lwc-3eigj2skqo3=""><p style="margin-bottom:0;" lwc-3eigj2skqo3="">In orgs with multiple currencies enabled, the currency of the payment detail record. This currency applies to both the claim amount and the adjusted amount.</p></td></tr><tr class="" lwc-3eigj2skqo3=""><td style="vertical-align:top;" class="slds-cell-wrap" lwc-3eigj2skqo3=""><p style="margin-bottom:0;" lwc-3eigj2skqo3=""><strong class="uicontrol" lwc-3eigj2skqo3="">Claim Amount</strong></p></td><td style="vertical-align:top;" class="slds-cell-wrap" lwc-3eigj2skqo3=""><p lwc-3eigj2skqo3="">The claim amount for this loss.</p><p id="insurance_add_claim_loss_payments_620796__uuid-6916db8e-9130-13ea-44bb-6a1532c260f0_para-idm3306574744142838" lwc-3eigj2skqo3=""><a name="insurance_add_claim_loss_payments_620796__uuid-6916db8e-9130-13ea-44bb-6a1532c260f0_para-idm3306574744142838" lwc-3eigj2skqo3="" href="https://help.salesforce.com/s?language=en_US"></a>When you press Tab to advance from Claim Amount to the next field, Vlocity calculates the <strong class="uicontrol" lwc-3eigj2skqo3="">Adjusted Amount</strong>, taking into account any deductibles or limits that apply to this loss.</p><p id="insurance_add_claim_loss_payments_620796__uuid-6916db8e-9130-13ea-44bb-6a1532c260f0_para-idm3308218430178547" style="margin-bottom:0;" lwc-3eigj2skqo3=""><a name="insurance_add_claim_loss_payments_620796__uuid-6916db8e-9130-13ea-44bb-6a1532c260f0_para-idm3308218430178547" lwc-3eigj2skqo3="" href="https://help.salesforce.com/s?language=en_US"></a>The <strong class="uicontrol" lwc-3eigj2skqo3="">Adjustment Reason</strong> field (read-only) describes why the adjustment occurred to the claim amount.</p></td></tr><tr class="" lwc-3eigj2skqo3=""><td style="vertical-align:top;" class="slds-cell-wrap" lwc-3eigj2skqo3=""><p id="insurance_add_claim_loss_payments_620796__uuid-6916db8e-9130-13ea-44bb-6a1532c260f0_para-idm3303290304082638" style="margin-bottom:0;" lwc-3eigj2skqo3=""><a name="insurance_add_claim_loss_payments_620796__uuid-6916db8e-9130-13ea-44bb-6a1532c260f0_para-idm3303290304082638" lwc-3eigj2skqo3="" href="https://help.salesforce.com/s?language=en_US"></a><strong class="uicontrol" lwc-3eigj2skqo3="">Adjusted Amount</strong></p></td><td style="vertical-align:top;" class="slds-cell-wrap" lwc-3eigj2skqo3=""><p style="margin-bottom:0;" lwc-3eigj2skqo3="">The amount to pay when a payment is issued for the payment detail. Typically the adjusted amount is the claim amount minus any adjustments.</p></td></tr></tbody></table>
    
    This **New Loss Item** form can be configured to show different fields. If the administrator configures the form without the **Claim Amount** field, the form shows a **Calculate** button.
    
    To learn how this form is configured, see [Customize the Claim Loss Payment Detail Form](https://help.salesforce.com/s/articleView?id=ind.insurance_customize_the_payment_detail_form_618950.htm&language=en_US&type=5 "Each line of business can involve different processes and data entry requirements. Account for these differences by configuring payment detail processes at the coverage spec level. Corresponding payment detail forms can then guide claims adjusters through expected interactions logically and consistently.").
    
    To learn about the logic used to calculate the adjusted amount when the Claim Amount field is removed from the form, see [InsClaimItemService:calculateCoverages](https://help.salesforce.com/s/articleView?id=ind.insurance_insclaimitemservice__calculatecoverages.htm&language=en_US&type=5 "Use this service to calculate the coverage amount and adjusted amount for a claim line item. These amounts are used as payment amount when the claims adjuster pays the claim line item.").
    
3.  Click **Add**.
    
    The loss item appears as a line item under the appropriate coverage.
    

Did this article solve your issue?

Let us know so we can improve!

YesNo