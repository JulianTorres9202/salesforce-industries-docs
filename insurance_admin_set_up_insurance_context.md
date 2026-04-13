---
title: "Set Up the Context Service for Digital Insurance"
source: "https://help.salesforce.com/s/articleView?id=ind.insurance_admin_set_up_insurance_context.htm&language=en_US&type=5"
scraped: "2026-04-13"
filter: "ind.insurance_"
---# Set Up the Context Service for Digital Insurance

Set Up the Context Service for Digital Insurance[](https://help.salesforce.com/s?language=en_US)

You are here:

1.  [Salesforce Help](/s/?language=en_US)
2.  [Docs](/s/products?language=en_US)
3.  [Digital Insurance](https://help.salesforce.com/s/articleView?id=ind.insurance_admin_standard.htm&language=en_US&type=5)

# Set Up the Context Service for Digital Insurance

Simplify the sharing and consumption of business application data using Context Service. Acting as a generic module, Context Service forms a layer between applications and procedures, enabling easy retrieval and use of data across various industry clouds at every step of the process.

### Required Editions

<table class="slds-table slds-table_bordered slds-m-bottom_small edition" lwc-3eigj2skqo3=""><colgroup lwc-3eigj2skqo3=""><col lwc-3eigj2skqo3=""></colgroup><tbody lwc-3eigj2skqo3=""><tr class="" lwc-3eigj2skqo3=""><td style="vertical-align:top;" class="slds-cell-wrap" lwc-3eigj2skqo3="">Available in: Lightning Experience</td></tr><tr class="" lwc-3eigj2skqo3=""><td style="vertical-align:top;" class="slds-cell-wrap" lwc-3eigj2skqo3="">Available in: <strong lwc-3eigj2skqo3="">Developer</strong>, <strong lwc-3eigj2skqo3="">Enterprise</strong>, <strong lwc-3eigj2skqo3="">Professional</strong>, and <strong lwc-3eigj2skqo3="">Unlimited</strong> Editions of Industries clouds where Context Service is enabled</td></tr></tbody></table>

Using Context Service, your business users can enhance application performance by optimizing data access and eliminating redundant input. When an application sends a data request, the context fetches and loads all necessary data from the database onto itself. It then distributes the required data to specific processes to fulfill the application's request.

1.  Grant users access to Context Service objects and features. See [Turn On Context Service](https://help.salesforce.com/s/articleView?id=ind.context_service_turn_on_context_service.htm&language=en_US&type=5).
2.  Extend the InsuranceContext context definition and customize it with relevant attributes and tags. See [Extend the Insurance Context Definition for Digital Insurance](https://help.salesforce.com/s/articleView?id=ind.insurance_admin_set_up_create_insurance_context_definition.htm&language=en_US&type=5).
    
    Note Make sure that the InsuranceContext context definition includes the QuoteRecordType attribute and that the attribute is mapped to the Quote Record Type field on the Quote object.
    

-   **[Extend the InsuranceContext Definition for Digital Insurance](https://help.salesforce.com/s/articleView?id=ind.insurance_admin_set_up_create_insurance_context_definition.htm&language=en_US&type=5)**  
    Extend the InsuranceContext and customize it with relevant attributes and tags.

Did this article solve your issue?

Let us know so we can improve!

YesNo