---
title: "Claim Coverages and Claim Financials"
source: "https://help.salesforce.com/s/articleView?id=ind.insurance_claim_coverages_and_claim_financials_620494.htm&language=en_US&type=5"
scraped: "2026-04-14"
filter: "ind.insurance_"
---# Claim Coverages and Claim Financials

Claim Coverages and Claim Financials[](https://help.salesforce.com/s?language=en_US)

You are here:

1.  [Salesforce Help](/s/?language=en_US)
2.  [Docs](/s/products?language=en_US)
3.  [Digital Insurance](https://help.salesforce.com/s/articleView?id=ind.insurance_admin_standard.htm&language=en_US&type=5)

# Claim Coverages and Claim Financials

Claims adjusters have quick access to tools that take a claim through processing to its resolution.

[](https://help.salesforce.com/s?language=en_US)

## Opening Claim Coverages and Setting Reserves

Claim coverages are opened systematically through product rules that run at the end of the FNOL flow. Claim coverages can also be opened by claim adjusters on existing claims. For example, if two vehicles are involved in a car accident, both a Collision and Property Damage claim coverage can be systemically opened with initial FNOL information. But an injury like whiplash can take days to appear and get diagnosed in a driver or passenger. So the claims adjuster opens the Bodily Injury coverage on the existing claim later.

Claims adjusters open coverages on the **Financials** tab. They're required to enter a loss reserve amount when they open a coverage on a claim. They have the option to enter an expense reserve amount when they open a coverage, or can do so later by clicking **Set Expense Reserve**. They can change reserve amounts anytime by clicking the pencil icon next to the amount.

To learn more, see [Open Coverages on a Claim](https://help.salesforce.com/s/articleView?id=ind.insurance_open_coverages_on_a_claim_620712.htm&language=en_US&type=5 "Coverages are the financial building blocks of a claim. After a claim coverage is opened, claims adjusters can track losses, payments, and expenses for that open coverage.").

Note

[](https://help.salesforce.com/s?language=en_US)The process of opening a claim coverage includes selecting the policy coverage to use to cover the loss. The Coverage field on the Open Coverage form shows the list of policy coverage records that exist for the insured item. For example, a Jaguar vehicle has Collision coverage on an auto policy. If the Jaguar is damaged in a car accident, the claims adjuster opens a claim coverage on the policy's Collision coverage. To learn more about how modeling works, see [Create Claim Product Models](https://help.salesforce.com/s/articleView?id=ind.insurance_create_claim_product_models_617529.htm&language=en_US&type=5 "A claim product model describes a claim that an insurance policyholder can file against an insurance policy.").

[](https://help.salesforce.com/s?language=en_US)

## Payment Details for Losses

Claims adjusters enter payment details when they intend to issue a payment for an item or injury involved in a claim.

To track these details, claims adjusters use the **New Loss Item** form on the **Financials** tab.

[](https://help.salesforce.com/s?language=en_US)Note

The form shows Currency only in orgs with multiple currencies enabled.

To learn how administrators can configure the payment detail form, see [Customize the Claim Loss Payment Detail Form](https://help.salesforce.com/s/articleView?id=ind.insurance_customize_the_payment_detail_form_618950.htm&language=en_US&type=5 "Each line of business can involve different processes and data entry requirements. Account for these differences by configuring payment detail processes at the coverage spec level. Corresponding payment detail forms can then guide claims adjusters through expected interactions logically and consistently.").

To learn how to record payment details, see [Add Claim Loss Payments](https://help.salesforce.com/s/articleView?id=ind.insurance_add_claim_loss_payments_620796.htm&language=en_US&type=5 "Claims adjusters enter payment details when they intend to issue a payment for an item or injury involved in a claim.").

[](https://help.salesforce.com/s?language=en_US)

## Expenses

Claims adjusters can add, edit, and delete expenses for open coverages as needed.

On the **Financials** tab, claims adjusters can click **New Expense Item** to add an expense.

[](https://help.salesforce.com/s?language=en_US)Note

The form shows Currency only in orgs with multiple currencies enabled.

To learn how, see [Add Claim Expense Payments](https://help.salesforce.com/s/articleView?id=ind.insurance_add_claim_expense_payments_620932.htm&language=en_US&type=5 "A claims adjuster can add new expense payment details to an open claim coverage.") and [Take Action on Expense Payments](https://help.salesforce.com/s/articleView?id=ind.insurance_take_action_on_expense_payments_620994.htm&language=en_US&type=5 "A claims adjuster can pay, edit, or delete expense payment details for a coverage.").

[](https://help.salesforce.com/s?language=en_US)

## Claims Financials in Multiple Currencies

In orgs with multiple currencies and advanced currency management enabled, claims adjusters can specify currency denomination when they set reserves, enter new losses and expenses, and make payments.

A functional hierarchy governs the display of default currencies and the way the system handles currency conversion.

Here’s the logic underlying the display of default currencies:

-   Claim records default to the currency of the policy on which the claim is created. The user who creates a claim can specify a different currency.
    
-   Claim coverages default to the currency of the claim on which they’re created. The user who opens the coverage can specify a different currency.
    
-   Loss and expense items default to the currency of the claim on which they’re created. The user who enters the loss or expense can specify a different currency.
    
-   A payment record is created in the currency of the claim coverage payment detail record that initiates the payment. Payment detail records can be grouped into the same payment as long as all the payment details use the same currency.
    

The Financial Summary user interface uses this currency conversion logic for display:

-   The Financial Summary converts payment amounts using the exchange rate that was active on the date the payment was made. For example, suppose a payment in euros (EUR) is made for a US dollar (USD) claim on March 20. The Financial Summary consistently displays the Payment in USD using the EUR:USD exchange rate from March 20, regardless of which day a user views the Financial Summary.
    
-   The Financial Summary converts reserve amounts using the current date’s exchange rates. For example, suppose claim coverage reserve is in Euros (EUR) on a US dollar (USD) claim. A user who views the Financial Summary on March 20 sees reserve amounts in USD that reflect the March 20 EUR:USD exchange rate. If the user views the Financial Summary again on March 25, the Financial Summary shows the reserve amounts in USD that reflect the March 25 EUR:USD exchange rate.
    

The Policy Terms Standing user interface uses this currency conversion logic for transactions:

-   For a deductible, the policy term's currency is converted into the payment detail's currency before a payment adjustment is applied. For example, a 5,000 EUR payment can get issued on a USD policy with a $500 deductible. If the EUR:USD exchange rate is 1:1.17, the system applies the deductible to the payment as 428 EUR, resulting in an adjusted payment amount is 4,572 EUR. But the policy terms are adjusted to reflect the full usage of the $500 deductible.
    
-   Limits work similarly. The system converts the payment amount into the policy term currency before tracking the consumption of the limit. For example, a 1,000,000 Japanese yen (JPY) payment can get issued against a $100,000 limit. If the USD:JPY exchange rate is 1:100, only $10,000 is tracked against the limit.
    

Here's the currency conversion logic used for reserve adjustments:

-   If a payment currency differs from the reserve currency, the system converts the payment amount to the reserve currency before applying the claim coverage reserve adjustment. For example, a 10,000 Japanese yen (JPY) payment can get issued against a $100,000 loss reserve. If the USD:JPY exchange rate is 1:100, a reserve adjustment of only $1,000 is created and the new loss reserve is $99,000.
    

See Salesforce Help for details about using multiple currencies and advanced currency management:

[](https://help.salesforce.com/s?language=en_US)

-   [Considerations for Enabling Multiple Currencies](https://help.salesforce.com/s/articleView?id=sales.admin_enable_multicurrency_implications.htm&language=en_US&type=5)
    
-   [About Advanced Currency Management](https://help.salesforce.com/s/articleView?id=sales.administration_about_advanced_currency_management.htm&language=en_US&type=5)
    
-   [Edit Dated Exchange Rates](https://help.salesforce.com/s/articleView?id=sf.administration_editing_effective_dated_exchange_rates.htm&language=en_US&type=5)
    

[](https://help.salesforce.com/s?language=en_US)

## Payments on Claim Coverages

Claims adjusters can use a full slate of financial actions, from initial payments, through approval processes and payment issuance, to payment cancellations. Flexible configuration options support the unique workflows that apply when a claim is open, pending approval, approved, or paid.

[](https://help.salesforce.com/s?language=en_US)On the **Financials** tab, users can:

[](https://help.salesforce.com/s?language=en_US)

-   Quickly identify what's open, pending approval, approved, or paid.
    
-   Choose from a list of payment actions tailored for each status. Approval requests and payment cancellation processes kick off automatically.
    
-   Take action on a single payment detail, or on several at once.
    

[](https://help.salesforce.com/s?language=en_US)To learn how administrators can configure payment actions, see [Configure Payment Actions Based on Claim Payment Status](https://help.salesforce.com/s/articleView?id=ind.insurance_configure_payment_actions_based_on_claim_payment_status_619416.htm&language=en_US&type=5 "Use a flexible framework to provide a full slate of financial actions to claims adjusters. The framework supports standard and custom financial workflows based on the status of claim payments. Configure payment actions to support initial payments, approval processes and payment issuance, and payment cancellations.").

[](https://help.salesforce.com/s?language=en_US)To learn how to process a payment, see [Take Action on Loss Payments](https://help.salesforce.com/s/articleView?id=ind.insurance_take_action_on_loss_payments_620890.htm&language=en_US&type=5 "A claims adjuster can choose from a full slate of financial actions, from initial payments, through approval processes and payment issuance, to payment cancellations.").

To learn how to use a payment authorization workflow to route requests for financial approval to the appropriate supervisors and managers, see [Build Business Processes for Payment Authorizations](https://help.salesforce.com/s/articleView?id=ind.insurance_finauth_build_bus_processes.htm&language=en_US&type=5 "Set limits on how much users can authorize for claim payments, and build a workflow that routes payment authorization requests to supervisors. Users authorized to approve larger amounts receive notifications of pending requests, link directly to claim details, and approve or reject financial transactions.").

[](https://help.salesforce.com/s?language=en_US)

## Financial Summary

Claims adjusters can monitor financials using charts that answer key questions: What are the losses worth and how much of the reserve is left? How much has been spent on loss and expenses payments? How do claim recoveries impact financial exposure? How much of the deductible or limit has a policyholder consumed?

[](https://help.salesforce.com/s?language=en_US)The **Financial Summary** panel of a claim answers these questions at a glance. It includes the:

[](https://help.salesforce.com/s?language=en_US)

-   **Financial Summary** chart.
    
-   **Policy Terms Standing** chart.
    

[](https://help.salesforce.com/s?language=en_US)The **Financial Summary** chart shows:

-   Pending Losses
    
    The total of all loss reserves or unpaid loss payment details on the claim, whichever is greater
    
-   Paid Losses
    
    The total of all loss payments on the claim that have been issued to the recipient
    
-   Pending Expenses
    
    The total of all expense reserves or unpaid expense payment details on the claim, whichever is greater
    
-   Paid Expenses
    
    The total of all expense payments on the claim that have been issued to the recipient
    
-   Pursued Recovery
    
    If your org tracks claim recoveries by using the Claim Recovery object, the recovery amount being pursued for this claim. See [Track Claim Recoveries](https://help.salesforce.com/s/articleView?id=ind.insurance_track_claim_recoveries_620011.htm&language=en_US&type=5 "Gain insight into claim recoveries and how pending and actual recoveries impact overall financial exposure. Maintain a complete history of each step of the recovery effort as team members pursue, accept, and seek additional recovery amounts.").
    
-   Accepted Recovery
    
    [](https://help.salesforce.com/s?language=en_US)If your org tracks claim recoveries by using the Claim Recovery object, the recovery amount accepted for this claim. See [Track Claim Recoveries](https://help.salesforce.com/s/articleView?id=ind.insurance_track_claim_recoveries_620011.htm&language=en_US&type=5 "Gain insight into claim recoveries and how pending and actual recoveries impact overall financial exposure. Maintain a complete history of each step of the recovery effort as team members pursue, accept, and seek additional recovery amounts.").
    
-   Financial Exposure
    
    The amount at the center of the chart, calculated as:
    
    Paid Losses + Pending Losses + Paid Expenses + Pending Expenses - (Pursued Recovery if applicable + Accepted Recovery if applicable)
    
    [](https://help.salesforce.com/s?language=en_US)Note
    
    You can configure chart settings to control how estimated and actual recovery amounts impact the overall financial exposure calculation. The calculation can include estimated recovery amounts, actual recovery amounts, or both. See [Configure the Claim Financial Summary](https://help.salesforce.com/s/articleView?id=ind.insurance_configure_the_claim_financial_summary_620121.htm&language=en_US&type=5 "Claims adjusters can monitor financials using charts that answer key questions: What are the losses worth and how much of the reserve is left? How much has been spent on loss and expenses payments? How do claim recoveries impact financial exposure? How much of the deductible or limit has a policyholder consumed?").
    

[](https://help.salesforce.com/s?language=en_US)The **Policy Terms Standing** chart shows the financial status of policy terms for this claim.

Several different definitions of policy terms are available out of the box including limits, deductibles, copay, and coinsurance. These terms are configured as power attributes and added to coverage specs or root products. To learn more about policy terms, see [Policy Terms as Power Attributes](https://help.salesforce.com/s/articleView?id=ind.insurance_policy_terms_as_power_attributes_617749.htm&language=en_US&type=5 "Enforce policy terms such as limits and deductibles by using power attributes. The \"power\" in power attributes comes from the extra metadata that you can configure for them. Insurance uses this metadata to track attributes as policy terms, from the product model to the policy record, and then on to claims against the policy.").

[](https://help.salesforce.com/s?language=en_US)Note

Hover over each bar to see the breakout of Used, Pending, and Remaining amounts (or counts).

Did this article solve your issue?

Let us know so we can improve!

YesNo