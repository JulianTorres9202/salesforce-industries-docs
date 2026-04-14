---
title: "Map Rating Inputs to Attributes"
source: "https://help.salesforce.com/s/articleView?id=ind.insurance_map_rating_inputs_to_attributes_610435.htm&language=en_US&type=5"
scraped: "2026-04-14"
filter: "ind.insurance_"
---# Map Rating Inputs to Attributes

Map Rating Inputs to Attributes[](https://help.salesforce.com/s?language=en_US)

You are here:

1.  [Salesforce Help](/s/?language=en_US)
2.  [Docs](/s/products?language=en_US)
3.  [Digital Insurance](https://help.salesforce.com/s/articleView?id=ind.insurance_admin_standard.htm&language=en_US&type=5)

# Map Rating Inputs to Attributes

Map each input required by your rating procedure must be mapped to an attribute in the product to be rated.

[](https://help.salesforce.com/s?language=en_US)Tip

Map inputs to attributes associated with child specs first. Then associate those child specs with a root product spec. This lets all root products that use some of the same coverages, insured items, and insured parties use the same mapped rating inputs.

1.  On the Product list page, find and open the child spec detail page you want to map ratings inputs to. Your child spec can be a coverage spec, insured item spec, or insured party spec.
2.  Select an attribute to map.
3.  In the right panel, select **Rating**.
4.  Under **Rating Type**, select Input.
5.  Under **Rating Input**, enter the variable name from the rating procedure that maps to this attribute.
6.  Click **Update** at the top of the right panel.
    
    Repeat these steps to map each input variable to an attribute you need to be rated on each coverage spec, insured item spec, and insured party spec.
    

[](https://help.salesforce.com/s?language=en_US)

After you map the rating input, verify the mapping. If necessary, change rating inputs mappings.

-   **[Verify Rating Input Mappings](https://help.salesforce.com/s/articleView?id=ind.insurance_verify_rating_input_mappings_610470.htm&language=en_US&type=5)**  
    After you map rating inputs to attributes, make sure input variables look right on the product spec.
-   **[Change Rating Inputs Mappings](https://help.salesforce.com/s/articleView?id=ind.insurance_change_rating_inputs_mappings_610491.htm&language=en_US&type=5)**  
    Change the way rating inputs are mapped to attributes as needed.

Did this article solve your issue?

Let us know so we can improve!

YesNo