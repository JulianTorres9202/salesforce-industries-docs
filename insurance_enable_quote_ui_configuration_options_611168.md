---
title: "Enable Quote UI Configuration Options"
source: "https://help.salesforce.com/s/articleView?id=ind.insurance_enable_quote_ui_configuration_options_611168.htm&language=en_US&type=5"
scraped: "2026-04-14"
filter: "ind.insurance_"
---# Enable Quote UI Configuration Options

Enable Quote UI Configuration Options[](https://help.salesforce.com/s?language=en_US)

You are here:

1.  [Salesforce Help](/s/?language=en_US)
2.  [Docs](/s/products?language=en_US)
3.  [Digital Insurance](https://help.salesforce.com/s/articleView?id=ind.insurance_admin_standard.htm&language=en_US&type=5)

# Enable Quote UI Configuration Options

You can choose several Quote UI configuration options based on your business needs.

1.  On a Quote, click the upper right gear menu and select **Edit Page**.
2.  On the Lightning App Builder for the Quote Record Page, click the **Quote LWC** tab.
3.  Click inside the tab to select the Vlocity Insurance Quote component.
4.  A panel opens on the right side of the page which contains configuration options:
    
    -   **Enable Debug Mode**: Makes the Rules Log for attributes visible.
        
    -   **Enable Async Price Quote**: Adds the queueable flag to the priceQuote call, which allows the service to complete the call in batches. This reduces time-out failures when a lot of pricing is needed and will require longer processing time.
        
    -   **Show Action**: Adds Action buttons to the Quote LWC. Examples of Actions buttons include **Create Version** and **Debug Mode**.
        
    -   **Enable Product Cloning**: Adds the ability to [clone root products](https://help.salesforce.com/s/articleView?id=ind.insurance_root_product_cloning_611399.htm&language=en_US&type=5 "You can clone root products on the Quote UI if the Enable Product Cloning option is selected.").
        
    -   **Edit Panel Mode**: Displays product details with a [side panel view](https://help.salesforce.com/s/articleView?id=ind.insurance_edit_panel_mode_611413.htm&language=en_US&type=5 "The Edit Panel Mode is designed for specific use cases where products are highly configurable and can have a large number of coverages and attributes.").
        
    -   **Enable Group Classes**: Adds the ability to add [group classes](https://help.salesforce.com/s/articleView?id=ind.insurance_group_classes_for_large_group_quotes_611436.htm&language=en_US&type=5 "Group classes describe a group of plan subscribers who'll all receive similar or the same benefits. You can add them to plans on large group quotes.") to products on the quote.
        
    -   **Is Multi-Root Product**: Enables the multi-root view which allows you to add more than one product to a quote.
        
    -   **Use Rating Fact**: Adds the ability to use Rating Facts in pricing calculation.
        
    -   **Enable Batch Mode**: Enables the Batch Mode if Rating Fact is used.
        
        Note
        
        You must select both the **Use Rating Fact** and **Enable Batch Mode** options to use Batch Mode.
        
    -   **Show Coverage Descriptions**: Displays a tooltip next to each coverage spec that has a description defined.
        
        Tip Add the Product Description field to the Product Details section in the Product object field set you use in your org.
        
    
5.  Select the options you want to enable.
6.  Click **Save**.

Did this article solve your issue?

Let us know so we can improve!

YesNo