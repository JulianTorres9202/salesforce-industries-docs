---
title: "Troubleshoot Policy Renewal Failures"
source: "https://help.salesforce.com/s/articleView?id=ind.insurance_policy_bulk_renew_troubleshooting.htm&language=en_US&type=5"
scraped: "2026-04-14"
filter: "ind.insurance_"
---# Troubleshoot Policy Renewal Failures

Troubleshoot Policy Renewal Failures[](https://help.salesforce.com/s?language=en_US)

You are here:

1.  [Salesforce Help](/s/?language=en_US)
2.  [Docs](/s/products?language=en_US)
3.  [Digital Insurance](https://help.salesforce.com/s/articleView?id=ind.insurance_admin_standard.htm&language=en_US&type=5)

# Troubleshoot Policy Renewal Failures

If some policy renewals fail because of errors, you can retry those policies by using a batch job or a custom action.

1.  Identify the failure.
    
    Check for common error messages in failed policies.
    
    -   Something went wrong while pricing the transaction. : java.lang.NullPointerException: Cannot invoke "Object.equals(Object)" because "newMode" is null
    -   industries.insurance.foundation.impl.exception.InsFoundationException: SF-0007-0001
    
2.  Retry the failed policies.
    -   Create an additional batch job that retrieves policies with a Failure status from the InsuranceAsyncBulkRecordDetail entity for a specific request, by using the jobIdentifier. This batch job then calls the renewInsurancePolicies invocation action.
    -   Create a custom action that retrieves records with a Failure status from InsuranceAsyncBulkRecordDetail based on the jobIdentifier, and then invokes the renewInsurancePolicies action.
3.  Reach out to your Salesforce rep for assistance if failures are because of limit breaches (for example, PricingApiCallRateLimit, ConfigApiCallRateLimit, BreDmMaxInvocationsPerHour).

Did this article solve your issue?

Let us know so we can improve!

YesNo