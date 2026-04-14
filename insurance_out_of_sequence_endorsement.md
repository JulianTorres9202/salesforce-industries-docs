---
title: "Insurance Policy Out of Sequence Endorsement"
source: "https://help.salesforce.com/s/articleView?id=ind.insurance_out_of_sequence_endorsement.htm&language=en_US&type=5"
scraped: "2026-04-14"
filter: "ind.insurance_"
---# Insurance Policy Out of Sequence Endorsement

Insurance Policy Out of Sequence Endorsement[](https://help.salesforce.com/s?language=en_US)

You are here:

1.  [Salesforce Help](/s/?language=en_US)
2.  [Docs](/s/products?language=en_US)
3.  [Digital Insurance](https://help.salesforce.com/s/articleView?id=ind.insurance_admin_standard.htm&language=en_US&type=5)

# Insurance Policy Out of Sequence Endorsement

Perform a backdated change on a policy in the past, current, or future policy term, even when another policy version with an effective date later than the endorsement date already exists. When policyholders or insurance brokers issue an out-of-sequence policy endorsement, the changes automatically apply to all future policy versions to maintain consistency.

### Required Editions

<table class="slds-table slds-table_bordered slds-m-bottom_small edition" lwc-3eigj2skqo3=""><colgroup lwc-3eigj2skqo3=""><col style="width:100%" lwc-3eigj2skqo3=""></colgroup><tbody lwc-3eigj2skqo3=""><tr class="" lwc-3eigj2skqo3=""><td style="vertical-align:top;" class="slds-cell-wrap" lwc-3eigj2skqo3="">Available in: Lightning Experience</td></tr><tr class="" lwc-3eigj2skqo3=""><td style="vertical-align:top;" class="slds-cell-wrap" lwc-3eigj2skqo3="">Available in: <strong lwc-3eigj2skqo3="">Enterprise</strong>, <strong lwc-3eigj2skqo3="">Unlimited</strong>, and <strong lwc-3eigj2skqo3="">Developer</strong> Editions of Digital Insurance Platform</td></tr></tbody></table>

Performing an out-of-sequence endorsement follows the same steps as a normal endorsement. You request changes to your policy, review the quote, and apply the endorsement. The difference is that out-of-sequence endorsement also identifies and updates future versions of your policy that are impacted by the change, based on the effective date you selected.

Supported out-of-sequence-endorsement usecases

-   Future term policies – Out-of-sequence endorsement applies changes to policies that are already renewed for a future term. For example, if you add a vehicle to the current policy, the renewed version also reflects the change.
-   Past term policies – Out-of-sequence endorsement applies corrections to past versions of a policy. For example, if you fix an address from a past effective date, the correction carries forward into all later versions.

How normal endorsements work

When users click Modify Policy in the active policy version, the flow calls the createQuote IA to generate an endorsement quote. After users update the quote and click Endorse Policy, the flow calls the endorsePolicy IA to create a new policy version with the applied changes.

How out-of-sequence endorsements work

OOSE follows the same steps as a normal endorsement. The difference is that changes made with an effective date earlier than existing versions also impact future versions of the policy. Users need visibility into these impacted versions before moving forward with an endorsement. This functionality isn’t available out of the box. A custom flow is required to display the impacted versions, give users the necessary context before quote creation, and determine whether the action should use the endorsement invocable action or the OOSE invocable action.

-   **[Set Up Out Of Sequence Endorsement Flows](https://help.salesforce.com/s/articleView?id=ind.insurance_out_of_sequence_endorsement_set_up_flow.htm&language=en_US&type=5)**  
    Configure flows to support Out-of-Sequence Endorsements (OOSE). Create a Modify Policy flow to show impacted policy versions before generating an endorsement quote, and update the Endorse Policy flow so it calls the correct invocable action depending on whether the endorsement is normal or OOSE.

Did this article solve your issue?

Let us know so we can improve!

YesNo