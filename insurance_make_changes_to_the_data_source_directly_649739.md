---
title: "Make Changes to the Data Source Directly"
source: "https://help.salesforce.com/s/articleView?id=ind.insurance_make_changes_to_the_data_source_directly_649739.htm&language=en_US&type=5"
scraped: "2026-04-14"
filter: "ind.insurance_"
---# Make Changes to the Data Source Directly

Make Changes to the Data Source Directly[](https://help.salesforce.com/s?language=en_US)

You are here:

1.  [Salesforce Help](/s/?language=en_US)
2.  [Docs](/s/products?language=en_US)
3.  [Digital Insurance](https://help.salesforce.com/s/articleView?id=ind.insurance_admin_standard.htm&language=en_US&type=5)

# Make Changes to the Data Source Directly

If the data source for a component is an Omnistudio Data Mapper or an Integration Procedure, you can make changes to the Data Mapper or Integration Procedure directly to get the data you want flowing into your site.

1.  If you need to, find the name of the data source in the FlexCard Data Source section (on the **Setup** tab in the right pane).
2.  Open the Data Mapper or Integration Procedure.
3.  Make your changes and save them.
4.  If you changed the output of the Data Source, make any corresponding changes in the FlexCard conditions, fields, or actions.
    
    For example, the **Price** field in a card named Open Claims expects a `TotalPaid` field. You change the Data Mapper used as the data source for this card to output `TotalAmount`. So you need to change the **Price** field to expect `TotalAmount`, so that the price appears.
    
5.  (Optional) If you want to see the new data reflected in the Designer and preview of the FlexCard, go to the **Setup** tab on the FlexCard and click **Save & Fetch**.

Did this article solve your issue?

Let us know so we can improve!

YesNo