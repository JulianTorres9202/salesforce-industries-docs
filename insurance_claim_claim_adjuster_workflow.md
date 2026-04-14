---
title: "Open Coverages on a Claim"
source: "https://help.salesforce.com/s/articleView?id=ind.insurance_claim_claim_adjuster_workflow.htm&language=en_US&type=5"
scraped: "2026-04-14"
filter: "ind.insurance_"
---# Open Coverages on a Claim

Open Coverages on a Claim[](https://help.salesforce.com/s?language=en_US)

You are here:

1.  [Salesforce Help](/s/?language=en_US)
2.  [Docs](/s/products?language=en_US)
3.  [Digital Insurance](https://help.salesforce.com/s/articleView?id=ind.insurance_admin_standard.htm&language=en_US&type=5)

# Open Coverages on a Claim

Coverages are the financial building blocks of a claim. Claim coverages are opened systematically through product rules that run at the end of the FNOL flow . Claim coverages can also be opened by claim adjusters on existing claims. The Verify Policy Coverage API validates coverage applicability and loss date to ensure compliance and accurate financial management of the claim. After a claim coverage is opened, claims adjusters can actively track losses, payments, and expenses associated with that specific coverage. This enables them to manage the financial aspects of the claim efficiently and ensure accurate record keeping.

### Required Editions

<table class="slds-table slds-table_bordered slds-m-bottom_small edition" lwc-3eigj2skqo3=""><colgroup lwc-3eigj2skqo3=""><col style="width:100%" lwc-3eigj2skqo3=""></colgroup><tbody lwc-3eigj2skqo3=""><tr class="" lwc-3eigj2skqo3=""><td style="vertical-align:top;" class="slds-cell-wrap" lwc-3eigj2skqo3=""><a title="Give users access to Claims Management features. Review the supported edition and permission sets for Claims Management." href="https://help.salesforce.com/s/articleView?id=ind.insurance_claim_perm_set_licenses.htm&amp;language=en_US&amp;type=5" lwc-3eigj2skqo3="">View supported editions.</a></td></tr></tbody></table>

| User Permissions Needed |
| --- |
| [View user permissions.](https://help.salesforce.com/s/articleView?id=ind.insurance_claim_perm_set_licenses.htm&language=en_US&type=5 "Give users access to Claims Management features. Review the supported edition and permission sets for Claims Management.") |

The process of opening a claim coverage includes selecting the policy coverage to use to cover the loss. The Coverage field on the Open Coverage interface shows the list of policy coverage records that exist for the insured item. For example, an Audi vehicle has Collision coverage on an auto policy. If the Audi is damaged in a car accident, the claims adjuster opens a claim coverage on the policy's Collision coverage.

1.  From the App Launcher, find and select **Claims**.
2.  Select a claim from the list view.
3.  Navigate to the Claim Financials tab.
4.  Click **Open Coverage**.
5.  Enter the coverage details:
    
    | field | description |
    | --- | --- |
    | Claimant | The claim participant associated with this claim coverage. |
    | Involved Item | The claim item associated with the claim coverage. |
    | Insured Item | The item that's insured for this claim coverage. |
    | Coverage | A policy coverage that’s associated with the insured item. |
    | Loss Reserve | The total loss reserve amount to be set for this claim coverage. |
    | Expense Reserve | The total expense reserve amount to be set for this claim coverage. |
    
6.  Save your changes.

Did this article solve your issue?

Let us know so we can improve!

YesNo