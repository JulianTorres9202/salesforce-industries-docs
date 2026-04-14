---
title: "InsPolicyService Methods"
source: "https://help.salesforce.com/s/articleView?id=ind.insurance_inspolicyservice_methods.htm&language=en_US&type=5"
scraped: "2026-04-14"
filter: "ind.insurance_"
---# InsPolicyService Methods

InsPolicyService Methods[](https://help.salesforce.com/s?language=en_US)

You are here:

1.  [Salesforce Help](/s/?language=en_US)
2.  [Docs](/s/products?language=en_US)
3.  [Digital Insurance](https://help.salesforce.com/s/articleView?id=ind.insurance_admin_standard.htm&language=en_US&type=5)

# InsPolicyService Methods

These are the available InsPolicyService methods.

-   **[InsPolicyService:calculateTaxesAndFees](https://help.salesforce.com/s/articleView?id=ind.insurance_inspolicyservice__calculatetaxesandfees.htm&language=en_US&type=5)**  
    Use this service to calculate and save taxes and fees on a target asset (policy).
-   **[InsPolicyService:cancelPolicy](https://help.salesforce.com/s/articleView?id=ind.insurance_inspolicyservice__cancelpolicy.htm&language=en_US&type=5)**  
    Use this service to cancel an existing insurance policy.
-   **[InsPolicyService:cancelPoliciesInBulk](https://help.salesforce.com/s/articleView?id=ind.insurance_inspolicyservice_cancelpoliciesinbulk.htm&language=en_US&type=5)**  
    Use this service to cancel policy records (InsurancePolicy) in bulk. The service uses InsPolicyService:cancelPolicy service and Vlocity batch Framework to process the cancellation of multiple policies asynchronously.
-   **[InsPolicyService:createMultiRootPolicy](https://help.salesforce.com/s/articleView?id=ind.insurance_inspolicyservice_createmultirootpolicy.htm&language=en_US&type=5)**  
    Use this service to issue a multi-root policy from a quote.
-   **[InsPolicyService:createMultiRootPolicyVersion](https://help.salesforce.com/s/articleView?id=ind.insurance_inspolicyservice_createmultirootpolicyversion.htm&language=en_US&type=5)**  
    Use this service to endorse a multi-root policy from an endorsed quote.
-   **[InsPolicyService:createOutOfSequencePolicyVersion](https://help.salesforce.com/s/articleView?id=ind.insurance_inspolicyservice__createoutofsequencepolicyversion.htm&language=en_US&type=5)**  
    Use this service to initiate an out-of-sequence endorsement for a given policy.
-   **[InsPolicyService:createPaymentSchedule](https://help.salesforce.com/s/articleView?id=ind.insurance_inspolicyservice__createpaymentschedule.htm&language=en_US&type=5)**  
    The InsPolicyService:createPaymentSchedule service creates a payment schedule (and optionally an initial payment transaction) for the target policy. This applies to Insurance Policy object only. The Policy (Asset) object is not supported.
-   **[InsPolicyService:createPolicyTerms](https://help.salesforce.com/s/articleView?id=ind.insurance_inspolicyservice__createpolicyterms.htm&language=en_US&type=5)**  
    Create policy terms in the **AssetTerm\_\_c** or **InsurancePolicyTerm\_\_c** (for Salesforce FSC) object for all the power attributes at the Policy and PolicyCoverage level. A power attribute is an attribute that has an attribute class, attribute scope, applicable item, and applicable actions.
-   **[InsPolicyService:createPolicyVersion](https://help.salesforce.com/s/articleView?id=ind.insurance_inspolicyservice__createpolicyversion.htm&language=en_US&type=5)**  
    Use this service to create a new version of an existing policy, while maintaining the existing policy record as-is.
-   **[InsPolicyService:createReinstatementPolicy](https://help.salesforce.com/s/articleView?id=ind.insurance_inspolicyservice_createreinstatementpolicy.htm&language=en_US&type=5)**  
    Use this service to reinstate a canceled policy.
-   **[InsPolicyService:createRenewalPolicy](https://help.salesforce.com/s/articleView?id=ind.insurance_inspolicyservice__createrenewalpolicy.htm&language=en_US&type=5)**  
    Use this service to create a renewal policy from an existing policy.
-   **[InsPolicyService:createRenewalQuote](https://help.salesforce.com/s/articleView?id=ind.insurance_inspolicyservice__createrenewalquote.htm&language=en_US&type=5)**  
    Use this service to create a renewal quote for an existing policy.
-   **[InsPolicyService:createTransaction](https://help.salesforce.com/s/articleView?id=ind.insurance_inspolicyservice__createtransaction.htm&language=en_US&type=5)**  
    Use this service to create a transaction on a target policy.
-   **[InsPolicyService:createUpdatePolicy](https://help.salesforce.com/s/articleView?id=ind.insurance_inspolicyservice__createupdatepolicy.htm&language=en_US&type=5)**  
    Use this service to create a new insurance policy or to update an existing policy with new information.
-   **[InsPolicyService:getInsuredItems](https://help.salesforce.com/s/articleView?id=ind.insurance_inspolicyservice__getinsureditems.htm&language=en_US&type=5)**  
    Use this service to find and return insured items and insured parties from a policy (asset).
-   **[InsPolicyService:getModifiedPolicy](https://help.salesforce.com/s/articleView?id=ind.insurance_inspolicyservice__getmodifiedpolicy.htm&language=en_US&type=5)**  
    Use this service when a user makes changes to the insured items or insured parties in an existing policy. The service takes the changes the user makes and returns modified policy data, including the recalculated price.
-   **[InsPolicyService:getOutOfSequenceEndorsementStatus](https://help.salesforce.com/s/articleView?id=ind.insurance_inspolicyservice_getoutofsequenceendorsementstatus.htm&language=en_US&type=5)**  
    Use this service to retrieve the current status of the OutOfSequenceEndorsement async job. The service accepts jobId, policyId, or referencePolicyNumber as an input to fetch the out-of-sequence endorsement operation status.
-   **[InsPolicyService:getPaymentSchedule](https://help.salesforce.com/s/articleView?id=ind.insurance_inspolicyservice__getpaymentschedule.htm&language=en_US&type=5)**  
    The InsPolicyService:getPaymentSchedule service returns the payment schedule of the InsurancePolicy. The Policy (Asset) object is not supported.
-   **[InsPolicyService:getPolicyAsyncJobStatus](https://help.salesforce.com/s/articleView?id=ind.insurance_inspolicyservice_getpolicyasyncjobstatus.htm&language=en_US&type=5)**  
    Use this service to fetch the status of the asynchronous batch job.
-   **[InsPolicyService:getPolicyDetails](https://help.salesforce.com/s/articleView?id=ind.insurance_inspolicyservice__getpolicydetails.htm&language=en_US&type=5)**  
    Use this service to get the coverages, insured items, pricing, and other information for an existing insurance policy, including optional coverages that weren't selected.
-   **[InsPolicyService:getPolicyVersions](https://help.salesforce.com/s/articleView?id=ind.insurance_inspolicyservice__getpolicyversions.htm&language=en_US&type=5)**  
    Use this service to retrieve the different versions of a policy. The service returns a list of policies with high level fields determined by the Policy field set **PolicyCompareHeader**.
-   **[InsPolicyService:getRuleLogs](https://help.salesforce.com/s/articleView?id=ind.insurance_inspolicyservice__getrulelogs.htm&language=en_US&type=5)**  
    This service retrieves rule logs for a target policy, sorted by execution date in ascending order.
-   **[InsPolicyService:initiateLapseGracePeriod](https://help.salesforce.com/s/articleView?id=ind.insurance_inspolicyservice__initiatelapsegraceperiod.htm&language=en_US&type=5)**  
    This service initiates a grace period on a policy, lapses a policy, or does nothing to a policy, depending on factors of the policy.
-   **[InsPolicyService:invokeProductRules](https://help.salesforce.com/s/articleView?id=ind.insurance_inspolicyservice__invokeproductrules.htm&language=en_US&type=5)**  
    Use this service with a policy to invoke underwriting rules you've added to a product.
-   **[InsPolicyService:invokeRules](https://help.salesforce.com/s/articleView?id=ind.insurance_inspolicyservice__invokerules.htm&language=en_US&type=5)**  
    Use this service to invoke state transition rules associated with a target state transaction on a target policy. If the rules satisfy the transition criteria, this service executes actions associated with the transition, optionally logs the results of the rule executions, and transitions the target policy to the new state.
-   **[InsPolicyService:modifyPaymentSchedule](https://help.salesforce.com/s/articleView?id=ind.insurance_inspolicyservice__modifypaymentschedule.htm&language=en_US&type=5)**  
    Use this service to modify an existing payment schedule based on a new Premium Frequency.
-   **[InsPolicyService:prepareToCancelPolicy](https://help.salesforce.com/s/articleView?id=ind.insurance_inspolicyservice__preparetocancelpolicy.htm&language=en_US&type=5)**  
    Use this service to calculate the premium price difference before canceling a policy. The service prorates the premium, fee, and tax amounts, and calculates the premium, fee, and tax refund.
-   **[InsPolicyService:prepareToRenewPolicy](https://help.salesforce.com/s/articleView?id=ind.insurance_inspolicyservice__preparetorenewpolicy.htm&language=en_US&type=5)**  
    Use this service to calculate the amount required for renewing an existing policy. This service returns renewal premium, taxes, and fees, or the renewal policy JSON without creating a policy.
-   **[InsPolicyService:removeInsuredItem](https://help.salesforce.com/s/articleView?id=ind.insurance_inspolicyservice__removeinsureditem.htm&language=en_US&type=5)**  
    Use this service to remove an insured item from an existing policy.
-   **[InsPolicyService:renewPoliciesInBatch](https://help.salesforce.com/s/articleView?id=ind.insurance_inspolicyservice__renewpoliciesinbatch.htm&language=en_US&type=5)**  
    Use this service to control the number of Apex jobs to initiate, and the number of batches to run per Apex job, for a large number of policy renewals.
-   **[InsPolicyService:verifyCoverage](https://help.salesforce.com/s/articleView?id=ind.insurance_inspolicyservice__verifycoverage.htm&language=en_US&type=5)**  
    Use this service to verify valid insurance coverage for a policyholder who is filing a claim.

Did this article solve your issue?

Let us know so we can improve!

YesNo