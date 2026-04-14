---
title: "Make Changes to Inherited Parts of the Root Product Spec"
source: "https://help.salesforce.com/s/articleView?id=ind.insurance_make_changes_to_inherited_parts_of_the_root_product_spec_606371.htm&language=en_US&type=5"
scraped: "2026-04-14"
filter: "ind.insurance_"
---# Make Changes to Inherited Parts of the Root Product Spec

Make Changes to Inherited Parts of the Root Product Spec[](https://help.salesforce.com/s?language=en_US)

You are here:

1.  [Salesforce Help](/s/?language=en_US)
2.  [Docs](/s/products?language=en_US)
3.  [Digital Insurance](https://help.salesforce.com/s/articleView?id=ind.insurance_admin_standard.htm&language=en_US&type=5)

# Make Changes to Inherited Parts of the Root Product Spec

After you create a product class-based root product spec, you can make some changes to the parts that are inherited from the product class. But some inherited things can't be changed on the root product spec.

Here's what you can do and change on the root product spec:

-   Coverage attributes can be modified as follows:
    
    -   Add attribute value rules to any listed attribute values
        
    -   Change the default attribute value in a preconfigured list of values
        
    -   Change the Read Only and Rating status on a coverage attribute
        
    -   Change the Rating Input/Output Mapping and Rating Attributes Use on a coverage attribute
        
-   Add additional coverages
    
-   Add additional insured items and insured parties
    
-   Modify insured item and insured party attributes
    
-   Add rules to insured item attributes and insured party attributes
    
-   Add additional rating facts
    
-   Modified rating fact attributes
    
-   Add new product-level attributes
    
-   Modify product-level attributes
    
-   Add additional underwriting rules
    

Here's what you can't do or change on the root product spec:

-   Inherited coverages can't be deleted
    
-   Inherited coverages can't have their Optional status, Parent Insured Item, or optional coverage rules modified
    
-   Attributes on coverages can't have their Value Data Type or Is Configurable checkbox modified
    
-   You can't add attribute values to a list of available attribute values on a coverage
    
-   Modify inherited eligibility rules
    
-   Modify inherited underwriting rules
    

Did this article solve your issue?

Let us know so we can improve!

YesNo