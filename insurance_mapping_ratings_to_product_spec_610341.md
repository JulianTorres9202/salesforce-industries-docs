---
title: "Map Ratings to Product Specs"
source: "https://help.salesforce.com/s/articleView?id=ind.insurance_mapping_ratings_to_product_spec_610341.htm&language=en_US&type=5"
scraped: "2026-04-14"
filter: "ind.insurance_"
---# Map Ratings to Product Specs

Map Ratings to Product Specs[](https://help.salesforce.com/s?language=en_US)

You are here:

1.  [Salesforce Help](/s/?language=en_US)
2.  [Docs](/s/products?language=en_US)
3.  [Digital Insurance](https://help.salesforce.com/s/articleView?id=ind.insurance_admin_standard.htm&language=en_US&type=5)

# Map Ratings to Product Specs

After you configure rating procedures, map ratings to your product specs. Complete this task for all your product specs, including insured item specs, insured party specs, and root product specs. OmniScripts and other components use services that read the mappings and formulas, and then return premium prices to your users.

Before you get started, make sure these items are configured and ready to use:

-   Rating procedure
    
    -   Lookup tables
        
    -   Expression sets
        
        Keep the input variable names and output variable names used in expression sets handy. You map these names to attributes later.
        
-   Integration procedures (if used for rating)
    
-   Coverage specs with attributes
    
-   Insured item specs with attributes
    
-   Insured party specs with attributes
    
-   Root product specs with attributes
    

Note

If you have Integration Procedures from earlier releases, you can use calculation matrices and calculation procedures instead of lookup tables and expression sets.

-   **[Specify Rating Procedure on Root Product Specs](https://help.salesforce.com/s/articleView?id=ind.insurance_specify_rating_procedure_on_root_product_specs_610402.htm&language=en_US&type=5)**  
    To get the correct pricing for each insurance product, assign a rating procedure to each root product spec.
-   **[Specify Rating Procedure on Child Product Specs](https://help.salesforce.com/s/articleView?id=ind.insurance_specify_rating_procedure_on_child_product_specs.htm&language=en_US&type=5)**  
    To use unique pricing for insured items and insured parties within a root product's hierarchy, assign a rating procedure to a child product spec.
-   **[Map Rating Inputs to Attributes](https://help.salesforce.com/s/articleView?id=ind.insurance_map_rating_inputs_to_attributes_610435.htm&language=en_US&type=5)**  
    Map each input required by your rating procedure must be mapped to an attribute in the product to be rated.
-   **[Map Rating Outputs on Product Simulator](https://help.salesforce.com/s/articleView?id=ind.insurance_map_rating_outputs_on_product_simulator_610512.htm&language=en_US&type=5)**  
    The best place to map your rating output variables is on the Simulate tab on the root product page. You can see each of the coverages in a list under Rating Outputs in the Simulate tab.
-   **[Set Instance and Root Product Premium Formulas on Simulator](https://help.salesforce.com/s/articleView?id=ind.insurance_set_instance_and_root_product_premium_formulas_on_simulator_610533.htm&language=en_US&type=5)**  
    Make sure your insurance product premiums take optional coverages into account by using rating procedures for coverages in combination with formulas on the root product Simulate tab.

Did this article solve your issue?

Let us know so we can improve!

YesNo