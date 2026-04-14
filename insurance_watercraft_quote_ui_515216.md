---
title: "Watercraft Quote UI"
source: "https://help.salesforce.com/s/articleView?id=ind.insurance_watercraft_quote_ui_515216.htm&language=en_US&type=5"
scraped: "2026-04-14"
filter: "ind.insurance_"
---# Watercraft Quote UI

Watercraft Quote UI[](https://help.salesforce.com/s?language=en_US)

You are here:

1.  [Salesforce Help](/s/?language=en_US)
2.  [Docs](/s/products?language=en_US)
3.  [Digital Insurance](https://help.salesforce.com/s/articleView?id=ind.insurance_admin_standard.htm&language=en_US&type=5)

# Watercraft Quote UI

Follow a user-friendly workflow and create a quote from the Lex console, which is built with Lightning Web Components.

All our screenshots are currently in Lightning style. Your spin may look different because it's using the Newport style in the Broker Portal and Customer Portal.

1.  To create a new quote, do not go to the Quote page. Instead, go to the Opportunities page and choose the Opportunity you're creating the quote for.
    
    [](https://help.salesforce.com/s?language=en_US)Note
    
    Before you create a quote on an Opportunity, go to the Details tab and make sure that the Opportunity has a pricebook assigned.
    
2.  On the right pane, in Quotes, click the carat and choose New Quote.
3.  Select **Quote** for all Auto quotes and click **Next**.
4.  On the New Quote: Quote window, enter a name for this quote, then click **Save**.
    
    Do not enter any other information here. Any info you enter here will mess up your quote as you create it on the Vlocity Quote UI.
    
5.  Now, navigate to the Quote page. On the Quote list view, choose the quote you just created.
6.  On the quote, click **Add Product** to start building the structure of your quote based on a product model.
7.  [](https://help.salesforce.com/s?language=en_US)Choose the **Marine** product and click **Add**.
8.  Click the **Marine** bar to configure policy-level coverages.
9.  You can change attribute values on required coverages, and select any available optional coverages by clicking **Add**.
10.  [](https://help.salesforce.com/s?language=en_US)After you've finished configuring policy-level coverages, you can add a vessel. Click **Add Vessel**.
     
     The Vessel appears under the Marine insurance product.
     
11.  [](https://help.salesforce.com/s?language=en_US)Click the **Vessel** bar to open all the coverages for this vessel.
     
     You can change attribute values on required coverages, and select any available optional coverages by clicking **Add**.
     
12.  After you've configured coverages for the vessel, you can click **Rate Now** on Marine.
     
     Insurance uses the rating procedure defined for Marine, and returns a Total premium with any applicable taxes and fees. It also includes the price for the vessel and prices for each coverage.
     
     You can add multiple vessels to a quote. Insurance uses the multi-instance product model to correctly rate the quote.
     

Did this article solve your issue?

Let us know so we can improve!

YesNo