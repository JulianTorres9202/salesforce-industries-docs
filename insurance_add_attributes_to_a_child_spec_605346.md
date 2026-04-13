---
title: "Add Attributes to a Child Spec"
source: "https://help.salesforce.com/s/articleView?id=ind.insurance_add_attributes_to_a_child_spec_605346.htm&language=en_US&type=5"
scraped: "2026-04-13"
filter: "ind.insurance_"
---# Add Attributes to a Child Spec

Add Attributes to a Child Spec[](https://help.salesforce.com/s?language=en_US)

You are here:

1.  [Salesforce Help](/s/?language=en_US)
2.  [Docs](/s/products?language=en_US)
3.  [Digital Insurance](https://help.salesforce.com/s/articleView?id=ind.insurance_admin_standard.htm&language=en_US&type=5)

# Add Attributes to a Child Spec

Most child specs include at least one attribute. When you add attributes to a child spec, you also configure them with controls and values.

1.  On the **Attributes** tab, click **New**.
2.  Choose the attribute category your attribute is in.
3.  Choose the attribute.
4.  (Optional) Edit the **Attribute Name**. This description isn't picked up by the services, added to any JSONs, or shown to users.
5.  (Optional) Change the **Name** if you want it to display differently in the UI for this child spec.
    
    As a best practice, use a unique, descriptive Name value for each power attribute, especially if multiple power attributes can apply to the same Claim, Claim Coverage, or Policy. For example, use names like “Collision Deductible” and “Comprehensive Deductible” instead of something generic like “Deductible.” The more descriptive names improve usability for users reviewing a claim with both deductibles, and they help ensure accurate information in the Policy Terms Standing panel.
    
6.  Configure the attribute.
    
    | 
    Field
    
     | 
    
    Description
    
     |
    | --- | --- |
    | 
    
    Is Hidden
    
     | 
    
    Select this option to hide this attribute from users.
    
    Hidden attributes aren't shown to customers at all but may be included in rating.
    
     |
    | 
    
    Is Configurable
    
     | 
    
    Leave this cleared to define this attribute with a blank value or a preset value that users can't change. See [Add a Fixed Value to an Attribute on a Child Spec](https://help.salesforce.com/s/articleView?id=ind.insurance_add_a_fixed_value_to_an_attribute_on_a_child_spec_605402.htm&language=en_US&type=5 "A fixed attribute value is a blank value or a preset value that users can't change.").
    
    Select this option to give users the flexibility to enter or select a value for this attribute. See [Add a Configurable Value to an Attribute on a Child Spec](https://help.salesforce.com/s/articleView?id=ind.insurance_add_a_configurable_value_to_an_attribute_on_a_child_spec_605442.htm&language=en_US&type=5 "A configurable attribute value gives users the flexibility to enter or select a value.").
    
     |
    | 
    
    Rating
    
     | 
    
    Select this option to have Vlocity use this attribute's value to rate the product this child spec is attached to. Follow the instructions in [Mapping Ratings to Product Specs](https://help.salesforce.com/s/articleView?id=ind.insurance_mapping_ratings_to_product_spec_610341.htm&language=en_US&type=5 "After you configure rating procedures, map ratings to your product specs. Complete this task for all your product specs, including insured item specs, insured party specs, and root product specs. OmniScripts and other components use services that read the mappings and formulas, and then return premium prices to your users.") to map your rating information correctly.
    
     |
    | 
    
    Tax and Fee Rating Attribute
    
     | 
    
    Select this option to use this attribute's value to rate a tax or fee for either this child spec or for the root product this child spec is attached to.
    
     |
    | Required | 
    
    Select this option to make the attribute required for the claim involved injury and claim damaged property specs.
    
    This configuration on the claim product model is enforced at runtime when claim item records are displayed on the participant card claim item page.
    
    To use this field, make sure you have the latest Insurance Product Model Cards DataPack. In the Vlocity Installation Assistant, within the Install Vlocity Cards DataPacks (Vlocity Installation and Upgrade) steps, complete the Install Insurance Product Model Cards DataPack (Vlocity Installation and Upgrade) step.
    
    Note This field is available only for ClaimPropertySpec and ClaimInjurySpec product record types.
    
    
    
    
    
     |
    

-   **[Add a Fixed Value to an Attribute on a Child Spec](https://help.salesforce.com/s/articleView?id=ind.insurance_add_a_fixed_value_to_an_attribute_on_a_child_spec_605402.htm&language=en_US&type=5)**  
    A fixed attribute value is a blank value or a preset value that users can't change.
-   **[Add a Configurable Value to an Attribute on a Child Spec](https://help.salesforce.com/s/articleView?id=ind.insurance_add_a_configurable_value_to_an_attribute_on_a_child_spec_605442.htm&language=en_US&type=5)**  
    A configurable attribute value gives users the flexibility to enter or select a value.

Did this article solve your issue?

Let us know so we can improve!

YesNo