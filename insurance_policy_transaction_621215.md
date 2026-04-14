---
title: "Insurance Policy Transactions"
source: "https://help.salesforce.com/s/articleView?id=ind.insurance_policy_transaction_621215.htm&language=en_US&type=5"
scraped: "2026-04-14"
filter: "ind.insurance_"
---# Insurance Policy Transactions

Insurance Policy Transactions[](https://help.salesforce.com/s?language=en_US)

You are here:

1.  [Salesforce Help](/s/?language=en_US)
2.  [Docs](/s/products?language=en_US)
3.  [Digital Insurance](https://help.salesforce.com/s/articleView?id=ind.insurance_admin_standard.htm&language=en_US&type=5)

# Insurance Policy Transactions

Insurance Policy Administration extends throughout the lifecycle of an insurance policy. Any updates made to a policy during its term are managed through policy transactions.

Some of the supported transaction types during the policy term are:

-   Sold Policy: This transaction is created when a policy is sold. It generates the premium for the new policy.
    
-   Changed/Endorsed: This transaction is generated after mid-term adjustment or endorsement in the policy. It indicates the change in premium for the policy year as a result of endorsement.
    
-   Endorsement: Indicates the premium adjustment for the payment schedule when the endorsement is performed.
    
-   Renewal: Generates the transaction amount when a policy is renewed for another term.
    
-   Cancellation: Generates the amount that must be refunded when a policy is terminated before its expiration date.
    
-   Reinstatement: Generates the transaction amount for a reinstated policy that was previously canceled.
    
-   Reinstatement by Payment Schedule: The transaction amount is calculated based on the amount refunded or charged for the cancellation transaction and the missed payments between the cancellation effective date and the reinstatement effective date.
    
-   Out-of-Sequence Changed/Endorsed: Total change in premium for the policy year as a result of endorsement. This transaction is generated after out-of-sequence endorsement in the policy. In case multi-term policies are impacted, the transaction is created for each term.
    
-   Out-of-Sequence Endorsement: The premium adjustment for the payment schedule when the endorsement is performed.
    

All transactions are linked to the original policy of the term.

View the Insurance Policy Transactions list related to a Policy (Asset) record on the Related tab. Each transaction in this list shows the name, version, type, and transaction amount. This information is stored in the [`InsurancePolicyTransaction`](https://developer.salesforce.com/docs/atlas.en-us.financial_services_cloud_object_reference.meta/financial_services_cloud_object_reference/sforce_api_objects_insurancepolicytransaction.htm) object.

## Insurance Policy Transaction Details

You can click a transaction name to view the insurance policy transaction details and the breakdown of the transaction amount.

Transaction Breakdown is a process that separates the total amount of a transaction into its individual components such as premiums, taxes, fees, policy surcharges, and contributions from policy components such as coverages, insured items, and participants. This information is stored in the [`InsPolicyTransactionDetail`](https://developer.salesforce.com/docs/atlas.en-us.financial_services_cloud_object_reference.meta/financial_services_cloud_object_reference/sforce_api_objects_inspolicytransactiondetail.htm) object.

Note Configure the `InsPolicyTransactionDetail` object in the related list of the `InsurancePolicyTransaction` object.

The Insurance package includes Transaction Breakdowns for different payment frequencies and payment methods for these flows:To view transaction breakdown, you must add the Insurance Policy Transaction Detail object to the related list of transactions.

-   Policy Issuance
-   Policy Endorsement
-   Policy Cancellation
-   Policy Reinstatement
    

## Transaction Breakdown for Policy Issuance

This flow uses [`InsPolicyService:createUpdatePolicy`](https://help.salesforce.com/s/articleView?id=ind.insurance_inspolicyservice__createupdatepolicy.htm&language=en_US&type=5 "Use this service to create a new insurance policy or to update an existing policy with new information.").

When you call `InsPolicyService:createUpdatePolicy`, the service creates an insurance policy transaction and populates transaction breakdown data into the transaction detail object. This object stores data about how much each asset, participant, or coverage contributes to the total transaction as premium, tax, and fees. Assets, participants, and coverages with at least one value greater than zero for premium, tax, or fees are displayed. Surcharge if any defined at root product level is also displayed.

## Transaction Breakdown for Policy Endorsement

This flow uses [`InsPolicyService:createPolicyVersion`](https://help.salesforce.com/s/articleView?id=ind.insurance_inspolicyservice__createpolicyversion.htm&language=en_US&type=5 "Use this service to create a new version of an existing policy, while maintaining the existing policy record as-is.").

When you call `InsPolicyService:createPolicyVersion`, the service updates the payment schedule and creates a payment schedule entry on the effective date of endorsement. The operation creates these transactions:

-   Changed/Endorsed: The premium difference across policy versions.
    
-   Endorsement: The endorsement transaction amount is calculated as premium adjustment based on old payment and new payment amount for the time period when endorsement transaction becomes effective. Surcharge if any defined at root product level is also displayed.
    
    Note Set the value of `useIsPaidFlag` as true to populate a transaction breakdown for the endorsed policy.
    

## Transaction Breakdown for Out-of-Sequence Policy Endorsement

This flow uses [InsPolicyService:createOutOfSequencePolicyVersion](https://help.salesforce.com/s/articleView?id=ind.insurance_inspolicyservice__createoutofsequencepolicyversion.htm&language=en_US&type=5 "Use this service to initiate an out-of-sequence endorsement for a given policy.")

When you call `InsPolicyService:createOutOfSequencePolicyVersion`, the service generates or updates payment schedule when `includePaymentSchedule` is set to true. The premium is calculated based on the values passed for `paymentCalculationMethod` and `paymentFrequency` options. The operation creates these transactions:

-   Out-of-Sequence Changed/Endorsed: Total change in premium for the policy year as a result of endorsement. This transaction is generated after out-of-sequence endorsement in the policy. In case multi-term policies are impacted, the transaction is created for each term.
    
-   Out-of-Sequence Endorsement: The premium adjustment for the payment schedule when the endorsement is performed.
    

## Transaction Breakdown for Policy Cancellation

This flow uses `[InsPolicyService:cancelPolicy](https://help.salesforce.com/s/articleView?id=ind.insurance_inspolicyservice__cancelpolicy.htm&language=en_US&type=5 "Use this service to cancel an existing insurance policy.")`.

When you call `InsPolicyService:cancelPolicy`, the service uses the appropriate calculation process based on the useIsPaidFlag value to arrive at the transaction. If the flag is true, the service prorates the policy based on the payment schedules. The cancellation transaction amount is calculated as the difference between the amount paid based on the payment schedule entries marked as paid and the actual amount that the customer owes based on the daily rate and effective date of the cancellation. Assets, participants, and coverages with at least one value greater than zero for premium, tax, or fees are displayed. Surcharge if any defined at root product level is also displayed.

Note Set the value of `useIsPaidFlag` as true to populate a transaction breakdown for the canceled policy.

## Transaction Breakdown for Policy Reinstatement

This flow uses `[InsPolicyService:createReinstatementPolicy](https://help.salesforce.com/s/articleView?id=ind.insurance_inspolicyservice_createreinstatementpolicy.htm&language=en_US&type=5 "Use this service to reinstate a canceled policy.")`.

When you call `InsPolicyService:createReinstatementPolicy`, the service reinstates the previously canceled policy and creates a reinstatement transaction on the effective date of the reinstatement. The service generates transaction detail entries for each reinstatement transaction performed on policies set up with a payment frequency and payment method as modal or daily. These entries are generated for all coverages, items, and participants where the premium is impacted. The payment schedule is adjusted to show the reinstatement transaction as of the reinstatement effective date and new entries based on the term premium of the new policy version starting from the following payment date from the date of reinstatement.

Reinstatement covers these transaction types:

-   **Reinstatement**: A reinstatement transaction is generated by default on the full amount that is owed based on the term premium of the reinstated policy version.
    
-   **Reinstatement by payment schedule**: This transaction shows up as a payment schedule entry. The transaction is calculated based on the amount refunded or charged for the cancellation transaction and the missed payments between the cancellation effective date and the reinstatement effective date.
    

Did this article solve your issue?

Let us know so we can improve!

YesNo