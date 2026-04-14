---
title: "Claim Credit Usage Considerations"
source: "https://help.salesforce.com/s/articleView?id=ind.insurance_claim_usage_types.htm&language=en_US&type=5"
scraped: "2026-04-14"
filter: "ind.insurance_"
---# Claim Credit Usage Considerations

Claim Credit Usage Considerations[](https://help.salesforce.com/s?language=en_US)

You are here:

1.  [Salesforce Help](/s/?language=en_US)
2.  [Docs](/s/products?language=en_US)
3.  [Digital Insurance](https://help.salesforce.com/s/articleView?id=ind.insurance_admin_standard.htm&language=en_US&type=5)

# Claim Credit Usage Considerations

Use of Insurance Claims Management impacts the consumption of credits used for billing in these usage types.

### Required Editions

<table class="slds-table slds-table_bordered slds-m-bottom_small edition" lwc-3eigj2skqo3=""><colgroup lwc-3eigj2skqo3=""><col style="width:100%" lwc-3eigj2skqo3=""></colgroup><tbody lwc-3eigj2skqo3=""><tr class="" lwc-3eigj2skqo3=""><td style="vertical-align:top;" class="slds-cell-wrap" lwc-3eigj2skqo3="">Available in: Lightning Experience</td></tr><tr class="" lwc-3eigj2skqo3=""><td style="vertical-align:top;" class="slds-cell-wrap" lwc-3eigj2skqo3="">Available in: <strong lwc-3eigj2skqo3="">Professional</strong>, <strong lwc-3eigj2skqo3="">Enterprise</strong>, and <strong lwc-3eigj2skqo3="">Unlimited</strong> Editions</td></tr></tbody></table>

| usage type | description | notes |
| --- | --- | --- |
| Claim intake | Tracks credits used for Claims First Notice of Loss (FNOL) | One credit is used whenever any of the following actions occur:
-   Create a claim by using the FNOL process
-   Invoke the Create Claim API

 |
| Claim processing | Tracks credits used for Claims processing | One credit is consumed whenever any of the following actions occur:

-   Click **Add Expense** on the Claims Financials page
-   Click **Add Loss** on the Claims Financials page
-   Invoke the Create Claim Coverage Payment Detail API

 |

Claim Credits usage isn’t reported in Digital Wallet. Your usage statement will be sent via email on a monthly basis. For details about how the Claim Credits usage type is billed, see the Claims Rate Card. For more information on how usage is billed, refer to your contract or contact your account executive.

Did this article solve your issue?

Let us know so we can improve!

YesNo