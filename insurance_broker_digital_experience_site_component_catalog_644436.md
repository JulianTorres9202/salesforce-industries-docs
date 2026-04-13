---
title: "Broker Digital Experience Site Component Catalog"
source: "https://help.salesforce.com/s/articleView?id=ind.insurance_broker_digital_experience_site_component_catalog_644436.htm&language=en_US&type=5"
scraped: "2026-04-13"
filter: "ind.insurance_"
---# Broker Digital Experience Site Component Catalog

Broker Digital Experience Site Component Catalog[](https://help.salesforce.com/s?language=en_US)

You are here:

1.  [Salesforce Help](/s/?language=en_US)
2.  [Docs](/s/products?language=en_US)
3.  [Digital Insurance](https://help.salesforce.com/s/articleView?id=ind.insurance_admin_standard.htm&language=en_US&type=5)

# Broker Digital Experience Site Component Catalog

The Broker site contains a bunch of components to get you started with providing your brokers with functionality they can use to create quotes, issue policies, and manage policies.

These components fall into three categories:

-   FlexCard Based Components
    
    Created for use in the Broker site, these components use FlexCards that you can customize and activate to compile LWCs for use in the site
    
-   LWCs
    
    Used in multiple UIs, you can extend these components to make changes specific to the Broker site
    
-   Classic Card Based Components
    
    Used in multiple UIs, you can customize these components in the Classic Card designer and activate them to generate LWS for use in the site
    

Some of these components call data sources:

-   Omnistudio Data Mappers
    
-   Integration Procedures
    
-   [Insurance Services Catalog](https://help.salesforce.com/s/articleView?id=ind.insurance_insurance_and_health_insurance_services_catalog.htm&language=en_US&type=5 "Get quote, policy, and claims systems up and running by using an extensive catalog of Digital Insurance Platform services. The services are methods of Apex classes that carry out common actions for insurance companies and health plans. They help you build end-to-end business processes faster by reducing or eliminating the need for custom programming.")
    
    To learn more about specific services used by experience components, go to the topic linked here, find the service, and click its link.
    

All of these data sources come out-of-the-box with Vlocity Insurance. The Data Mappers and Integration Procedures are listed in tables below.

| 
Component

 | 

LWC Name

 | 

What It Does

 |
| --- | --- | --- |
| 

[Insurance Account Record Header Component](https://help.salesforce.com/s/articleView?id=ind.insurance_t_insurance_account_record_header_component_645076.htm&language=en_US&type=5 "This component shows brokers a snapshot of data about the account they're looking at. This info can help them contact the account holder and chat about the weather in their location as an icebreaker.")

 | 

cfInsAccountHeader

 | 

Displays information about the specified account in its header.

 |
| 

[Insurance Account Quote List Component](https://help.salesforce.com/s/articleView?id=ind.insurance_t_insurance_account_quote_list_component_644983.htm&language=en_US&type=5 "On this component, brokers see a list of all the quotes attached to a specific account.")

 | 

cfInsAccountQuoteList

 | 

Displays a list of quotes attached to the specified account.

 |
| 

[Insurance Account Insurance Policy List Component](https://help.salesforce.com/s/articleView?id=ind.insurance_t_insurance_account_insurance_policy_list_component_644687.htm&language=en_US&type=5 "On this component, brokers can see a list plus key details about each policy attached to a specific account.")

 | 

cfInsAccountInsurancePolicyList

 | 

Displays a list of insurance policies attached to the specified account (FSC).

 |
| 

[Insurance Account (Asset) Policy List Component](https://help.salesforce.com/s/articleView?id=ind.insurance_t_insurance_accountassetpolicy_list_component_644807.htm&language=en_US&type=5 "On this component, brokers can see a list plus key details about each policy attached to a specific account.")

 | 

cfInsAccountPolicyList

 | 

Displays a list of policies attached to the specified account (asset-based policy records).

 |
| 

[Insurance Quote List Component for the Homepage](https://help.salesforce.com/s/articleView?id=ind.insurance_quote_list_component_for_the_homepage_645171.htm&language=en_US&type=5 "Your brokers need to see the quotes they're working on in list form. This component displays that list.")

 | 

cfInsQuoteListCard

 | 

Displays a list of quotes on the homepage of the site.

 |
| 

[Insurance Insurance Policy Record Header Component](https://help.salesforce.com/s/articleView?id=ind.insurance_t_insurance_insurance_policy_record_header_component_645561.htm&language=en_US&type=5 "This component shows brokers a snapshot of data about the insurance policy they're looking at.")

 | 

cfInsInsurancePolicyHeader

 | 

Displays information about the specified insurance policy (FSC).

 |
| 

[Insurance Account Asset Record Header Component](https://help.salesforce.com/s/articleView?id=ind.insurance_t_insurance_account_asset_record_header_component_645367.htm&language=en_US&type=5 "This component shows brokers a snapshot of data about the asset-based policy they're looking at.")

 | 

cfInsAccountAssetHeader

 | 

Displays information about the specified insurance policy (asset-based policy records).

 |
| 

[Insurance Quote Record Header](https://help.salesforce.com/s/articleView?id=ind.insurance_quote_record_header_645467.htm&language=en_US&type=5 "This component shows brokers a snapshot of data about the quote they're looking at. This info can help them get a quick idea of the status of the quote, including the quote status and the date the quote expires.")

 | 

cfInsQuoteHeader

 | 

Display information about the specified quote.

 |
| 

[Insurance Account Policy List Flyout](https://help.salesforce.com/s/articleView?id=ind.insurance_t_insurance_account_policy_list_flyout_644916.htm&language=en_US&type=5 "Users can click a link on the Insurance Account Insurance Policy List Component or the Insurance Account (Asset) Policy List Component component to see the contents of this component, which shows additional information about the price of the policy.")

 | 

cfInsAccountPolicyListFlyout

 | 

Displays additional information about a policy in a flyout

Called by Account Insurance Policy List and Account Policy List.

 |

| 
Component

 | 

LWC Name

 |
| --- | --- |
| 

Vlocity State Transition

 | 

**stateTransition**

 |
| 

Vlocity Rules Log

 | 

**rulesLog**

 |
| 

Vlocity Insurance Policy

 | 

**insPolicy**

 |
| 

Vlocity Insurance Policy Insured Items

 | 

**insPolicyInsuredItems**

 |
| 

Vlocity Insurance Quote

 | 

**insQuote**

 |
| 

Vlocity Insurance Quote Insured Items

 | 

**insQuoteInsuredItems**

 |
| 

Insurance Trailing Documents Components

 | 

**insTrailingDocuments**

 |

| 
Component

 | 

LWC Names

 | 

What It Does

 |
| --- | --- | --- |
| 

**ins-quote-actions**

 | 

**cfInsQuoteActions**

 | 

Displays actions a user can take from the Quote page, and contains a pubsub action that lets the user issue an insurance policy.

 |
| 

**ins-insurance-policy-actions**

 | 

**cfInsInsurancePolicyActions**

 | 

Displays actions a user can take from the Policy page. This component comes with pre-built ations to modify policies and create endorsement quotes.

 |

| 
Data Mapper

 | 

Components that Use It

 |
| --- | --- |
| 

**InsGetQuoteByProducer**

 | 

Quote List (on the Homepage)

 |
| 

**InsGetAccountInsurancePolicyList**

 | 

Account Insurance Policy List

 |
| 

**InsGetAccountPolicyList**

 | 

Account Policy List (Asset)

 |
| 

**InsGetAccountQuoteList**

 | 

Account Quote List

 |

| 
Integration Procedure

 | 

Components that Use It

 |
| --- | --- |
| 

**InsRecordHeader\_getDetails**

 | 

Account Record Header

 |
| 

**InsRecordHeaderQuote\_getDetails**

 | 

Quote Record header

 |

-   **[Insurance Account Insurance Policy List Component](https://help.salesforce.com/s/articleView?id=ind.insurance_t_insurance_account_insurance_policy_list_component_644687.htm&language=en_US&type=5)**  
    On this component, brokers can see a list plus key details about each policy attached to a specific account.
-   **[Insurance Account (Asset) Policy List Component](https://help.salesforce.com/s/articleView?id=ind.insurance_t_insurance_accountassetpolicy_list_component_644807.htm&language=en_US&type=5)**  
    On this component, brokers can see a list plus key details about each policy attached to a specific account.
-   **[Insurance Account Quote List Component](https://help.salesforce.com/s/articleView?id=ind.insurance_t_insurance_account_quote_list_component_644983.htm&language=en_US&type=5)**  
    On this component, brokers see a list of all the quotes attached to a specific account.
-   **[Insurance Account Record Header Component](https://help.salesforce.com/s/articleView?id=ind.insurance_t_insurance_account_record_header_component_645076.htm&language=en_US&type=5)**  
    This component shows brokers a snapshot of data about the account they're looking at. This info can help them contact the account holder and chat about the weather in their location as an icebreaker.
-   **[Insurance Quote List Component for the Homepage](https://help.salesforce.com/s/articleView?id=ind.insurance_quote_list_component_for_the_homepage_645171.htm&language=en_US&type=5)**  
    Your brokers need to see the quotes they're working on in list form. This component displays that list.
-   **[insRecordListTable LWC](https://help.salesforce.com/s/articleView?id=ind.insurance_t_insrecordlisttable_lwc_645253.htm&language=en_US&type=5)**  
    This component displays a list of records from a data source that is provided to the component.
-   **[insRecordHeader LWC](https://help.salesforce.com/s/articleView?id=ind.insurance_t_insrecordheader_lwc_645312.htm&language=en_US&type=5)**  
    This component displays record data as a header.
-   **[Insurance Account Asset Record Header Component](https://help.salesforce.com/s/articleView?id=ind.insurance_t_insurance_account_asset_record_header_component_645367.htm&language=en_US&type=5)**  
    This component shows brokers a snapshot of data about the asset-based policy they're looking at.
-   **[Insurance Quote Record Header](https://help.salesforce.com/s/articleView?id=ind.insurance_quote_record_header_645467.htm&language=en_US&type=5)**  
    This component shows brokers a snapshot of data about the quote they're looking at. This info can help them get a quick idea of the status of the quote, including the quote status and the date the quote expires.
-   **[Insurance Insurance Policy Record Header Component](https://help.salesforce.com/s/articleView?id=ind.insurance_t_insurance_insurance_policy_record_header_component_645561.htm&language=en_US&type=5)**  
    This component shows brokers a snapshot of data about the insurance policy they're looking at.

Did this article solve your issue?

Let us know so we can improve!

YesNo