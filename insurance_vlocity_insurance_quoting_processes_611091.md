---
title: "Insurance Quoting Processes"
source: "https://help.salesforce.com/s/articleView?id=ind.insurance_vlocity_insurance_quoting_processes_611091.htm&language=en_US&type=5"
scraped: "2026-04-14"
filter: "ind.insurance_"
---# Insurance Quoting Processes

Insurance Quoting Processes[](https://help.salesforce.com/s?language=en_US)

You are here:

1.  [Salesforce Help](/s/?language=en_US)
2.  [Docs](/s/products?language=en_US)
3.  [Digital Insurance](https://help.salesforce.com/s/articleView?id=ind.insurance_admin_standard.htm&language=en_US&type=5)

# Insurance Quoting Processes

You can build quoting processes for your users in two ways: Lightning web components and OmniScripts. Lightning web components make up the processes that your internal users can use to create quotes for your customers. Use OmniScripts to create processes to guide your external users (like customers and partners).

[](https://help.salesforce.com/s?language=en_US)

## Quoting Lightning Web Component (LWC)

Insurance offers a quoting [LWC](https://developer.salesforce.com/docs/component-library/documentation/en/lwc) out of the box to help you create a seamless quoting experience for your users. Add products, coverages, and attributes to an existing quote, and customize them right on the quote LWC!

Here's an example of the quote LWC while configuring an auto insurance quote:

Note When configuring the Vlocity State Transition page for Insurance quoting, use InsuranceRuleService as the State Rules Class Name. For detailed setup instructions, see [Add State Model Components to an Existing Record Page](https://help.salesforce.com/s/articleView?id=ind.os_add_state_model_components_to_an_existing_record_page_180517.htm&language=en_US&type=5).

See [Quoting](https://help.salesforce.com/s/articleView?id=ind.insurance_vlocity_insurance_quoting_611024.htm&language=en_US&type=5 "To estimate how much a policy would cost, you use a quote. Create a quote by selecting products offered by the provider and using information supplied by the customer to calculate the estimate. The Insurance quoting solution brings everything you need right to your fingertips and does all of the heavy lifting for you.") to learn more.

[](https://help.salesforce.com/s?language=en_US)

## OmniScript

An OmniScript provides a way to define the desired series of steps in the quoting flow. [Use OmniScripts to Add and Modify Insured Items](https://help.salesforce.com/s/articleView?id=ind.insurance_use_omniscripts_to_add_and_modify_insured_items_614083.htm&language=en_US&type=5 "Vlocity Insurance offers an out-of-the-box form your users can use to add and modify insured items on the Quote UI. However, this form isn't customizable. If you want to use your own styles or add functionality to these processes, you can create an OmniScript and hook up that OmniScript to the Quote UI.") to learn more.

[](https://help.salesforce.com/s?language=en_US)

## Services

LWCs and OmniScripts both use [services](https://help.salesforce.com/s/articleView?id=ind.insurance_insurance_and_health_insurance_services_catalog.htm&language=en_US&type=5 "Get quote, policy, and claims systems up and running by using an extensive catalog of Digital Insurance Platform services. The services are methods of Apex classes that carry out common actions for insurance companies and health plans. They help you build end-to-end business processes faster by reducing or eliminating the need for custom programming.") to pull product and rating information into the quoting process.

[](https://help.salesforce.com/s?language=en_US)Products configured with attributes and rules get pulled into the quoting process via services that are central to the quoting process: 

[](https://help.salesforce.com/s?language=en_US)

-   **InsProductService:repriceProduct**
    
-   **InsQuoteService:invokeProductRules**
    
-   **InsQuoteService:invokeRules**
    
-   **InsQuoteService:createUpdateQuote**
    
-   **InsProductService:getRatedProducts**
    

[](https://help.salesforce.com/s?language=en_US)See our [services catalog](https://help.salesforce.com/s/articleView?id=ind.insurance_insurance_and_health_insurance_services_catalog.htm&language=en_US&type=5 "Get quote, policy, and claims systems up and running by using an extensive catalog of Digital Insurance Platform services. The services are methods of Apex classes that carry out common actions for insurance companies and health plans. They help you build end-to-end business processes faster by reducing or eliminating the need for custom programming.") for a full list of services that can support your quoting processes.

Did this article solve your issue?

Let us know so we can improve!

YesNo