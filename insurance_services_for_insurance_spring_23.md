---
title: "Services for Insurance Spring '23"
source: "https://help.salesforce.com/s/articleView?id=ind.insurance_services_for_insurance_spring_23.htm&language=en_US&type=5"
scraped: "2026-04-14"
filter: "ind.insurance_"
---# Services for Insurance Spring '23

Services for Insurance Spring '23[](https://help.salesforce.com/s?language=en_US)

You are here:

1.  [Salesforce Help](/s/?language=en_US)
2.  [Docs](/s/products?language=en_US)
3.  [Digital Insurance](https://help.salesforce.com/s/articleView?id=ind.insurance_admin_standard.htm&language=en_US&type=5)

# Services for Insurance Spring '23

Explore new services and updates to existing services in Spring '23.

## New Services

[InsClaimItemService:claimCoverageValuation](https://help.salesforce.com/s/articleView?id=ind.insurance_insclaimitemservice_claimcoveragevaluation.htm&language=en_US&type=5 "Use this service to verify that users have the authority to pay or approve amounts in different types of financial activities.")

-   Verifies that users have the authority to pay or approve amounts in different types of financial activities. Also verifies the maximum payment and approval amount that a user can configure for someone else.
    

[InsPolicyService:cancelPoliciesInBulk](https://help.salesforce.com/s/articleView?id=ind.insurance_inspolicyservice_cancelpoliciesinbulk.htm&language=en_US&type=5 "Use this service to cancel policy records (InsurancePolicy) in bulk. The service uses InsPolicyService:cancelPolicy service and Vlocity batch Framework to process the cancellation of multiple policies asynchronously.")

-   Deletes insurance policy records in bulk using InsPolicyService: cancelPolicy service.
    

## Updated Services

[InsEnrollmentServiceStd:enrollMembers](https://help.salesforce.com/s/articleView?id=ind.insurance_insenrollmentservicestd__enrollmembers.htm&language=en_US&type=5 "Use this service to enroll census members into their selected plans.")

-   New `saveMemberPremium` remote option
    

[InsPolicyService:cancelPolicy](https://help.salesforce.com/s/articleView?id=ind.insurance_inspolicyservice__cancelpolicy.htm&language=en_US&type=5 "Use this service to cancel an existing insurance policy.")

-   New `additionalFees` remote option
    

[InsPolicyService:createPaymentSchedule](https://help.salesforce.com/s/articleView?id=ind.insurance_inspolicyservice__createpaymentschedule.htm&language=en_US&type=5 "The InsPolicyService:createPaymentSchedule service creates a payment schedule (and optionally an initial payment transaction) for the target policy. This applies to Insurance Policy object only. The Policy (Asset) object is not supported.")

-   New `coolingOffPeriod` remote option
    

[InsPolicyService:createUpdatePolicy](https://help.salesforce.com/s/articleView?id=ind.insurance_inspolicyservice__createupdatepolicy.htm&language=en_US&type=5 "Use this service to create a new insurance policy or to update an existing policy with new information.")

-   New `coolingOffPeriod` remote option
    

Did this article solve your issue?

Let us know so we can improve!

YesNo