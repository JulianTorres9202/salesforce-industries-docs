---
title: "Configure Rating Engine for Property using Expression Sets"
source: "https://help.salesforce.com/s/articleView?id=ind.insurance_configure_rating_engine_for_property_using_expression_sets.htm&language=en_US&type=5"
scraped: "2026-04-14"
filter: "ind.insurance_"
---# Configure Rating Engine for Property using Expression Sets

Configure Rating Engine for Property using Expression Sets[](https://help.salesforce.com/s?language=en_US)

You are here:

1.  [Salesforce Help](/s/?language=en_US)
2.  [Docs](/s/products?language=en_US)
3.  [Digital Insurance](https://help.salesforce.com/s/articleView?id=ind.insurance_admin_standard.htm&language=en_US&type=5)

# Configure Rating Engine for Property using Expression Sets

The rating engine for Homeowners (HO3) and Renters (HO4) products is reconfigured to work with expression sets and decision matrices.

Note From Summer '22 onwards, the homeowners and renters products will use Business Rule Engine components for rating premiums. The existing customers can still use calculation procedures and decision matrices as rating engine.

**Where:** Available in Summer '22 and later releases

**Who:** This feature is available to users who have Property and Casualty Application.

**How:** The homeowners rating procedure for Property and Casualty Application is built using the PropertyRating Integration Procedure. You can find this OmniScript in OmniStudio Integration Procedures under:

-   Type: insRating
    
-   Subtype: propertyOwner
    
-   Name: PropertyRating
    

Renters rating procedure for Property and Casualty Application is built using the PropertyRentersRating Integration Procedure. You can find this OmniScript in OmniStudio Integration Procedures under:

-   Type: insRating
    
-   Subtype: propertyRenter
    
-   Name: PropertyRentersRating
    

Did this article solve your issue?

Let us know so we can improve!

YesNo