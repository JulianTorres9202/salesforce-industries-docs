---
title: "Attribute Rules and Attribute Value Rules Structure for Batch Loading"
source: "https://help.salesforce.com/s/articleView?id=ind.insurance_attribute_rules_and_attribute_value_rules_structure_for_batch_loading_609161.htm&language=en_US&type=5"
scraped: "2026-04-13"
filter: "ind.insurance_"
---# Attribute Rules and Attribute Value Rules Structure for Batch Loading

Attribute Rules and Attribute Value Rules Structure for Batch Loading[](https://help.salesforce.com/s?language=en_US)

You are here:

1.  [Salesforce Help](/s/?language=en_US)
2.  [Docs](/s/products?language=en_US)
3.  [Digital Insurance](https://help.salesforce.com/s/articleView?id=ind.insurance_admin_standard.htm&language=en_US&type=5)

# Attribute Rules and Attribute Value Rules Structure for Batch Loading

If you have to add attribute rules or attribute value rules to hundreds or thousands of products, you can write scripts to batch load rules directly into the database.

One of the important things you must decide before you load attribute rules and attribute value rules is at what level you want to store the rules. You have two choices:

-   Product Child Item (PCI) level
    
    A PCI is a coverage, insured item, or insured party that is attached to a root product
    
-   Spec level
    
    A spec is a coverage spec, insured item spec, or insured party spec
    

Note

Attributes assigned directly to a root product are always stored at the product level.

This is what it looks like when an attribute rules is stored at the PCI level:

Attributes can be assigned at the root product PCI level by storing the PCI Id in the Object Id column of the Attribute Assignment table. To find the PCI Id, go to the Related tab on the root product page:

Alternately, attributes can be assigned at the spec level by storing the Product Id in the Object Id column of the Attribute Assignment table.

If you haven't yet associated specs to products, you can load rules to the attributes on the specs identified by the Product ID of the spec. When you add this spec to a root product, the rules come over with the spec.

If you've already created your root products and added coverages and insured items to them, we recommend that you add rules at the root product PCI level—the coverage attached to the product won't inherit any changes you make at the coverage spec level.

[](https://help.salesforce.com/s?language=en_US)

## Batch Loading

-   [Batch Load Attribute Rules](https://help.salesforce.com/s/articleView?id=ind.insurance_batch_load_attribute_rules_609199.htm&language=en_US&type=5 "You can write scripts to batch load attribute rules directly into the database.")
    
    You can write scripts to batch load attribute rules directly into the database.
    
-   [Batch Load Attribute Value Rules](https://help.salesforce.com/s/articleView?id=ind.insurance_batch_load_attribute_value_rules_609278.htm&language=en_US&type=5 "An attribute value rule is a rule you assign to one specific attribute value.")
    
    An attribute value rule is a rule you assign to one specific attribute value.
    

-   **[Batch Load Attribute Rules](https://help.salesforce.com/s/articleView?id=ind.insurance_batch_load_attribute_rules_609199.htm&language=en_US&type=5)**  
    You can write scripts to batch load attribute rules directly into the database.
-   **[Batch Load Attribute Value Rules](https://help.salesforce.com/s/articleView?id=ind.insurance_batch_load_attribute_value_rules_609278.htm&language=en_US&type=5)**  
    An attribute value rule is a rule you assign to one specific attribute value.

Did this article solve your issue?

Let us know so we can improve!

YesNo