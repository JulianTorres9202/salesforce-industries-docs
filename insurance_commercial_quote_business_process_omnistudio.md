---
title: "Commercial Quote Business Process"
source: "https://help.salesforce.com/s/articleView?id=ind.insurance_commercial_quote_business_process_omnistudio.htm&language=en_US&type=5"
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

[](https://help.salesforce.com/s?language=en_US)

1.  To create a quote, we **don't** start on the Quote page. Instead, we go to the Opportunities page and choose the Opportunity we're creating the quote for.
    
    Important
    
    Before you create a quote on an Opportunity, go to the Details tab and make sure that the Opportunity has a pricebook assigned.
    
    [](https://help.salesforce.com/s?language=en_US)
    1.  Click into the **Pricebook** field.
    2.  Enter Standard and click the magnifying glass to search for the Standard Pricebook.
    3.  Choose **Standard Pricebook**.
    4.  Click **Save**.
2.  From the Related Panel, click **New Quote**.
    
    If you don't see this option in your opportunity, check if your opportunity is linked to a business account.
    
3.  Select **Quote** and click **Next**.
4.  To enter product details on quote record, click **Add Product**.
5.  Select **Commercial Auto** as product and click **Add**.
6.  [](https://help.salesforce.com/s?language=en_US)You can now add either building, or a business, or both to this quote and have them insured.
    
    To add the business you want to insure, click **Add Business**. Enter the business details and click **Save**. You see the business in your quote.
    
7.  To add the location of the building you want to insure, click **Add Location**. Enter location information and click **Save**.
8.  To add vehicles as child item for location, click **Add Vehicle**.
9.  [](https://help.salesforce.com/s?language=en_US)The vehicle appears in your quote. Enter vehicle details.
10.  After configuring all your coverages, click **Rate Now**.
     
     [](https://help.salesforce.com/s?language=en_US)Using the rating procedure defined for Commercial Auto, it returns a Total premium with any applicable taxes and fees.
     

Did this article solve your issue?

Let us know so we can improve!

YesNo