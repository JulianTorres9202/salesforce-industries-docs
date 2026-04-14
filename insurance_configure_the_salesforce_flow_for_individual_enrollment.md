---
title: "Configure the Salesforce Flow for Individual Enrollment"
source: "https://help.salesforce.com/s/articleView?id=ind.insurance_configure_the_salesforce_flow_for_individual_enrollment.htm&language=en_US&type=5"
scraped: "2026-04-14"
filter: "ind.insurance_"
---# Configure the Salesforce Flow for Individual Enrollment

Configure the Salesforce Flow for Individual Enrollment[](https://help.salesforce.com/s?language=en_US)

You are here:

1.  [Salesforce Help](/s/?language=en_US)
2.  [Docs](/s/products?language=en_US)
3.  [Digital Insurance](https://help.salesforce.com/s/articleView?id=ind.insurance_admin_standard.htm&language=en_US&type=5)

# Configure the Salesforce Flow for Individual Enrollment

Use this flow to enable group census members to enroll themselves and their dependents into the selected plans.

To enable individual enrollment for a customer community user in an org where Person Account isn't enabled and Person Contacts is used to identify the policy owner, the contact ownership must be updated to account owner. You must set up a trigger on Contact before the Insert event. To learn how, see [Assign roles to account owner users](https://salesforce.stackexchange.com/questions/368108/portal-user-cannot-edit-own-account-and-cannot-create-new-contacts-portal-users/368109).

Tip Create a separate clone of the Enrollment\_Flow template for individual enrollment.

Note After you configure the flow, remove the Create User Invocable action.

Did this article solve your issue?

Let us know so we can improve!

YesNo