---
title: "Extend the Prebuilt Expression Set to Perform Custom Processing of Limits"
source: "https://help.salesforce.com/s/articleView?id=ind.insurance_claim_custom_exp_set_lmts.htm&language=en_US&type=5"
scraped: "2026-04-14"
filter: "ind.insurance_"
---# Extend the Prebuilt Expression Set to Perform Custom Processing of Limits

Extend the Prebuilt Expression Set to Perform Custom Processing of Limits[](https://help.salesforce.com/s?language=en_US)

You are here:

1.  [Salesforce Help](/s/?language=en_US)
2.  [Docs](/s/products?language=en_US)
3.  [Digital Insurance](https://help.salesforce.com/s/articleView?id=ind.insurance_admin_standard.htm&language=en_US&type=5)

# Extend the Prebuilt Expression Set to Perform Custom Processing of Limits

The Processing Limits Expression Set offers powerful extensibility to handle complex payment scenarios while maintaining compliance with carrier-approved policies. By leveraging this flexibility, the system accommodates scenarios where carriers enable payments beyond the sold policy limit under specific tolerances. This extension enables precise control over payment thresholds, ensuring that payments are processed smoothly up to the effective allowance limit while enforcing strict caps beyond it. In addition, it provides robust tracking and tagging mechanisms to monitor consumption beyond the sold limit, supporting transparency, auditability, and regulatory compliance.

### Required Editions

<table class="slds-table slds-table_bordered slds-m-bottom_small edition" lwc-3eigj2skqo3=""><colgroup lwc-3eigj2skqo3=""><col style="width:100%" lwc-3eigj2skqo3=""></colgroup><tbody lwc-3eigj2skqo3=""><tr class="" lwc-3eigj2skqo3=""><td style="vertical-align:top;" class="slds-cell-wrap" lwc-3eigj2skqo3=""><a title="Give users access to Claims Management features. Review the supported edition and permission sets for Claims Management." href="https://help.salesforce.com/s/articleView?id=ind.insurance_claim_perm_set_licenses.htm&amp;language=en_US&amp;type=5" lwc-3eigj2skqo3="">View supported editions.</a></td></tr></tbody></table>

## Use Case: Enabling Payments Beyond Sold Policy Limits with Carrier-Approved Tolerances

This use case is designed for Claims Administrators, Solution Architects, and Implementation Teams using Digital Insurance Claims who need to enable payments beyond the sold policy limit under carrier-approved tolerances, while ensuring proper tracking and compliance.

**Considerations**

-   The Expression Set processes data exclusively from the Insurance Policy Limits Context. To incorporate external data, use Integration Procedures to extend the logic.
-   The allowance must remain immutable and governed by the carrier program, sourced from product attribute scopes or coverage attributes within the IPL context.
-   Avoid modifying the Adjusted Amount. Instead, focus on adjusting blocking thresholds and tagging consumption within the Processing Limits.

**Scenario:**

Some insurance carriers support a soft overage on a policy’s sold limit to reduce friction during payment processing. For example:

-   **Sold Policy Limit:** $10,000
-   **Carrier Allowance:** 10%
-   **Effective Allowance Limit (Soft Cap):** $11,000

**Custom Logic:**

During Processing Limits, the system ensures that payments aren’t blocked until the total consumption reaches the effective allowance limit of $11,000. If a payment request exceeds this limit, the system partially pays the amount up to the allowance and blocks the remaining portion. The blocked amount is accompanied by clear reason codes to provide transparency and clarity for the user. This functionality is designed to work seamlessly without altering the cost-share calculations from the Calculate Adjustments API. The system extends the Processing Limits Expression Set to compute an allowance-aware threshold. This threshold accounts for the carrier-approved tolerance above the sold policy limit and ensures that any consumption beyond the sold limit is properly tagged as Allowance Consumption for tracking and reporting purposes

**Recommended Usage**

Use this approach when:

-   The carrier documents and supports a tolerance or allowance above the sold limits, for example, +5%, +10%.
-   You want to avoid hard blocks when the sold limit is reached while enforcing a strict cap at the allowance limit.
-   You want auditable tracking of amounts consumed beyond the sold limit, ensuring accurate reporting, reconciliation, and regulatory review.

Avoid this approach when:

-   The extra amount must be treated as Ex-gratia.
-   The product mandates a hard-stop at the sold limit with no tolerance.

**Workflow**

1.  **Calculate Adjustments** (prebuilt): Calculates the **AdjustedAmount** that is unchanged by this extension.
2.  **Processing Limits** (extended):
    -   Computes an **Effective Limit** = InitialLimit × (1 + AllowancePercent). For example, $10,000 × 1.10 = $11,000.
    -   Determines the **New Remaining With Allowance** = Effective Limit - Total Consumed To Date.
    -   Pays up to **New Remaining With Allowance** and blocks any amount exceeding it.
    -   Tags any amount paid beyond the sold limit of $10,000 as **Allowance Consumption** for tracking purposes.

## Computation

**Policy Details:**

-   **Sold Policy Limit**: $10,000
-   **Allowance Percent**: 10%
-   **Effective Limit**: $11,000

## Example A: Within Allowance

-   **Consumed to Date**: $9,500
-   **Requested Amount**: $800
-   **Remaining with Allowance**: $11,000 − $9,500 = **$1,500**
-   **Payable**: min($800, $1,500) = **$800** (no block)
-   **AllowanceConsumption**: Portion above $10,000 → $10,300 − $10,000 = **$300** tagged.

## Example B: Exceeding Allowance

-   **Consumed to Date**: $10,900
-   **Requested Amount**: $300
-   **Remaining with Allowance**: $11,000 − $10,900 = **$100**
-   **Payable**: min($300, $100) = **$100**
-   **OverLimit (Blocked)**: $300 − $100 = **$200** with reason: **Limit Reached**.

## Benefits

-   This approach ensures strict compliance with **carrier-approved tolerances**, providing a reliable framework for managing payments while maintaining full transparency and auditability. It allows for accurate tracking and reporting of any amounts consumed beyond the sold policy limit.
-   By enabling payments up to the **effective allowance limit**, this solution minimizes customer friction and ensures a smooth payment experience. For any amounts that exceed the allowance, clear reason codes are provided to explain the blocked portions, enhancing clarity and trust.
-   The solution is seamlessly integrated with the existing **Calculate Adjustments** logic, ensuring that cost-share calculations remain unaffected. This guarantees that the core functionality of the system operates without disruption while extending its capabilities to handle allowance-based scenarios.

Did this article solve your issue?

Let us know so we can improve!

YesNo