---
title: "Attributes for Auto Products"
source: "https://help.salesforce.com/s/articleView?id=ind.insurance_attributes_for_auto_products_with_omnistudio.htm&language=en_US&type=5"
scraped: "2026-04-13"
filter: "ind.insurance_"
---# Attributes for Auto Products

Attributes for Auto Products[](https://help.salesforce.com/s?language=en_US)

You are here:

1.  [Salesforce Help](/s/?language=en_US)
2.  [Docs](/s/products?language=en_US)
3.  [Digital Insurance](https://help.salesforce.com/s/articleView?id=ind.insurance_admin_standard.htm&language=en_US&type=5)

# Attributes for Auto Products

All the attributes used in the Auto insurance product and the insured item spec, insured party spec, and coverage specs are defined in the Vlocity Attribute Designer. Attributes are arranged into Attribute Categories.

Want to see a complete list of the attributes used in the Multi Auto product model? Visit the [Auto Attribute Catalog](https://help.salesforce.com/s/articleView?id=ind.insurance_auto_attribute_catalog_omnistudio.htm&language=en_US&type=5 "In this catalog, all attributes used for the Auto line of business are listed by Attribute Category. Each Attribute Category has its own table, which includes attribute codes and the product specs the attributes are used by.").

In the Vlocity Attribute Designer, basic information is defined for all attributes, such as name and attribute code.

For specific limit and deductible attributes that we use to describe policy terms, more information is defined:

-   Attribute Class
    
-   Attribute Scope
    
-   Applicable Actions
    
-   Applicable Item
    
-   Value Type
    

Attributes that have these fields set are called power attributes. Power attributes defined for policy terms so that the claims system can track them.

To learn more about power attributes, including when to use them and how to set them up, see [](https://help.salesforce.com/s?language=en_US)[Policy Terms as Power Attributes](https://help.salesforce.com/s/articleView?id=ind.insurance_policy_terms_as_power_attributes_617749.htm&language=en_US&type=5 "Enforce policy terms such as limits and deductibles by using power attributes. The \"power\" in power attributes comes from the extra metadata that you can configure for them. Insurance uses this metadata to track attributes as policy terms, from the product model to the policy record, and then on to claims against the policy.").

The attribute's Value Data Type, available values, default selected value, rating status, and other specifics are configured on the insured item spec, insured party spec, coverage spec, or root product spec.

A common attribute configuration used in the Auto product is the split limit attribute. This attribute type is used when several policy terms need to be displayed and selected together by customers. But Vlocity needs to access and act on each attribute independently for rating, rules, and claims.

The Uninsured Motorist coverage contains a Limit attribute that's got a split limit.

To configure this split limit attribute, we selected Multiselect Picklist for the Value Data Type and created a Value Decoder to help Vlocity work with the split limit attribute values.

Did this article solve your issue?

Let us know so we can improve!

YesNo