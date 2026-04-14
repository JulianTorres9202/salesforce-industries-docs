---
title: "Create Child Specs"
source: "https://help.salesforce.com/s/articleView?id=ind.insurance_create_child_specs_605269.htm&language=en_US&type=5"
scraped: "2026-04-14"
filter: "ind.insurance_"
---# Create Child Specs

Create Child Specs[](https://help.salesforce.com/s?language=en_US)

You are here:

1.  [Salesforce Help](/s/?language=en_US)
2.  [Docs](/s/products?language=en_US)
3.  [Digital Insurance](https://help.salesforce.com/s/articleView?id=ind.insurance_admin_standard.htm&language=en_US&type=5)

# Create Child Specs

Child specs are key building blocks for your product models. They're components of the root product specs that Insurance rates, quotes, sells, and administers for your customers.

Before You Begin

Plan which root products to associate with each child spec. Also decide how each attribute on each spec is used by Insurance and by your users. This helps you plan which attributes comprise each child spec, and how to configure each attribute on each spec.

1.  Go to the Products page and click **New**.
2.  Select the type of child spec you're creating.
3.  Fill out the detail information as follows:
    
    -   **Product Name**: Required. Enter a descriptive name for this child spec.
        
    -   **Product Code**: Make this code short, descriptive, and unique so that other users can identify this child spec by reading this code.
        
        Tip
        
        A descriptive, easy-to-read, consistent product code naming convention will make it easier to identify your products.
        
    -   **Active**: Check Active if you want this spec to be available in Insurance to be added to root product specs.
        
    -   **Status**: If you use process flows, such as one in which all specs must be reviewed and approved before they're activated, set a status here.
        
        Note
        
        Selecting **Active** in the **Status** field does not make it available for use in Insurance. To make a child spec available, check the **Active** checkbox.
        
    -   **Product Family**: Choose a Product Family that this child spec will belong to.
        
        Leave this field blank if this spec doesn't fit into a Product Family or if you don't use product families.
        
        Most insurers that use this option (as well as the Line of Business, Type, and Sub Type options) have large product catalogs, and need Product Families to help them slice and dice their catalog to make it easier to find specific products.
        
        For example, the [InsProductService: getRatedProducts](https://help.salesforce.com/s/articleView?id=ind.insurance_insproductservice__getratedproducts.htm&language=en_US&type=5 "Use this service to get an array of one or more products, priced using rating procedures attached to those products. This service also includes extra features such as tax and fee calculations, filtering, and performance optimization.") can use Product Family (and Line of Business, Type, and Sub Type) values as filters.
        
    -   **Line of Business**: Choose a Line of Business that this child spec will belong to.
        
        Leave this field blank if this spec doesn't fit into a Line of Business or if you don't use this option.
        
    -   **Type**: Choose a Type that this child spec will belong to.
        
        Leave this field blank if this spec doesn't fit into a Type or if you don't use Types.
        
    -   **Sub Type**: Choose a Sub Type that this child spec will belong to.
        
        Leave this field blank if this spec doesn't fit into a Sub Type or if you don't use sub types.
        
    -   **Carrier**: Enter the name of the carrier within your organization that backs the type of policy that this child spec will be a part of.
        
        Leave this field blank if you don't have different carriers for different types of insurance.
        
    -   **Parent Class**: Enter a Parent Class if you plan to write eligibility rules against product classes.
        
    -   **Term**: Set the term for this child spec that its root product will use. Insurance uses the Term value in revenue scheduling for purchased policies.
        
    
4.  Click **Save**.

Did this article solve your issue?

Let us know so we can improve!

YesNo