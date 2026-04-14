---
title: "Quote Business Process For Group Voluntary Benefits"
source: "https://help.salesforce.com/s/articleView?id=ind.insurance_quote_business_process_for_gbv.htm&language=en_US&type=5"
scraped: "2026-04-14"
filter: "ind.insurance_"
---# Quote Business Process For Group Voluntary Benefits

Quote Business Process For Group Voluntary Benefits[](https://help.salesforce.com/s?language=en_US)

You are here:

1.  [Salesforce Help](/s/?language=en_US)
2.  [Docs](/s/products?language=en_US)
3.  [Digital Insurance](https://help.salesforce.com/s/articleView?id=ind.insurance_admin_standard.htm&language=en_US&type=5)

# Quote Business Process For Group Voluntary Benefits

Quickly and efficiently configure, reprice, and view a quote for group plans.

1.  Create an opportunity for a group account. Fill the required fields and select Standard Price Book in the Price Book field.
    
    Note Create the required group class records applicable for your group account. This is required only if you want to rate a product only for a specific group class or classes.
    
2.  From the Related tab on the opportunity, create a new quote. Select L**Large Group Quote****arge Group Quote**, and then enter an effective date for the quote.
3.  On the new quote record, click **Add Plan** on the Configure Plan tab.
4.  Select plans on the Add Product window, and then click **Add**.
    
    Once the plans are added to the quote, the line items show a red $0.00 premium price to indicate that the plans must be rated.
    
    Tip You can add up to three plans at a time. Add additional plans in batches of threes by using the **Add Plan** **Add Plan** button.
    
5.  On the Census tab, click **Upload CSV File**.
6.  Select **Upload new census** on the Upload Census window.
7.  Select a census CSV file.
8.  On the Map Fields screen, map the fields in the uploaded CSV file to the corresponding Group Census Member fields.
9.  Save the uploaded file.
    
    The census is uploaded and shows census members in an expandable tree view.
    
10.  Edit member information or add a dependent by using the member dropdown menu.
11.  Rate a single plan by using the **Rate Now** button or rate all plans by using the **Rate All Plans** button.
     
     A bell notification lets you know when rating is complete.
     
12.  Click **Refresh** on the quote record to view the updated premium.
13.  Add optional coverages, and then re-rate the plans.
14.  When the quote is finalized, click **Accepted** in the state transition component, and then click **Mark as Complete**.

Did this article solve your issue?

Let us know so we can improve!

YesNo