---
title: "Add a Deep Clone in Batch Button to the Page Layout"
source: "https://help.salesforce.com/s/articleView?id=ind.insurance_add_a_deep_clone_in_batch_button_to_the_page_layout_608685.htm&language=en_US&type=5"
scraped: "2026-04-13"
filter: "ind.insurance_"
---# Add a Deep Clone in Batch Button to the Page Layout

Add a Deep Clone in Batch Button to the Page Layout[](https://help.salesforce.com/s?language=en_US)

You are here:

1.  [Salesforce Help](/s/?language=en_US)
2.  [Docs](/s/products?language=en_US)
3.  [Digital Insurance](https://help.salesforce.com/s/articleView?id=ind.insurance_admin_standard.htm&language=en_US&type=5)

# Add a Deep Clone in Batch Button to the Page Layout

If you have large products (dozens or hundreds of attributes, dozens or hundreds of coverages), you can add a **Deep Clone in Batch** button to your product layout. This button is configured to clone large products by initiating a batch job. This avoids timeout errors.

1.  Go to **Setup > Object Manager.**
2.  Find the **Product** object.
3.  Click **Page Layouts**.
4.  Click the name of the Product Layout you use (probably Vlocity 108).
5.  Under Salesforce Mobile and Lightning Experience Actions, click **override the global publisher layout**.
6.  In the top right pane, click **Mobile & Lightning Actions**.
7.  Drag the **Deep Clone in Batch** button down into the Salesforce Mobile and Lightning Experience Actions area.
8.  Click **Save**.

Did this article solve your issue?

Let us know so we can improve!

YesNo