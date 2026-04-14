---
title: "Support Transaction and Payment Schedule Breakdown for Out-of-Sequence Endorsement"
source: "https://help.salesforce.com/s/articleView?id=ind.insurance_support_transaction_and_payment_schedule_breakdown_for_out_of_sequence_endorsement.htm&language=en_US&type=5"
scraped: "2026-04-14"
filter: "ind.insurance_"
---# Support Transaction and Payment Schedule Breakdown for Out-of-Sequence Endorsement

Support Transaction and Payment Schedule Breakdown for Out-of-Sequence Endorsement[](https://help.salesforce.com/s?language=en_US)

You are here:

1.  [Salesforce Help](/s/?language=en_US)
2.  [Docs](/s/products?language=en_US)
3.  [Digital Insurance](https://help.salesforce.com/s/articleView?id=ind.insurance_admin_standard.htm&language=en_US&type=5)

# Support Transaction and Payment Schedule Breakdown for Out-of-Sequence Endorsement

The InsPolicyService:createOutOfSequencePolicyVersion service now supports generating transaction breakdowns and payment schedule entry details for out-of-sequence transactions. Customers can see the premium, tax, and fee contribution from policy components and surcharges if defined at the root product level for out-of-sequence endorsement.

**How**: Set includePaymentSchedule=true and createTransaction=true

**Where**: This change applies to Lightning Experience in Professional, Enterprise, and Unlimited editions.

**How**: Set includePaymentSchedule=true and createTransaction=true when initiating a single or multi-term out-of-sequence endorsement through the service flow.

## See Also

-   [InsPolicyService:createOutOfSequencePolicyVersion](https://help.salesforce.com/s/articleView?id=ind.insurance_inspolicyservice__createoutofsequencepolicyversion.htm&language=en_US&type=5 "Use this service to initiate an out-of-sequence endorsement for a given policy.")

Did this article solve your issue?

Let us know so we can improve!

YesNo