---
title: "Insurance Application Suite Renew a Policy Through Email"
source: "https://help.salesforce.com/s/articleView?id=ind.insurance_insurance_application_suite_renew_a_policy_through_email.htm&language=en_US&type=5"
scraped: "2026-04-14"
filter: "ind.insurance_"
---# Insurance Application Suite Renew a Policy Through Email

Insurance Application Suite Renew a Policy Through Email[](https://help.salesforce.com/s?language=en_US)

You are here:

1.  [Salesforce Help](/s/?language=en_US)
2.  [Docs](/s/products?language=en_US)
3.  [Digital Insurance](https://help.salesforce.com/s/articleView?id=ind.insurance_admin_standard.htm&language=en_US&type=5)

# Insurance Application Suite Renew a Policy Through Email

A week before your policy expires, you receive a reminder email to renew your policy. Here's what an example email looks like:

Here's what an example email looks like:

[](https://help.salesforce.com/s?language=en_US)The email has a link to see policy details as well as a link to quickly renew your policy.

[](https://help.salesforce.com/s?language=en_US)

1.  Click the link in the email to renew your policy.
2.  Modify your coverages, if required, and click **Next**.
3.  That's it! Your policy is renewed. To see the new policy, click **View Policy**.

[](https://help.salesforce.com/s?language=en_US)

[](https://help.salesforce.com/s?language=en_US)This email is sent out by the scheduled job **PolicyRenewBatch**. This job, in turn, calls the Integration Procedure **bulkRenewals** that checks the renewal date for all policies and then sends out an email to policies that expire within a week from the day the job is run. Schedule the job to run periodically so that all policies that are coming up for renewal can be covered.

Did this article solve your issue?

Let us know so we can improve!

YesNo