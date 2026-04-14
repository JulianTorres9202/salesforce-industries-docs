---
title: "Custom Integration Procedures for Processing Limits"
source: "https://help.salesforce.com/s/articleView?id=ind.insurance_claim_custom_ip_limits.htm&language=en_US&type=5"
scraped: "2026-04-14"
filter: "ind.insurance_"
---# Custom Integration Procedures for Processing Limits

Custom Integration Procedures for Processing Limits[](https://help.salesforce.com/s?language=en_US)

You are here:

1.  [Salesforce Help](/s/?language=en_US)
2.  [Docs](/s/products?language=en_US)
3.  [Digital Insurance](https://help.salesforce.com/s/articleView?id=ind.insurance_admin_standard.htm&language=en_US&type=5)

# Custom Integration Procedures for Processing Limits

The standard expression set is designed to manage responsibilities within the context of the Insurance Policy Limit. However, there are situations where more specialized calculations are required. In such cases, when you need to process limits by using custom logic, you can enhance the calculation flow by implementing a custom Integration Procedure (IP). This enables a more tailored and precise handling of policy limits.

### Required Editions

<table class="slds-table slds-table_bordered slds-m-bottom_small edition" lwc-3eigj2skqo3=""><colgroup lwc-3eigj2skqo3=""><col style="width:100%" lwc-3eigj2skqo3=""></colgroup><tbody lwc-3eigj2skqo3=""><tr class="" lwc-3eigj2skqo3=""><td style="vertical-align:top;" class="slds-cell-wrap" lwc-3eigj2skqo3=""><a title="Give users access to Claims Management features. Review the supported edition and permission sets for Claims Management." href="https://help.salesforce.com/s/articleView?id=ind.insurance_claim_perm_set_licenses.htm&amp;language=en_US&amp;type=5" lwc-3eigj2skqo3="">View supported editions.</a></td></tr></tbody></table>

**Scenario**

When the primary beneficiary or any dependent is under 18 and they use the Critical Illness coverage under the Medical Insurance root product, the system must make sure that the overall policy level limit (Sum Insured) remains unaffected. Instead, the system should only debit the specific Benefit limit such as for a Platelet Count Test and the coverage level limit. This makes sure that the policy's total coverage amount is preserved for other potential claims.

**Inputs**

-   **Coverage:** Critical Illness
    
-   **Benefit:** Platelet Count Test
    
-   **Participant:** The participant is 16 years old, which means the minor rule applies.
    
-   **Starting Limits:**
    
    -   The Policy Sum Insured (SI) is $50,000. This is the total amount available under the policy.
    -   The Critical Illness Coverage has a limit of $5,000. This is the maximum amount that can be claimed for critical illness-related expenses.
    -   The Platelet Count Benefit has a specific limit of $600. This is the maximum amount that can be claimed for platelet count tests.
-   **Claim (Allowed Amount):** The claim amount for the Platelet Count Test is $120. This is the amount that is being requested for reimbursement under the benefit.
    

In this scenario, since the participant is under 18, the system should make sure that the $120 claim is deducted only from the Platelet Count Benefit limit and the Critical Illness Coverage limit, without affecting the overall Policy Sum Insured of $50,000.

**Rules**

If the **Coverage** is Critical Illness and **age** is less than 18 implement these rules:

-   Don't reduce the Policy's Sum Insured.
-   Reduce only the Benefit limit and the Coverage limit.
-   Calculate the Payment as the minimum of the allowed amount, the remaining Benefit limit, and the remaining Coverage limit.
-   Calculate the Denied amount as the difference between the allowed amount and the Payment.

**Minor (aged 16) Consumption and Balances**

| Bucket | Before | Change | After |
| --- | --- | --- | --- |
| Platelet Count (Benefit) | $600 | −$120 | $480 |
| Critical Illness (Coverage) | $5,000 | −$120 | $4,880 |
| Policy Sum Insured | $50,000 | −$0 | $50,000 |

-   **Payment Amount:** $120 has been approved and will be paid.
    
-   **Denied Amount:** $0, meaning no part of the claim has been denied.
    
-   **Policy Limit:** The overall policy limit remains unaffected and unchanged.
    

This is a sample output JSON:

```
{
  "isLimitExceeded": true,
  "claimLossItemProcessingDetailsOutput": {
    "list": [
      {
        "insurancePolicyLimitId": "9QMSG000000A7t34AC",
        "category": "Limit - Currency",
        "scope": "Policy",
        "postedAmount": "120",
        "calculatedInitialAmount": "50000",
        "remainingAmount": "50000",
        "totalUsedAmount": "0",
        "isLimitExceeded" : "false"
      },
      {
        "insurancePolicyLimitId": "9QMSG000000A7t34AC",
        "category": "Limit - Currency",
        "scope": "Policy",
        "postedAmount": "120",
        "calculatedInitialAmount": "5000",
        "remainingAmount": "4880",
        "totalUsedAmount": "120",
        "isLimitExceeded" : "false"
      },
      {
        "insurancePolicyLimitId": "9QMSG000000A7t34AC",
        "category": "Limit - Currency",
        "scope": "Policy",
        "postedAmount": "120",
        "calculatedInitialAmount": "600",
        "remainingAmount": "480",
        "totalUsedAmount": "120",
        "isLimitExceeded" : "false"
      }
    ]
  }
}
```

In contrast, for an adult aged 19, the policy limit is consumed as follows:

**Adult (aged 19) Consumption and Balances**

| Bucket | Before | Change | After |
| --- | --- | --- | --- |
| Platelet Count (Benefit) | $600 | −$120 | $480 |
| Critical Illness (Coverage) | $5,000 | −$120 | $4,880 |
| Policy Sum Insured | $50,000 | −$120 | $49,880 |

**Payment Amount:** $120 has been approved and will be paid.

Note Before you create your custom Integration Procedure, make sure that you enable [Omnistudio Metadata API Support](https://help.salesforce.com/s/articleView?id=xcloud.os_enable_omnistudio_metadata_api_support.htm&language=en_US&type=5).

Did this article solve your issue?

Let us know so we can improve!

YesNo