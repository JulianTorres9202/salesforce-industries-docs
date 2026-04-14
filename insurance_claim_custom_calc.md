---
title: "Extend the Prebuilt Expression Set to Perform Custom Calculations"
source: "https://help.salesforce.com/s/articleView?id=ind.insurance_claim_custom_calc.htm&language=en_US&type=5"
scraped: "2026-04-14"
filter: "ind.insurance_"
---# Extend the Prebuilt Expression Set to Perform Custom Calculations

Extend the Prebuilt Expression Set to Perform Custom Calculations[](https://help.salesforce.com/s?language=en_US)

You are here:

1.  [Salesforce Help](/s/?language=en_US)
2.  [Docs](/s/products?language=en_US)
3.  [Digital Insurance](https://help.salesforce.com/s/articleView?id=ind.insurance_admin_standard.htm&language=en_US&type=5)

# Extend the Prebuilt Expression Set to Perform Custom Calculations

The Calculate Adjustments Prebuilt Expression Set is a customizable algorithm designed to determine how benefit categories such as Deductible, Copay, and Out-of-Pocket Maximum (OOPM) transform a claimed amount into an adjusted amount, while also generating auditable postings such as Insurance Policy Limit Tracking (IPLT) and Claim Coverage Payment Adjustment (CCPA) records. You can copy and change the prebuilt expression set, or create an expression set for specific areas, regions, or networks. You can do this without changing the main APIs.

### Required Editions

<table class="slds-table slds-table_bordered slds-m-bottom_small edition" lwc-3eigj2skqo3=""><colgroup lwc-3eigj2skqo3=""><col style="width:100%" lwc-3eigj2skqo3=""></colgroup><tbody lwc-3eigj2skqo3=""><tr class="" lwc-3eigj2skqo3=""><td style="vertical-align:top;" class="slds-cell-wrap" lwc-3eigj2skqo3=""><a title="Give users access to Claims Management features. Review the supported edition and permission sets for Claims Management." href="https://help.salesforce.com/s/articleView?id=ind.insurance_claim_perm_set_licenses.htm&amp;language=en_US&amp;type=5" lwc-3eigj2skqo3="">View supported editions.</a></td></tr></tbody></table>

## Configuration Options

You can use any element within the Expression Set Builder to align with your business logic:

-   **Flow style:** Maintain the prebuilt sequential order, switch to simultaneous evaluation, or implement any other custom logic.
-   **Per-category math:** Define formulas for calculating required amounts, whether flat or percentage-based, including minimum and maximum values.
-   **Category rules:** Apply deductions from one category within another category, such as including the Copay within the Deductible category.
-   **OOPM enforcement:** Ensure OOPM is checked after each deduction, with automatic adjustment of caps and reallocations.
-   **Outputs and audit:** Make sure that the prebuilt executable response format is still compatible with Claim Coverage Payment Detail (CCPD), Process Limits, IPLT, and CCPA. You can add extra details to make the response more traceable.

## Use Case: Simultaneous Evaluation of Deductible and Copay for a Claim Amount

Custom logic used in this use case:

-   When processing the claim, both the Deductible and Copay amounts are considered simultaneously.
-   The Copay amount is included within the Deductible category for standings. This means that the Copay is treated as part of the Deductible until the Deductible limit is reached.
-   To ensure clear and auditable ledger entries, the system generates separate records for the IPLT and adjustment nodes. This separation helps in maintaining transparency and traceability of each component of the claim processing.
-   OOPM is checked after each deduction to ensure that the patient's total out-of-pocket expenses don't exceed the limit. After applying the Deductible and Copay, the system verifies that the cumulative patient responsibility is within the OOPM limit. If the OOPM is exceeded, the system adjusts the amounts accordingly.

**Inputs:**

-   **Claim Amount :**$10,000
-   **Deductible Remaining :**$200
-   **Copay :**$50 (flat)
-   **Out-of-Pocket Maximum (OOPM) Remaining :**$1,000

**Computation (simultaneous with bucket inclusion):**

1.  **Deductible Component Applied:**
    
    -   **Deductible Applied :**The first step is to apply the remaining deductible amount to the claim. Here, the deductible remaining is $200.
    -   **Cumulative Patient Responsibility :**After applying the deductible, the patient is responsible for this amount. So, the cumulative patient responsibility is now $200.
    -   **OOPM Check :**We need to check if the cumulative patient responsibility exceeds the OOPM. In this case, $200 (cumulative patient responsibility) is less than or equal to $1,000 (OOPM remaining), so it's within the limit.
    -   **OOPM Remaining :**After applying the deductible, the OOPM remaining is updated. OOPM remaining = $1,000 - $200 = $800.
2.  **Copay Component Applied:**
    
    -   **Copay Applied :**Next, we apply the copay amount. The copay is a flat $50.
    -   **Cumulative Patient Responsibility :**Adding the copay to the previous cumulative patient responsibility, we get $200 (deductible) + $50 (copay) = $250.
    -   **OOPM Check :**Again, we check if the cumulative patient responsibility exceeds the OOPM. Here, $250 (cumulative patient responsibility) is less than or equal to $800 (OOPM remaining), so it's within the limit.
    -   **OOPM Remaining :**After applying the copay, the OOPM remaining is updated. OOPM remaining = $800 - $50 = $750.
3.  **Bucket Inclusion with Cap:**
    
    -   **Attempt to Include Copay in Deductible Bucket :**We attempt to include the copay amount in the deductible bucket. However, the deductible bucket remaining was $200.
    -   **Inclusion Capped at $200 Total :**Since the deductible bucket remaining is $200, the inclusion is capped at $200 total.
    -   **Deductible Bucket Consumed This Run :**The deductible bucket consumed this run is calculated as the minimum of the sum of the deductible and copay amounts and the remaining deductible bucket. So, min($200 (deductible) + $50 (copay), $200 remaining) = $200.
    -   **Composition Counted Toward Bucket :**The composition counted toward the bucket is $200 from the deductible and $50 from the copay.
    -   **Deductible Remaining After Run :**After this run, the deductible remaining is $0.
    -   **Copay Remaining After Run :**After this run, the copay remaining is $0.
4.  **Adjusted Amount (Payer Liability):**
    
    -   **Adjusted Amount :**Finally, we calculate the adjusted amount, which is the payer's liability. This is the original claim amount minus
    -   **Adjusted Amount :**Finally, we calculate the adjusted amount, which is the payer's liability. This is the original claim amount minus the deductible applied. So, $10,000 - $200 = $9,800.

**Summary:**

-   The patient is responsible for $250 (deductible + copay).
-   The payer's liability is $9,800 after applying the deductible.
-   The OOPM is reduced to $750 after these computations.

This is a sample input JSON:

```
{
"ClaimedAmount": "10000",
"InsurancePolicyLimit": [
{
"Category": "Deductible",
"Scope": "PolicyCoverage",
"PolicyLimitAmount": "2000",
"InsurancePolicyLimitTracking": [
{
"RemainingAmount": "200"
}
]
},
{
"Category": "CoPay",
"Scope": "ClaimCoverage",
"PolicyLimitValue": "50",
"InsurancePolicyLimitTracking": [
{
"RemainingAmount": "50"
}
]
},

{
"Category": "OutOfPocketMax",
"Scope": "Policy",
"PolicyLimitAmount": "5000",
"InsurancePolicyLimitTracking": [
{
"RemainingAmount": "1000"
}
]
}
]
}
```

This is a sample output JSON:

```
{
"ClaimedAmount": "10000",
"InsurancePolicyLimit": [
{
"Category": "Deductible",
"Scope": "PolicyCoverage",
"PolicyLimitAmount": "200",
"InsurancePolicyLimitTracking": [
{
"RemainingAmount": "0"
}
]
},
{
"Category": "CoPay",
"Scope": "ClaimCoverage",
"PolicyLimitValue": "50",
"InsurancePolicyLimitTracking": [
{
"RemainingAmount": "0"
}
]
},
{
"Category": "OutOfPocketMax",
"Scope": "Policy",
"PolicyLimitAmount": "5000",
"InsurancePolicyLimitTracking": [
{
"RemainingAmount": "750"
}
]
}
]
}

```

Did this article solve your issue?

Let us know so we can improve!

YesNo