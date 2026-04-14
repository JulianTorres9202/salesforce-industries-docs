---
title: "Create Lightning Record Pages for Insurance"
source: "https://help.salesforce.com/s/articleView?id=ind.insurance_create_lightning_record_pages_asof242.htm&language=en_US&type=5"
scraped: "2026-04-14"
filter: "ind.insurance_"
---# Create Lightning Record Pages for Insurance

Create Lightning Record Pages for Insurance[](https://help.salesforce.com/s?language=en_US)

You are here:

1.  [Salesforce Help](/s/?language=en_US)
2.  [Docs](/s/products?language=en_US)
3.  [Digital Insurance](https://help.salesforce.com/s/articleView?id=ind.insurance_admin_standard.htm&language=en_US&type=5)

# Create Lightning Record Pages for Insurance

Create the Lightning record pages that apply to Insurance and Insurance Industries Extension orgs.

1.  From Setup, use Quick Find to find and select Lightning App Builder.
2.  Click **New**.
3.  Select **Record Page**, then click **Next**.
4.  For **Label**, enter a unique, descriptive name. For example:
    
    -   Claim Product Record Page
        
    -   Product Record Page
        
    -   Product Class Record Page
        
    -   Product Coverage Record Page
        
    -   Product Spec Record Page
        
    
    For **Object**, enter Product. Then click **Next**.
    
5.  For the page template, click **Clone Salesforce Default Page**, and then select **Grouped View Default**. Then click **Finish**.
6.  Click the **Tabs** component, then click **Add Tab**.
    
    Add the custom tabs that belong on the page. Here are the typical ones.
    
    | Record Page | Custom Tabs |
    | --- | --- |
    | Claim Product | [](https://help.salesforce.com/s?language=en_US)
    -   Injuries
    -   Properties
    -   API
    -   Rules
    
     |
    | Product | 
    
    -   Coverages
    -   Insured Items
    -   Rating Facts
    -   Attributes
    -   Rules
    -   Surcharges
    -   Simulate
    -   API
    
     |
    | Product Class | [](https://help.salesforce.com/s?language=en_US)
    
    -   Coverages
    -   Insured Items
    -   Rating Facts
    -   Attributes
    -   Rules
    
     |
    | Product Coverage | [](https://help.salesforce.com/s?language=en_US)
    
    -   Attributes
    -   Surcharges
    
     |
    | Product Spec | [](https://help.salesforce.com/s?language=en_US)
    
    -   Attributes
    
     |
    
7.  Find the **Vlocity Cards** component and drag it to a custom tab. Then define the appropriate **Layout Name** and **Custom Visualforce Page**. Do this for each custom tab.
    
    Here are the values for each type of record page.
    
    | Record Page | Tab | Properties |
    | --- | --- | --- |
    | Claim Product | Injuries | 
    **Layout Name**: ins-claims-injuries-admin-container
    
    [](https://help.salesforce.com/s?language=en_US)**Custom Visualforce Page**: InsuranceClaimsInjuriesAdmin
    
     |
    | Properties | 
    
    **Layout Name**: ins-claims-properties-admin-container
    
    [](https://help.salesforce.com/s?language=en_US)**Custom Visualforce Page**: InsuranceClaimsPropertiesAdmin
    
     |
    | API | 
    
    **Layout Name**: ins-product-methods-helper
    
    [](https://help.salesforce.com/s?language=en_US)**Custom Visualforce Page**: InsuranceProductMethodsHelper
    
     |
    | Rules | 
    
    **Layout Name**: ins-product-rules
    
    [](https://help.salesforce.com/s?language=en_US)**Custom Visualforce Page**: InsuranceProductRules
    
     |
    | 
    
    Product
    
     | Coverages | 
    
    **Layout Name**: ins-coverage-container
    
    **Custom Visualforce Page**: InsuranceCoverages
    
     |
    | Insured Items | 
    
    **Layout Name**: ins-insured-items-container
    
    **Custom Visualforce Page**: InsuranceInsuredItems
    
     |
    | 
    
    Rating Facts
    
     | 
    
    [](https://help.salesforce.com/s?language=en_US)**Layout Name**: ins-rating-fact-container
    
    [](https://help.salesforce.com/s?language=en_US)**Custom Visualforce Page**: InsuranceRatingFact
    
     |
    | 
    
    Attributes
    
     | 
    
    [](https://help.salesforce.com/s?language=en_US)**Layout Name**: ins-product-attributes-container
    
    [](https://help.salesforce.com/s?language=en_US)**Custom Visualforce Page**: InsuranceProductAttributes
    
     |
    | 
    
    Rules
    
     | 
    
    [](https://help.salesforce.com/s?language=en_US)**Layout Name**: ins-product-rules
    
    [](https://help.salesforce.com/s?language=en_US)**Custom Visualforce Page**: InsuranceProductRules
    
     |
    | 
    
    Surcharges
    
     | 
    
    [](https://help.salesforce.com/s?language=en_US)**Layout Name**: ins-product-taxes-container
    
    [](https://help.salesforce.com/s?language=en_US)**Custom Visualforce Page**: InsuranceTaxesAdmin
    
     |
    | 
    
    Simulate
    
     | 
    
    [](https://help.salesforce.com/s?language=en_US)**Layout Name**: ins-product-rating-output-input-map
    
    [](https://help.salesforce.com/s?language=en_US)**Custom Visualforce Page**: InsuranceProductRatingMap
    
     |
    | 
    
    API
    
     | 
    
    [](https://help.salesforce.com/s?language=en_US)**Layout Name**: ins-product-methods-helper
    
    [](https://help.salesforce.com/s?language=en_US)**Custom Visualforce Page**: InsuranceProductMethodsHelper
    
     |
    | 
    
    Product Class
    
     | 
    
    Coverages
    
     | 
    
    [](https://help.salesforce.com/s?language=en_US)**Layout Name**: ins-coverage-container
    
    [](https://help.salesforce.com/s?language=en_US)**Custom Visualforce Page**: InsuranceCoverages
    
     |
    | 
    
    Insured Items
    
     | 
    
    [](https://help.salesforce.com/s?language=en_US)**Layout Name**: ins-insured-items-container
    
    [](https://help.salesforce.com/s?language=en_US)**Custom Visualforce Page**: InsuranceInsuredItems
    
     |
    | 
    
    Rating Facts
    
     | 
    
    [](https://help.salesforce.com/s?language=en_US)**Layout Name**: ins-rating-fact-container
    
    [](https://help.salesforce.com/s?language=en_US)**Custom Visualforce Page**: InsuranceRatingFact
    
     |
    | 
    
    Attributes
    
     | 
    
    [](https://help.salesforce.com/s?language=en_US)**Layout Name**: ins-product-attributes-container
    
    [](https://help.salesforce.com/s?language=en_US)**Custom Visualforce Page**: InsuranceProductAttributes
    
     |
    | 
    
    Rules
    
     | 
    
    [](https://help.salesforce.com/s?language=en_US)**Layout Name**: ins-product-rules
    
    [](https://help.salesforce.com/s?language=en_US)**Custom Visualforce Page**: InsuranceProductRules
    
     |
    | 
    
    Product Coverage
    
     | 
    
    Attributes
    
     | 
    
    [](https://help.salesforce.com/s?language=en_US)**Layout Name**: ins-product-attributes-container
    
    [](https://help.salesforce.com/s?language=en_US)**Custom Visualforce Page**: InsuranceProductAttributes
    
     |
    | 
    
    Surcharges
    
     | 
    
    [](https://help.salesforce.com/s?language=en_US)**Layout Name**: ins-product-taxes-container
    
    [](https://help.salesforce.com/s?language=en_US)**Custom Visualforce Page**: InsuranceTaxesAdmin
    
     |
    | 
    
    Product Spec
    
     | 
    
    Attributes
    
     | 
    
    [](https://help.salesforce.com/s?language=en_US)**Layout Name**: ins-product-attributes-container
    
    [](https://help.salesforce.com/s?language=en_US)**Custom Visualforce Page**: InsuranceProductAttributes
    
     |
    
    Lightning record pages are now configured in your org. Activate them to make them available to users. See [Activate the Lightning Record Pages You Create](https://help.salesforce.com/s/articleView?id=ind.insurance_activate_the_lightning_record_pages_you_create.htm&language=en_US&type=5 "To make Lightning record pages available to your users, activate them. You can activate a page when you save it for the first time or later using the Activation button.").
    

Did this article solve your issue?

Let us know so we can improve!

YesNo