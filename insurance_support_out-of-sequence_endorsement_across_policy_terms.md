---
title: "Support Out-of-Sequence Endorsement Across Policy Terms"
source: "https://help.salesforce.com/s/articleView?id=ind.insurance_support_out-of-sequence_endorsement_across_policy_terms.htm&language=en_US&type=5"
scraped: "2026-04-14"
filter: "ind.insurance_"
---# Support Out-of-Sequence Endorsement Across Policy Terms

Support Out-of-Sequence Endorsement Across Policy Terms[](https://help.salesforce.com/s?language=en_US)

You are here:

1.  [Salesforce Help](/s/?language=en_US)
2.  [Docs](/s/products?language=en_US)
3.  [Digital Insurance](https://help.salesforce.com/s/articleView?id=ind.insurance_admin_standard.htm&language=en_US&type=5)

# Support Out-of-Sequence Endorsement Across Policy Terms

Perform a backdated change on a policy when one or more future policy versions with an effective date later than the endorsement date exists and automatically apply the change on all future policy versions. External customers can use `InsPolicyService:createOutOfSequencePolicyVersion` to perform an out-of-sequence endorsement and `InsPolicyService:getOutOfSequenceEndorsementStatus` to retrieve the endorsement status.

**Where**: This change applies to Lightning Experience in Professional, Enterprise, and Unlimited editions with the Insurance Industries managed package.

**How**: Before you begin an out-of-sequence endorsement, complete these prerequisites:

-   Set the **EnableOutOfSequenceEndorsement** custom setting to **true**.
    
-   Populate the same **Reference Policy Number** on all the policy versions for a given insurance policy.
    
-   When performing an out-of-sequence endorsement using the `InsPolicyService:createOutOfSequencePolicyVersion` service, set createTransaction and includePaymentSchedule options to true. Setting these options to true enables payment schedules and transactions for the current policy term.
    

## See Also

-   [Manage an Out-of-Sequence Endorsement](https://help.salesforce.com/s/articleView?id=ind.insurance_create_an_out_of_sequence_endorsement.htm&language=en_US&type=5 "An out-of-sequence endorsement is a modification to a policy with an effective date that is earlier than the effective date of another endorsement already bound on the policy. All the backdated changes are automatically applied on top of future policy versions within and across the policy terms.")

Did this article solve your issue?

Let us know so we can improve!

YesNo