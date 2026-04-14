---
title: "Renew Policies with Changes"
source: "https://help.salesforce.com/s/articleView?id=ind.insurance_policy_bulk_policy_renewal_with_changes.htm&language=en_US&type=5"
scraped: "2026-04-14"
filter: "ind.insurance_"
---# Renew Policies with Changes

Renew Policies with Changes[](https://help.salesforce.com/s?language=en_US)

You are here:

1.  [Salesforce Help](/s/?language=en_US)
2.  [Docs](/s/products?language=en_US)
3.  [Digital Insurance](https://help.salesforce.com/s/articleView?id=ind.insurance_admin_standard.htm&language=en_US&type=5)

# Renew Policies with Changes

Use an auto-launched flow to make changes to the policy before renewal. For bulk quote renewals, this flow is also recommended for updating additional fields, because copying additional fields by using fieldsets isn't supported.

1.  In Setup, find and select **Flows**.
2.  Click **New Flow**.
3.  Select **Auto-Launched Flow (No Trigger)**.
4.  Add a text variable to pass the policy ID into the flow.
    1.  Add a resource of type Variable.
    2.  Enter policyId as the API name.
    3.  Select **Text** as the data type.
    4.  Select **Available for input**.
5.  To retrieve the policy context by using the policyId, use the [Get Insurance Policy invocable action](https://developer.salesforce.com/docs/atlas.en-us.insurance_developer_guide.meta/insurance_developer_guide/actions_obj_get_insurance_policy.htm).
6.  Update the context.
    
    -   Use custom invocable actions to generate input nodes, if required.
    
    -   Use the [Product Rating invocable action](https://developer.salesforce.com/docs/atlas.en-us.insurance_developer_guide.meta/insurance_developer_guide/actions_obj_reprice_product.htm) to update the context values.
7.  Create a text variable to return the updated context ID.
    1.  Add a resource of type Variable.
    2.  Enter contextId as the API name.
    3.  Select **Text** as the data type.
    4.  Select **Available for output**.
8.  Pass the flow name as input to the renewInsurancePolicies invocation action by using the flowAPINameWithNamespace field. This applies to both quote and policy renewals.
9.  Save your changes, and activate the flow.

Did this article solve your issue?

Let us know so we can improve!

YesNo