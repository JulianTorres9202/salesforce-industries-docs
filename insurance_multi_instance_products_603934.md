---
title: "Multi-Instance Products"
source: "https://help.salesforce.com/s/articleView?id=ind.insurance_multi_instance_products_603934.htm&language=en_US&type=5"
scraped: "2026-04-14"
filter: "ind.insurance_"
---# Multi-Instance Products

Multi-Instance Products[](https://help.salesforce.com/s?language=en_US)

You are here:

1.  [Salesforce Help](/s/?language=en_US)
2.  [Docs](/s/products?language=en_US)
3.  [Digital Insurance](https://help.salesforce.com/s/articleView?id=ind.insurance_admin_standard.htm&language=en_US&type=5)

# Multi-Instance Products

A multi-instance insurance product model describes an insurance product that can have more than one instance of its insured items (or insured parties). Each insured item (or insured party) can also have its own set of coverage selections and attribute values.

For example, an auto insurance product model has Vehicle as an insured item spec and Driver as an insured party spec. At runtime, a quote or a policy can have multiple instances of both insured party and insured item--that is, multiple vehicles and multiple drivers.

[](https://help.salesforce.com/s?language=en_US)Multi-instance single root insurance products can include multiple instances of one insured item per quote and per policy. An example of a multi-instance insurance product is a homeowner's product with child coverages associated to the Home insured item.

[](https://help.salesforce.com/s?language=en_US)In a simple multi-instance product model, you associate an insured item spec or insured party spec to the root product spec.

[](https://help.salesforce.com/s?language=en_US)You can then associate coverage specs to the root product spec and the insured item or insured product spec.

[](https://help.salesforce.com/s?language=en_US)In this example homeowners insurance product, the coverages are all attached directly to the root product spec:

[](https://help.salesforce.com/s?language=en_US)To change that, you can associate a **Parent Insured Item** in the dropdown.

[](https://help.salesforce.com/s?language=en_US)

## Multi-Instance with Grandchild Insured Items

Multi-instance products with grandchildren have a hierarchical structure that can work in several ways:

-   Root Product
    
    -   Coverages
        
    -   Insured Item
        
        -   Insured Item
            
-   Root Product
    
    -   Insured Item
        
        -   Coverages
            
        -   Insured Item
            
-   Root Product
    
    -   Coverages
        
    -   Insured Item
        
        -   Coverages
            
        -   Insured Item
            
-   Root Product
    
    -   Insured Item
        
        -   Insured Item
            
    -   Insured Item
        
    -   Insured Item
        
    -   ...(more insured items at the same level)
        
-   Root Product
    
    -   Coverages
        
    -   Insured Item
        
        -   Coverages
            
        -   Insured Item
            
    -   Insured Item
        

You can substitute insured parties for insured items in any of these structures, but Vlocity treats the data for insured parties a bit differently. We'll look at grandchild insured parties in the next section.

Here's an example of a multi-instance with grandchildren structure:

Here's how the insured item and grandchild insured item are set up on the root product spec:

When a multi-instance product gets quoted and sold as policy, the structure of the root product and insured items looks like this:

[](https://help.salesforce.com/s?language=en_US)

## Multi-Instance with Grandchild Insured Parties

Vlocity handles grandchild insured parties (people) differently than it handles grandchild insured items.

The way the insured item spec and grandchild insured party spec are set up is the same as for a grandchild insured item spec.

Here's what a multi-instance with insured item and grandchild insured party structure can look like when it is quoted and sold as a policy:

So what's different about a multi-instance product model with a grandchild insured party? It's the way the insured party data is stored once a policy is created.

In policy data, insured parties get stored as Held Party Relationships. This lets Vlocity store the insured party data only once while maintaining a multiple instance structure.

[](https://help.salesforce.com/s?language=en_US)

## Instance Model Guardrails

Keep these things in mind when you plan products:

-   We do support associating coverages to a root product and to a single first-level insured item on the same root product.
    
-   We don't support associating coverages to more than one insured item or insured party in a product model.
    

Did this article solve your issue?

Let us know so we can improve!

YesNo