---
title: "Create an Auto-Launched Flow"
source: "https://help.salesforce.com/s/articleView?id=ind.insurance_set_up_bulk_renewal_auto_launched_flow.htm&language=en_US&type=5"
scraped: "2026-04-14"
filter: "ind.insurance_"
---# Create an Auto-Launched Flow

Create an Auto-Launched Flow[](https://help.salesforce.com/s?language=en_US)

You are here:

1.  [Salesforce Help](/s/?language=en_US)
2.  [Docs](/s/products?language=en_US)
3.  [Digital Insurance](https://help.salesforce.com/s/articleView?id=ind.insurance_admin_standard.htm&language=en_US&type=5)

# Create an Auto-Launched Flow

Build a flow that receives input from the batch job and calls the renewInsurancePolicies invocation action for each policy record.

1.  In Setup, find and select **Flows**.
2.  Click **New Flow**.
3.  Select **Auto-Launched Flow (No Trigger)**.
4.  Add a text variable to pass the policy ID into the flow.
    1.  Add a new resource of type Variable.
    2.  Enter policyId as the API name.
    3.  Select **Text** as the data type.
    4.  Select **Available for input**.
        
        Any variable marked as Available for input must be passed a value from the batch job. If not, the flow throws an error.
        
5.  Create an Apex-defined variable of type renewInsurancePoliciesIAInputRep.
    1.  Add a resource of type Variable.
    2.  Specify an API name.
    3.  Select **Apex-Defined** as the data type.
    4.  Select **ConnectApi\_\_RenewInsurancePoliciesIAInputRep** as the Apex class.
    5.  Select **Available for input**.
6.  Add these variables to the flow.
    
    | Variable | description |
    | --- | --- |
    | policyId | Required |
    | jobIdentifier | Unique identifier for tracking and reporting |
    | priceBookId | Required for renewal quotes. If not provided, the Standard Pricebook recordId is used by default |
    | productSellingModel | Required for renewal quotes. The default is One Time |
    | sameTenure | By default, renewal policies and quotes are created with annual as the tenure. To retain the original tenure, set sameTenure=true |
    | issueQuote | Set to true to generate renewal quotes |
    | executeConfigurationRules | Run configuration rules if true |
    | executeQualificationRules | Run qualification rules if true (only for renewal quotes) |
    | flowAPINameWithNamespace | For changes during renewal, pass the pre-step flow name and namespace in the format, <namespace>\_\_<flowName> in the flowAPINameWithNamespace field. |
    | fieldSetIds | Copies additional fields from the original policy to the renewed policy. This applies only to policy renewals, not renewal quotes. The same set of fields and values is applied to all renewed policies. To set different values for specific policies, use a post-processing flow triggered by the InsPolicyRnwlStatusEvent after renewal. For renewal quotes, this field is ignored. If mandatory custom fields are required for quote creation, populate them in the pre-step flow by using context variables that are mapped in the context definition. The pre-step flow doesn't allow modifying effective dates. |
    
    Keep the number of steps in the flow to a minimum. Because batch jobs run in a single thread, too many steps can slow down the entire bulk renewal process.
    
7.  Save your changes, and activate the flow.

#### See Also

-   [Renew Insurance Policies Action](https://developer.salesforce.com/docs/atlas.en-us.insurance_developer_guide.meta/insurance_developer_guide/actions_obj_renew_insurance_policies.htm)
-   [Autolaunched Flow](https://help.salesforce.com/s/articleView?id=service.voice_conversation_intelligence_autolaunched_flow_setup.htm&language=en_US&type=5)

Did this article solve your issue?

Let us know so we can improve!

YesNo