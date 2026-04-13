---
title: "Common Features of Insurance Policy Administration"
source: "https://help.salesforce.com/s/articleView?id=ind.insurance_admin_policies_features.htm&language=en_US&type=5"
scraped: "2026-04-13"
filter: "ind.insurance_"
---# Common Features of Insurance Policy Administration

Common Features of Insurance Policy Administration[](https://help.salesforce.com/s?language=en_US)

You are here:

1.  [Salesforce Help](/s/?language=en_US)
2.  [Docs](/s/products?language=en_US)
3.  [Digital Insurance](https://help.salesforce.com/s/articleView?id=ind.insurance_admin_standard.htm&language=en_US&type=5)

# Common Features of Insurance Policy Administration

Learn how policy APIs and invocable actions manage policy transactions such as issuance, endorsement, renewal, and cancellation. Calculate term taxes based on transaction types and policy durations, and support both annual and nonannual policies.

[](https://help.salesforce.com/s?language=en_US)

## Insurance Policy Transactions

Updates to a policy during its term are managed through policy transactions. Each transaction creates an InsurancePolicyTransaction record.

Each InsurancePolicyTransaction record falls into one of these categories:

[](https://help.salesforce.com/s?language=en_US)

-   Issuance: The policy is sold or issued to the policyholder, generating the premium for the new policy.
    
-   Endorsement: There's a change in the premium for the policy term due to an endorsement.
    
-   Renewal: The policy is renewed for another term, generating the premium for the renewed policy.
    
-   Cancellation: The policy is terminated before its expiration date, generating the amount that must be refunded.
    

All transactions are linked to the original policy version of the terms.

## Insurance Policy Surcharge

The policy APIs and invocable actions calculate the term amount for taxes associated with each quote line item based on the policy transaction type and its duration. The APIs and invocable actions also use the isProrated and isRefundable values that were configured during the tax definition, for their calculations.

The Issue Insurance Policy API or issueInsurancePolicy action processes the context data to compute the term taxes for the policy based on the effectiveFromDate and effectiveToDate. It also creates surcharge records that are saved in the InsurancePolicySurcharge object.

The Endorse Insurance Policy API or endorseInsurancePolicy action processes the context data to compute the term taxes for the new policy version. It also creates surcharge records that are saved in the InsurancePolicySurcharge object. In addition, it prorates the amounts for existing records in the InsurancePolicySurcharge object for the previous policy version based on the endorsement effective date.

The Cancel Insurance Policy API or cancelInsurancePolicy action prorates the amounts for existing records in the InsurancePolicySurcharge object for the affected policy versions based on the cancellation date.

The Renew Insurance Policy API or renewInsurancePolicy action processes the context data to compute the term taxes for the renewed policy version based on the effectiveFromDate and effectiveToDate. It also creates surcharge records that are saved in the InsurancePolicySurcharge object.

## Support for Annual and Nonannual Policies

Policy administration supports both annual and nonannual durations. The policy duration, determined by the effectiveFromDate and effectiveToDate, can be less than a year, exactly 365 or 366 days, or span multiple years. The standard premium and tax are always considered annual, either 365 or 366 days, based on whether it's a leap year. The term premium and term tax are prorated based on the standard rates and the policy's effectiveFromDate and effectiveToDate.

## Gross Written Premium Calculation

The Gross Written Premium (GWP) calculation has been revised in the Winter '26 release to ensure accuracy and alignment with standard insurance accounting practices. Previously, the GWP calculation included taxes and fees, which led to discrepancies in how the total premium amount was represented. With this update, the formula has been adjusted to exclude taxes and fees, making sure that the GWP now reflects only the actual premium amount charged over the policy's term.

-   **[Insurance Policy Dynamic Attributes](https://help.salesforce.com/s/articleView?id=ind.insurance_admin_policies_dynamic_attributes.htm&language=en_US&type=5)**  
    Explore how dynamic attributes store values and how you query them with supported filters.

Did this article solve your issue?

Let us know so we can improve!

YesNo