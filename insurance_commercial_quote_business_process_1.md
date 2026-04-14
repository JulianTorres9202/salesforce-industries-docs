---
title: "Commercial Quote Business Process"
source: "https://help.salesforce.com/s/articleView?id=ind.insurance_commercial_quote_business_process_1.htm&language=en_US&type=5"
scraped: "2026-04-14"
filter: "ind.insurance_"
---# Commercial Quote Business Process

Commercial Quote Business Process[](https://help.salesforce.com/s?language=en_US)

You are here:

1.  [Salesforce Help](/s/?language=en_US)
2.  [Docs](/s/products?language=en_US)
3.  [Digital Insurance](https://help.salesforce.com/s/articleView?id=ind.insurance_admin_standard.htm&language=en_US&type=5)

# Commercial Quote Business Process

We've created a quote business process for General Liability for you to examine, use as an example, and extend to create your own business processes for insurance.

You can create and modify quotes directly on the Quote UI, which is built with Lightning Web Components.

1.  To create a quote, we don't start on the Quote page. Instead, we go to the Opportunities page and choose the Opportunity we're creating the quote for.
    
    [](https://help.salesforce.com/s?language=en_US)Important
    
    Before you create a quote on an Opportunity, go to the Details tab and make sure that the Opportunity has a pricebook assigned.
    
2.  From the Actions Panel, click **Commercial Quote**.
    
    If you don't see this option in your opportunity, check if your opportunity is linked to a business account.
    
3.  Enter quote details and click **Next**.
4.  Select a plan to add it to your quote and click **Next**.
5.  That's it! Your quote is ready. To proceed with rating your quote, click **View Quote**.
6.  You can now add either building, or a business, or both to this quote and have them insured.
    
    To add the location of the building you want to insure, click **Add Location**.
    
7.  Enter location information and click **Save**.
8.  [](https://help.salesforce.com/s?language=en_US)The location appears in your quote. Now you can add a building to it by clicking **\+ Building** and then selecting **Create New**.
9.  [](https://help.salesforce.com/s?language=en_US)To add the business you want to insure, click **Add Business**.
10.  Enter the business details and click **Save**. You see the business in your quote.
11.  After configuring all your coverages, click **Rate Now**.
     
     [](https://help.salesforce.com/s?language=en_US)Using the rating procedure defined for General Liability and returns a Total premium with any applicable taxes and fees.
     

-   **[Commercial Quote OmniScript](https://help.salesforce.com/s/articleView?id=ind.insurance_t_commercial_quote_omniscript_526722.htm&language=en_US&type=5)**  
    Commercial quoting is powered by the Commercial Quote OmniScript. It uses Rating Procedures, Integration Procedures, Omnistudio Data Mappers, LWCs, and FlexCards to create the guided flow.

Did this article solve your issue?

Let us know so we can improve!

YesNo