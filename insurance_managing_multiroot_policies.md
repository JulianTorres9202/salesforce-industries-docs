---
title: "Managing Multiroot Policies"
source: "https://help.salesforce.com/s/articleView?id=ind.insurance_managing_multiroot_policies.htm&language=en_US&type=5"
scraped: "2026-04-14"
filter: "ind.insurance_"
---# Managing Multiroot Policies

Managing Multiroot Policies[](https://help.salesforce.com/s?language=en_US)

You are here:

1.  [Salesforce Help](/s/?language=en_US)
2.  [Docs](/s/products?language=en_US)
3.  [Digital Insurance](https://help.salesforce.com/s/articleView?id=ind.insurance_admin_standard.htm&language=en_US&type=5)

# Managing Multiroot Policies

Multiroot policies help insurance carriers enhance their product offerings by bundling multiple insurance products, such as auto and home insurance, into a single policy. This approach provides versatile coverage options that you can market and sell as a unified package.

### Required Editions

<table class="slds-table slds-table_bordered slds-m-bottom_small edition" lwc-3eigj2skqo3=""><colgroup lwc-3eigj2skqo3=""><col style="width:100%" lwc-3eigj2skqo3=""></colgroup><tbody lwc-3eigj2skqo3=""><tr class="" lwc-3eigj2skqo3=""><td style="vertical-align:top;" class="slds-cell-wrap" lwc-3eigj2skqo3="">Available in: Lightning Experience in&nbsp;<strong lwc-3eigj2skqo3="">Professional</strong>,&nbsp;<strong lwc-3eigj2skqo3="">Enterprise</strong>, and&nbsp;<strong lwc-3eigj2skqo3="">Unlimited</strong>&nbsp;editions with the Insurance Industries managed package.</td></tr></tbody></table>

As part of the multiroot policy services, you can:

[](https://help.salesforce.com/s?language=en_US)

-   Create multiroot insurance policies from multiroot quotes by using the `InsPolicyService.createMultiRootPolicy` service.
    
-   Modify existing multiroot policies based on evolving user needs by using the `InsPolicyService.createMultiRootPolicyVersion` service.This service includes adding or removing root products, ensuring that the policy remains relevant and valuable over time.
    
-   Create an endorsement quote from a multiroot policy by using the `InsQuoteService.createEndorsementQuote` service.
    
-   Manage all transactions related to these policies.The streamlined management of bundled policies simplifies internal operations, reducing administrative overhead, and improving efficiency.
    
-   Retrieve the status of asynchronous policy administration jobs by using the `InsPolicyService.getPolicyAsyncJobStatus` service.
    

-   **[Hierarchical Structure and Features of Multiroot Policies](https://help.salesforce.com/s/articleView?id=ind.insurance_features_multiroot_policies.htm&language=en_US&type=5)**  
    Multiroot policies are organized in a hierarchical structure. A parent policy serves as the primary entity, connecting to multiple child policies, each representing a specific insurance product within the bundle. This approach provides a clear and comprehensive representation of the entire multiroot policy.
-   **[Support for Additional Fields](https://help.salesforce.com/s/articleView?id=ind.insurance_additional_fields_support_multiroot_policies.htm&language=en_US&type=5)**  
    Use the additional fields option to include custom fields or override Quote fields in both parent and child multiroot policies.
-   **[Considerations and Limitations](https://help.salesforce.com/s/articleView?id=ind.insurance_limitations_for_multiroot_policies.htm&language=en_US&type=5)**  
    Here are some things to keep in mind about multiroot policies.

#### See Also

-   [InsPolicyService:createMultiRootPolicy](https://help.salesforce.com/s/articleView?id=ind.insurance_inspolicyservice_createmultirootpolicy.htm&language=en_US&type=5)
-   [InsPolicyService:createMultiRootPolicyVersion](https://help.salesforce.com/s/articleView?id=ind.insurance_inspolicyservice_createmultirootpolicyversion.htm&language=en_US&type=5)
-   [InsQuoteService:createEndorsementQuote](https://help.salesforce.com/s/articleView?id=ind.insurance_insquoteservice_createendorsementquote.htm&language=en_US&type=5)
-   [InsPolicyService:getPolicyAsyncJobStatus](https://help.salesforce.com/s/articleView?id=ind.insurance_inspolicyservice_getpolicyasyncjobstatus.htm&language=en_US&type=5)

Did this article solve your issue?

Let us know so we can improve!

YesNo