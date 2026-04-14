---
title: "Create a Root Product Spec from Scratch"
source: "https://help.salesforce.com/s/articleView?id=ind.insurance_create_a_root_product_spec_from_scratch_605766.htm&language=en_US&type=5"
scraped: "2026-04-14"
filter: "ind.insurance_"
---# Create a Root Product Spec from Scratch

Create a Root Product Spec from Scratch[](https://help.salesforce.com/s?language=en_US)

You are here:

1.  [Salesforce Help](/s/?language=en_US)
2.  [Docs](/s/products?language=en_US)
3.  [Digital Insurance](https://help.salesforce.com/s/articleView?id=ind.insurance_admin_standard.htm&language=en_US&type=5)

# Create a Root Product Spec from Scratch

When you create a root product spec from scratch, you start with a blank slate instead of creating a product model based on a product class or cloning an existing root product spec.

-   [Create the Root Product Spec and Add Details](https://help.salesforce.com/s/articleView?id=ind.insurance_create_the_root_product_spec_and_add_details_605811.htm&language=en_US&type=5 "Create a new root product spec and add details to it.")
    
    [](https://help.salesforce.com/s?language=en_US)Create a new root product spec and add details to it.
    
-   [Add Child Specs to a Root Product](https://help.salesforce.com/s/articleView?id=ind.insurance_add_child_specs_to_a_root_product_605904.htm&language=en_US&type=5 "After you create a root product spec, you can add child specs to it. Child specs include Coverages, Insured Items, Insured Parties, and Rating Facts.")
    
    [](https://help.salesforce.com/s?language=en_US)After you create a root product spec, you can add child specs to it. Child specs include Coverages, Insured Items, Insured Parties, and Rating Facts.
    
-   [Configure Coverages](https://help.salesforce.com/s/articleView?id=ind.insurance_configure_coverages_605925.htm&language=en_US&type=5 "After you add coverages to a root product spec, you can configure them as child coverages, modify their attributes, make them optional, add rules to optional coverages, and re-order them in the UI.")
    
    [](https://help.salesforce.com/s?language=en_US)After you add coverages to a root product spec, you can configure them as child coverages, modify their attributes, make them optional, add rules to optional coverages, and re-order them in the UI.
    
-   [Add Eligibility and Underwriting Rules](https://help.salesforce.com/s/articleView?id=ind.insurance_add_eligibility_and_underwriting_rules_606093.htm&language=en_US&type=5 "Vlocity Insurance uses eligibility rules to filter a root product in or out of quotes at runtime. Underwriting (workflow) rules determine when a runtime quote for a root product can be automatically issued as a policy, when it must be sent to underwriting, and when a policy issue is automatically declined.")
    
    [](https://help.salesforce.com/s?language=en_US)Vlocity Insurance uses eligibility rules to filter a root product in or out of quotes at runtime. Underwriting (workflow) rules determine when a runtime quote for a root product can be automatically issued as a policy, when it must be sent to underwriting, and when a policy issue is automatically declined.
    
-   [Add Attributes Directly to a Root Product Spec](https://help.salesforce.com/s/articleView?id=ind.insurance_add_attributes_directly_to_a_root_product_spec_606113.htm&language=en_US&type=5 "You can add and configure attributes that apply to the whole root product spec, as opposed to attributes that apply to child specs.")
    
    [](https://help.salesforce.com/s?language=en_US)You can add and configure attributes that apply to the whole root product spec, as opposed to attributes that apply to child specs.
    
-   [Add Taxes and Fees to the Root Product Spec](https://help.salesforce.com/s/articleView?id=ind.insurance_add_taxes_and_fees_to_the_root_product_spec_606124.htm&language=en_US&type=5 "To apply taxes and fees to insurance product premiums, you can attach them to root products.")
    
    [](https://help.salesforce.com/s?language=en_US)To apply taxes and fees to insurance product premiums, you can attach them to root products.
    
-   [Map Provider Networks to Coverage Specs](https://help.salesforce.com/s/articleView?id=ind.insurance_configure_networks_on_a_root_plan_spec.htm&language=en_US&type=5 "You can add existing provider networks to root plan (product) specs. Based on how you've configured the coverage specs on the root plan spec, you can map each provider network to specific coverage specs.")
    
    [](https://help.salesforce.com/s?language=en_US)You can add existing provider networks to root plan (product) specs. Based on how you configure the coverage specs on the root plan spec, you can map each provider network to specific coverage specs.
    
-   [Add a Price Book Entry](https://help.salesforce.com/s/articleView?id=ind.insurance_add_a_price_book_entry_606216.htm&language=en_US&type=5 "After you create a product, add it to a price book.")
    
    [](https://help.salesforce.com/s?language=en_US)After you create a product, add it to a price book.
    
-   [Set Up the Product Rating Simulator](https://help.salesforce.com/s/articleView?id=ind.insurance_set_up_the_product_rating_simulator_606240.htm&language=en_US&type=5 "To set up a product rating simulator, complete an analysis, set up a rating procedure, and then map the rating procedure to the product model.")
    
    [](https://help.salesforce.com/s?language=en_US)To set up a product rating simulator, complete an analysis, set up a rating procedure, and then map the rating procedure to the product model.
    

-   **[Create the Root Product Spec and Add Details](https://help.salesforce.com/s/articleView?id=ind.insurance_create_the_root_product_spec_and_add_details_605811.htm&language=en_US&type=5)**  
    Create a new root product spec and add details to it.
-   **[Add Child Specs to a Root Product](https://help.salesforce.com/s/articleView?id=ind.insurance_add_child_specs_to_a_root_product_605904.htm&language=en_US&type=5)**  
    After you create a root product spec, you can add child specs to it. Child specs include Coverages, Insured Items, Insured Parties, and Rating Facts.
-   **[Configure Coverages](https://help.salesforce.com/s/articleView?id=ind.insurance_configure_coverages_605925.htm&language=en_US&type=5)**  
    After you add coverages to a root product spec, you can configure them as child coverages, modify their attributes, make them optional, add rules to optional coverages, and re-order them in the UI.
-   **[Modify Attributes on Insured Items and Insured Parties](https://help.salesforce.com/s/articleView?id=ind.insurance_modify_attributes_on_insured_items_and_insured_parties_606050.htm&language=en_US&type=5)**  
    You can change the configuration of any attribute in an insured item or insured party on a root product spec. Your changes to an insured item or party on a root product override the inherited configuration from the insured item spec.
-   **[Modify Attributes on Rating Facts](https://help.salesforce.com/s/articleView?id=ind.insurance_modify_attributes_on_rating_facts_606076.htm&language=en_US&type=5)**  
    You can make some changes to attributes in rating facts on a root product spec.
-   **[Add Eligibility and Underwriting Rules](https://help.salesforce.com/s/articleView?id=ind.insurance_add_eligibility_and_underwriting_rules_606093.htm&language=en_US&type=5)**  
    Vlocity Insurance uses eligibility rules to filter a root product in or out of quotes at runtime. Underwriting (workflow) rules determine when a runtime quote for a root product can be automatically issued as a policy, when it must be sent to underwriting, and when a policy issue is automatically declined.
-   **[Add Attributes Directly to a Root Product Spec](https://help.salesforce.com/s/articleView?id=ind.insurance_add_attributes_directly_to_a_root_product_spec_606113.htm&language=en_US&type=5)**  
    You can add and configure attributes that apply to the whole root product spec, as opposed to attributes that apply to child specs.
-   **[Add Taxes and Fees to the Root Product Spec](https://help.salesforce.com/s/articleView?id=ind.insurance_add_taxes_and_fees_to_the_root_product_spec_606124.htm&language=en_US&type=5)**  
    To apply taxes and fees to insurance product premiums, you can attach them to root products.
-   **[Configure Networks on a Root Plan Spec](https://help.salesforce.com/s/articleView?id=ind.insurance_configure_networks_on_a_root_plan_spec.htm&language=en_US&type=5)**  
    You can add existing provider networks to root plan (product) specs. Based on how you've configured the coverage specs on the root plan spec, you can map each provider network to specific coverage specs.
-   **[Add a Price Book Entry](https://help.salesforce.com/s/articleView?id=ind.insurance_add_a_price_book_entry_606216.htm&language=en_US&type=5)**  
    After you create a product, add it to a price book.
-   **[Set Up the Product Rating Simulator](https://help.salesforce.com/s/articleView?id=ind.insurance_set_up_the_product_rating_simulator_606240.htm&language=en_US&type=5)**  
    To set up a product rating simulator, complete an analysis, set up a rating procedure, and then map the rating procedure to the product model.

Did this article solve your issue?

Let us know so we can improve!

YesNo