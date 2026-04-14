---
title: "Considerations and Limitations for Insurance Policies"
source: "https://help.salesforce.com/s/articleView?id=ind.insurance_considerations_and_limitations_for_insurance_policies.htm&language=en_US&type=5"
scraped: "2026-04-14"
filter: "ind.insurance_"
---# Considerations and Limitations for Insurance Policies

Considerations and Limitations for Insurance Policies[](https://help.salesforce.com/s?language=en_US)

You are here:

1.  [Salesforce Help](/s/?language=en_US)
2.  [Docs](/s/products?language=en_US)
3.  [Digital Insurance](https://help.salesforce.com/s/articleView?id=ind.insurance_admin_standard.htm&language=en_US&type=5)

# Considerations and Limitations for Insurance Policies

Here are some things to keep in mind about Insurance Policies.

-   Policy administration supports only annual policy terms. Custom, daily, quarterly, half-yearly, and monthly policy terms aren't supported.
    
-   The policy duration is determined by the effective date and expiration date. The duration of the first version of the policy can be less than 365 days, and for leap years, less than 366 days.​ You can perform endorsements, cancellations, renewals, reinstatements, and out-of-sequence endorsements on original policy versions with durations of less than a year. However, for renewals, the renewed policy duration is always 365 or 366 days.
    
-   Policies with a duration of less than 365 or 366 days do not support Insurance Policy Transaction, Insurance Policy Payment Schedule, Insurance Payment Schedule Entry Detail, and Insurance Policy Transaction Detail.
    
-   The endorsement transaction doesn't populate the revenue schedule.
    
-   The Insurance Payment Schedule Entry Detail and Insurance Policy Transaction Detail don't have any premium amount at the root product level.
    
-   You can't change the payment frequency within the policy term for payment schedules where the `useIsPaidFlag` is true.
    
-   Policy administration supports only single-root products.
    
-   For payment schedule calculations that involve division, the currency field on the insurance policy and other policy admin objects rounds off the number to two decimal places. Further operations on these numbers sometimes result in marginal rounding off errors in the total amount.
    

**Out-of-Sequence Endorsement**

-   [InsPolicyService:createOutOfSequencePolicyVersion](https://help.salesforce.com/s/articleView?id=ind.insurance_inspolicyservice__createoutofsequencepolicyversion.htm&language=en_US&type=5 "Use this service to initiate an out-of-sequence endorsement for a given policy.") doesn’t create policy terms.
    
-   Out-of-Sequence payment schedule is supported only when you initiate an out-of-sequence endorsement using the [InsPolicyService:createOutOfSequencePolicyVersion](https://help.salesforce.com/s/articleView?id=ind.insurance_inspolicyservice__createoutofsequencepolicyversion.htm&language=en_US&type=5 "Use this service to initiate an out-of-sequence endorsement for a given policy.") service.
    
-   You can’t call a future method in triggers for Insurance Policies and related tables during an out-of-sequence operation.
    
-   You can’t customize async job bell notifications.
    

**InsPolicyService:renewPoliciesInBatch**

Before you call [InsPolicyService:renewPoliciesInBatch](https://help.salesforce.com/s/articleView?id=ind.insurance_inspolicyservice__renewpoliciesinbatch.htm&language=en_US&type=5 "Use this service to control the number of Apex jobs to initiate, and the number of batches to run per Apex job, for a large number of policy renewals."), understand the limits and what isn't supported:

-   The service doesn't support passing in `userInputs` for a single policy.
-   The service doesn't support passing in `additionalFields` node for a policy record.
-   Repricing options can't be defined at a policy level.
-   Service can't be called from a scheduled job.
-   The creation of renewal quotes isn't supported.
-   The service output doesn't report errors or success at the policy level.

Did this article solve your issue?

Let us know so we can improve!

YesNo