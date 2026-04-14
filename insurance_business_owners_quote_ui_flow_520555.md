---
title: "Business Owners Quote UI Flow"
source: "https://help.salesforce.com/s/articleView?id=ind.insurance_business_owners_quote_ui_flow_520555.htm&language=en_US&type=5"
scraped: "2026-04-14"
filter: "ind.insurance_"
---# Business Owners Quote UI Flow

Business Owners Quote UI Flow[](https://help.salesforce.com/s?language=en_US)

You are here:

1.  [Salesforce Help](/s/?language=en_US)
2.  [Docs](/s/products?language=en_US)
3.  [Digital Insurance](https://help.salesforce.com/s/articleView?id=ind.insurance_admin_standard.htm&language=en_US&type=5)

# Business Owners Quote UI Flow

You can create and modify quotes directly on the Quote UI (also called the Lex Console), which is built with Lightning Web Components.

1.  To create a new quote, we don't start on the Quote page. Instead, we go to the Opportunities page and choose the Opportunity we're creating the quote for.
    
    [](https://help.salesforce.com/s?language=en_US)Important
    
    Before you create a quote on an Opportunity, go to the Details tab and make sure that the Opportunity has a pricebook assigned.
    
2.  On the right pane of the **Opportunities** page, in the **Quotes** panel, click the carat and choose **New Quote**.
3.  On the **New Quote: Quote** window, choose **Quote**.
4.  On the **New Quote: Quote** window, enter a name for this quote, then click **Save**.
    
    Do _not_ enter any other information here. Any info you enter here will mess up your quote as you create it on the Vlocity Quote UI.
    
5.  Now navigate to the Quote page. On the Quote list view, choose the quote you just created.
    
    On the **Coverages** tab of the quote, click **Add Product** to start building the structure of your quote based on a product model.
    
6.  For this example, we choose the Superior Business product. Click **Add**.
7.  The Superior Business product appears on the **Coverages** tab. The premium **Total** is $0 and colored red because it hasn't been rated yet. But we're not rating this quote yet. First we need to add an insured item.
8.  Click **Add smallBusiness**.
    
    All the fields and selections on this form correspond to attributes on the smallBusiness insured item spec in the product model.
    
9.  Fill out the form and click **Next**.
    
    The smallBusiness appears as a child of the Business Owners insurance product.
    
10.  Click the **Show Coverages** bar to open all the coverages for this property. You can change attribute values on required coverages, and select any available optional coverages by clicking **Add**.
11.  After configuring coverages, click **Rate Now**.
     
     The workflow uses the rating procedure defined for Business Owners Policy and returns a Total premium with any applicable taxes and fees. It also includes the prices for each coverage.
     
12.  Finally, quote documents can be emailed to the prospective customer. Click **Quote Doc** on the **Actions** panel.
     
     After you've clicked the button you won't see the message being sent but rest assured that is! The email with the quote details is sent to the email address listed in the opportunity for this quote.
     

Did this article solve your issue?

Let us know so we can improve!

YesNo