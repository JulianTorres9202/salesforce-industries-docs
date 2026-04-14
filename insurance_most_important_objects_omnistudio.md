---
title: "The Most Important Objects"
source: "https://help.salesforce.com/s/articleView?id=ind.insurance_most_important_objects_omnistudio.htm&language=en_US&type=5"
scraped: "2026-04-14"
filter: "ind.insurance_"
---# The Most Important Objects

The Most Important Objects[](https://help.salesforce.com/s?language=en_US)

You are here:

1.  [Salesforce Help](/s/?language=en_US)
2.  [Docs](/s/products?language=en_US)
3.  [Digital Insurance](https://help.salesforce.com/s/articleView?id=ind.insurance_admin_standard.htm&language=en_US&type=5)

# The Most Important Objects

The Property & Casualty Application includes a broad range of Salesforce standard objects and custom objects.

For property and casualty insurance, the most important of these objects are:

-   Product
    
    This object is where admins create product models to rate and sell. All the child specs, child spec attribute configurations and rules, product-level attributes, workflow rules, surcharges, and product details are configured and stored.
    
-   Quote
    
    This object has a LWC-based UI that lets Insurance and Administration users generate and administrate quotes.
    
    The Quote object connects to sub-objects, such as Quote Line Item. To learn more about the Quote object, see [Vlocity Insurance Quote Object Model](https://help.salesforce.com/s/articleView?id=ind.insurance_vlocity_insurance_quoteobject_model_614266.htm&language=en_US&type=5 "We've extended the Salesforce quote data model to store Insurance-specific data in quotes. When Insurance quoting uses the functionality of both Insurance and Salesforce to store all the data associated with that quote.").
    
-   Policies
    
    The Policies object is actually the Salesforce standard Asset object that we've renamed. It contains policy record data.
    
-   Claim
    
    This object has an LWC-based UI that lets Vlocity Administrator, Vlocity Insurance, and Vlocity Adjuster Dashboard work with claims.
    
    This object stores all claim data. It includes subobjects such as Claim Line Items.
    

Did this article solve your issue?

Let us know so we can improve!

YesNo