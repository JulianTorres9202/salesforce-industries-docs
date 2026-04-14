---
title: "Invocable Actions for Insurance Claims Management"
source: "https://help.salesforce.com/s/articleView?id=ind.insurance_claim_ia.htm&language=en_US&type=5"
scraped: "2026-04-14"
filter: "ind.insurance_"
---# Invocable Actions for Insurance Claims Management

Invocable Actions for Insurance Claims Management[](https://help.salesforce.com/s?language=en_US)

You are here:

1.  [Salesforce Help](/s/?language=en_US)
2.  [Docs](/s/products?language=en_US)
3.  [Digital Insurance](https://help.salesforce.com/s/articleView?id=ind.insurance_admin_standard.htm&language=en_US&type=5)

# Invocable Actions for Insurance Claims Management

Use the invocable actions in Salesforce Flows to manage claims.

### Required Editions

<table class="slds-table slds-table_bordered slds-m-bottom_small edition" lwc-3eigj2skqo3=""><colgroup lwc-3eigj2skqo3=""><col style="width:100%" lwc-3eigj2skqo3=""></colgroup><tbody lwc-3eigj2skqo3=""><tr class="" lwc-3eigj2skqo3=""><td style="vertical-align:top;" class="slds-cell-wrap" lwc-3eigj2skqo3=""><a title="Give users access to Claims Management features. Review the supported edition and permission sets for Claims Management." href="https://help.salesforce.com/s/articleView?id=ind.insurance_claim_perm_set_licenses.htm&amp;language=en_US&amp;type=5" lwc-3eigj2skqo3="">View supported editions.</a></td></tr></tbody></table>

| invocable Action | description |
| --- | --- |
| createPolicyLimits | Use this action to create insurance policy limit records for policy coverage and root attributes. |
| verifyPolicyCoverage | Use this action to verify the coverage of an insurance policy. |
| createClaim | Use this action to create a claim. |
| updateClaim | Use this action to update a claim. |
| getClaim | Use this action to get details of a claim. |
| invokeUnderwritingRules | Use this action to invoke underwriting rules for different insurance object records at run time. |
| openClaimCoverage | Use this action to open a claim coverage. |
| updateClaimCoverage | Use this action to update a claim coverage. |
| getInsPolicyCurrentStandings | Use this action to get the current standings of the insurance policy limits. |
| calculateAdjustments | Use this action to calculate the adjusted amount for a loss item. |
| createClaimCvrPaymentDetail | Use this action to create a claim coverage payment detail record. |
| editClaimCvrPaymentDetail | Use this action to change the details in a claim coverage payment detail record. |
| cancelClaimCvrPaymentDetail | Use this action to cancel a claim coverage payment detail record. |
| deleteClaimCvrPaymentDetail | Use this action to delete a claim coverage payment detail record. |
| payClaimCvrPaymentDetail | Use this action to pay a claim coverage payment detail record. |
| recalculateAdjustments | Use this action to calculate the adjusted amount for a loss item when you update the claimed amount in a claim coverage payment detail record. |
| payExGratiaClaimCvrPymtDetail | Use this action to process an ex gratia payment for a loss-type claim coverage payment detail record. |

#### See Also

-   [Insurance Claims Standard Invocable Actions](https://developer.salesforce.com/docs/atlas.en-us.insurance_developer_guide.meta/insurance_developer_guide/insurance_claim_invocable_actions_parent.htm)

Did this article solve your issue?

Let us know so we can improve!

YesNo