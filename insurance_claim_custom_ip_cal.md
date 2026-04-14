---
title: "Custom Integration Procedures for Adjustment Calculations"
source: "https://help.salesforce.com/s/articleView?id=ind.insurance_claim_custom_ip_cal.htm&language=en_US&type=5"
scraped: "2026-04-14"
filter: "ind.insurance_"
---# Custom Integration Procedures for Adjustment Calculations

Custom Integration Procedures for Adjustment Calculations[](https://help.salesforce.com/s?language=en_US)

You are here:

1.  [Salesforce Help](/s/?language=en_US)
2.  [Docs](/s/products?language=en_US)
3.  [Digital Insurance](https://help.salesforce.com/s/articleView?id=ind.insurance_admin_standard.htm&language=en_US&type=5)

# Custom Integration Procedures for Adjustment Calculations

The standard expression set is designed to handle obligations within the Insurance Policy Limit context. There are instances where you need more specialized calculations. When you need to calculate Deductibles, Copays, Coinsurance, or Out-of-Pocket Maximum (OOPM) with custom logic, you can extend the calculation flow by using a custom Integration Procedure (IP).

### Required Editions

<table class="slds-table slds-table_bordered slds-m-bottom_small edition" lwc-3eigj2skqo3=""><colgroup lwc-3eigj2skqo3=""><col style="width:100%" lwc-3eigj2skqo3=""></colgroup><tbody lwc-3eigj2skqo3=""><tr class="" lwc-3eigj2skqo3=""><td style="vertical-align:top;" class="slds-cell-wrap" lwc-3eigj2skqo3=""><a title="Give users access to Claims Management features. Review the supported edition and permission sets for Claims Management." href="https://help.salesforce.com/s/articleView?id=ind.insurance_claim_perm_set_licenses.htm&amp;language=en_US&amp;type=5" lwc-3eigj2skqo3="">View supported editions.</a></td></tr></tbody></table>

A custom IP is particularly beneficial in ‌these situations:

-   **External data:** The data required for your calculations is not always confined to standard data sets. For example, you might incorporate claimant or account data such as age, region, or employer group. This external data can significantly impact the calculation of deductibles, copays, coinsurance, or OOPM.
-   **Advanced logic:** In certain scenarios, standard logic may not be sufficient. For example, you need to apply age-based coinsurance rebates or other complex rules.
-   **Real-time consumption values:** In certain cases, the values required for calculations are dynamic and fetched in real time. This involves external APIs to access the latest information.

By using a custom IP, you can make sure that your calculations are precise and tailored to your specific needs, leveraging data and logic that go beyond the standard capabilities of the expression set. This flexibility is crucial for handling complex insurance scenarios and providing accurate results.

Before you create your custom Integration Procedure, make sure that you enable [Omnistudio Metadata API Support](https://help.salesforce.com/s/articleView?id=xcloud.os_enable_omnistudio_metadata_api_support.htm&language=en_US&type=5).

## Custom IP Workflow

Steps to create a custom IP for calculating adjustments:

1.  Create an integration procedure. For example, IP\_CustomAdjustments.
    
    The IP takes the claimCoverageId, ccpdId, and requestedAmount as inputs.
    
2.  It fetches reference data:
    
    -   The DOB from the Contact object to calculate age.
    -   The address from the Account object to determine region.
3.  Optionally, it invokes the Get Current Standings API to fetch the latest deductible, copay, coinsurance, and OOPM usage.
    
    -   Use this API inside your IP if you want to retrieve the current deductible, OOPM, and other obligation balances.
    -   This ensures your obligation calculation reflects the most recent consumption at the time of calculation.
    -   If you don't invoke this API, your IP uses the values passed via the request or static configuration.
    -   You can use other data extraction tools within the IP if the Get Current Standings API isn't ideal for the use case.
4.  Implements obligation rules:
    
    -   **Deductible:** Deducts the remaining deductible amount.
    -   **Coinsurance:** Applies either the base or an adjusted rate. For example, apply a reduced coinsurance rate for claimants over the age of 75.
    -   **OOPM:** Adjust obligations if the claimant has already reached the out-of-pocket maximum.
5.  Produces a consolidated JSON response that includes:
    
    -   **insurancePolicyLimitTrackings:** Details of limit tracking.
    -   **claimCovPaymentAdjustments:** Breakdown of payment adjustments.
    -   Ensures that the adjustedAmount reflects the final payable amount after all obligations.

**Summary**

Ensure the output JSON format is exactly as shown below.

```
{
"adjustedAmount": 800,
"adjustmentReason": "Deductible, Copay, Coinsurance, OOPM",
"insurancePolicyLimitTrackings": [
{
"calcInitialAmount": 1000,
"category": "Deductible",
"insurancePolicyLimitId": "1TDxx0000004Cc7GAE",
"postedAmount": 200,
"remainingAmount": 0,
"scope": "ClaimCoverage",
"totalUsedAmount": 500
},

{
"calcInitialAmount": 1000,
"category": "Coinsurance",
"insurancePolicyLimitId": "1TDxx0000004Cc6GAE",
"postedAmount": 54.60,
"remainingAmount": 925.40,
"scope": "ClaimCoverage",
"totalUsedAmount": 300
},
{
"calcInitialAmount": 1000,
"category": "OOPM",
"insurancePolicyLimitId": "1TDxx0000004Cc8GAE",
"postedAmount": 200,
"remainingAmount": 0,
"scope": "Policy",
"totalUsedAmount": 6000
}
],
"claimCovPaymentAdjustments": [
{ "adjustedAmount": 200, "adjustmentReason": "Deductible" },
{ "adjustedAmount": 20, "adjustmentReason": "Copay" },
{ "adjustedAmount": 54.60, "adjustmentReason": "Coinsurance" },
{ "adjustedAmount": 200, "adjustmentReason": "OOPM" }
]
}
```

## Use case: Obligations with Optional Current Standings

**Scenario**

-   **Requested Amount:** $1,000
    
-   **Deductible Remaining:** $200 (retrieved from the Get Current Standings API)
    
-   **Coinsurance:** 7% (rebate applied, normally 10%)
    
-   **Out-of-Pocket Maximum (OOPM):** Claimant has already used $5,700 out of the $6,000 cap.
    

**Calculation Steps**

1.  Deductible application:
    
    -   The remaining deductible of $200 is applied to the requested amount.
    -   Requested amount after deductible: $1,000 - $200 = $800
2.  Coinsurance application:
    
    -   Apply the 7% coinsurance to the remaining amount.
    -   Coinsurance amount: $800 \* 7% = $56
3.  Out-of-Pocket Maximum (OOPM) consideration:
    
    -   The remaining amount after deductible and coinsurance is considered for OOPM is $44.
    -   Adjusted amount after coinsurance: $800 - $56 = $744
4.  Final Amount:
    
    -   Since the claimant has not reached the OOPM cap, the remaining $744 is covered and sent for payment.

**Output JSON sample:**

```
{
  "adjustedAmount": 744,
  "adjustmentReason": "Deductible, Copay, Coinsurance",
  "insurancePolicyLimitTrackings": [
    {
      "calcInitialAmount": 200,
      "category": "Deductible",
      "insurancePolicyLimitId": "1TDxx0000004Cc7GAE",
      "postedAmount": 1000,
      "remainingAmount": 0,
      "scope": "ClaimCoverage",
      "totalUsedAmount": 1000
    },
    {
      "calcInitialValue": 7,
      "category": "Coinsurance",
      "insurancePolicyLimitId": "1TDxx0000004Cc6GAE",
      "postedAmount": 800,
      "scope": "ClaimCoverage",
      "totalUsedAmount": 56
    },
    {
      "calcInitialAmount": 300,
      "category": "OOPM",
      "insurancePolicyLimitId": "1TDxx0000004Cc8GAE",
      "postedAmount": 1000,
      "remainingAmount": 44,
      "scope": "Policy",
      "totalUsedAmount": 5956
    }
  ],
  "claimCovPaymentAdjustments": [
    {
      "adjustedAmount": 200,
      "adjustmentReason": "Deductible"
    },
    {
      "adjustedAmount": 56,
      "adjustmentReason": "Coinsurance"
    }
  ]
}
```

## Considerations

-   **Optional API:** For accuracy, you can call the Get Current Standings API from within the IP. Use this API if you need real-time data on limit consumption.
    
-   **Association:** During setup, associate your IP with the relevant policy coverages where the obligation logic is to be applied.
    

Did this article solve your issue?

Let us know so we can improve!

YesNo