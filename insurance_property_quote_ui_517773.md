---
title: "Property Quote UI"
source: "https://help.salesforce.com/s/articleView?id=ind.insurance_property_quote_ui_517773.htm&language=en_US&type=5"
scraped: "2026-04-14"
filter: "ind.insurance_"
---# Property Quote UI

Property Quote UI[](https://help.salesforce.com/s?language=en_US)

You are here:

1.  [Salesforce Help](/s/?language=en_US)
2.  [Docs](/s/products?language=en_US)
3.  [Digital Insurance](https://help.salesforce.com/s/articleView?id=ind.insurance_admin_standard.htm&language=en_US&type=5)

# Property Quote UI

Follow a user-friendly workflow and create a quote from the Lex console, which is built with Lightning Web Components.

All our screenshots are currently in Lightning style. Your spin may look different because it's using the Newport style in the Broker Portal and Customer Portal.

1.  To create a new quote, do not go to the Quote page. Instead, go to the Opportunities page and choose the Opportunity you're creating the quote for.
    
    [](https://help.salesforce.com/s?language=en_US)Note
    
    Before you create a quote on an Opportunity, go to the Details tab and make sure that the Opportunity has a pricebook assigned.
    
2.  On the right pane, in Quotes, click the carat and choose New Quote.
3.  Select **Quote** and click **Next**.
4.  On the New Quote: Quote window, enter a name for this quote, then click **Save**.
    
    Do not enter any other information here. Any info you enter here will mess up your quote as you create it on the Vlocity Quote UI.
    
5.  Now, navigate to the Quote page. On the Quote list view, choose the quote you just created.
6.  On the **Coverages** tab of the quote, click **Add Product**to start building the structure of your quote based on a product model.
7.  For this example, we've selected the **Homeowners** product. Click **Add**.
8.  The Homeowners insurance product appears on the **Coverages** tab. The premium **Total** is $0 and colored red because it hasn't been rated yet. But we're not rating this quote yet. First we need to add an insured item. Click **Add Home**.
9.  Enter details of the property you want to insure and click **Save**.
    
    All the fields and selections on this form correspond to attributes on the Home insured item spec in the product model.
    
10.  The Home appears as a child of the Homeowners insurance product. Click the **Homeowners (HO3)** bar to open all the coverages for this property. You can change attribute values on required coverages, and select any available optional coverages by clicking **Add**.
11.  After you've configured coverages for the vehicle, you can click **Rate Now**.
     
     Vlocity uses the rating procedure defined for Homeowners (HO3) and returns a Total premium with any applicable taxes and fees. It also includes the prices for each coverage.
     
12.  Next, add Scheduled Items to the home. These are specific types of valuables, such as Art and Jewelry. Click the carat under the home and choose **Create New**.
13.  The Add Scheduled Item form comes standard with the Vlocity Insurance Lightning Web Components.
     
     Fill out the form and click **Save**.
     
14.  Scheduled Items are added as children of the Home, and grandchildren of the Homewonwers insurance product.
     
     Click **Rate Now** after you've added all the scheduled items to the property. The rating procedure returns prices with the driver information included.
     
15.  The total premium is displayed for the quote. To email quote documents to the prospective customer, click **Quote Doc** on the Actions panel.
     
     Though the UI doesn't send a message, after you've clicked the button and the UI returns to this page, the email with the quote details has been sent to the email address that's listed in the opportunity we built this quote on.
     

Did this article solve your issue?

Let us know so we can improve!

YesNo