---
title: "Insurance Quote Item Relationships Object"
source: "https://help.salesforce.com/s/articleView?id=ind.insurance_vlocity_insurance_quote_item_relationshipsobject_614611.htm&language=en_US&type=5"
scraped: "2026-04-14"
filter: "ind.insurance_"
---# Insurance Quote Item Relationships Object

Insurance Quote Item Relationships Object[](https://help.salesforce.com/s?language=en_US)

You are here:

1.  [Salesforce Help](/s/?language=en_US)
2.  [Docs](/s/products?language=en_US)
3.  [Digital Insurance](https://help.salesforce.com/s/articleView?id=ind.insurance_admin_standard.htm&language=en_US&type=5)

# Insurance Quote Item Relationships Object

The Quote Item Relationships object is an object that holds the table that's used for many-to-many quote line item relationships only. It creates a structure that lets Vlocity store driver data only one time.

[](https://help.salesforce.com/s?language=en_US)In the quote line item, the Subparent Id field is left blank for insured parties, and this table is populated. This makes it possible to store insured parties only one time. This structure is specific to a quote line item structure that looks like this:

[](https://help.salesforce.com/s?language=en_US)Insured party = child of insured item = child of root product

[](https://help.salesforce.com/s?language=en_US)You can access Quote Item Relationship objects from the Related tab of a quote line Item.

[](https://help.salesforce.com/s?language=en_US)Note

Vlocity uses this object only in quotes with a multi-item structure that includes grandchild insured parties.

If you don't see this object, this quote doesn't use that structure.

[](https://help.salesforce.com/s?language=en_US)The key quote item relationship fields are:

[](https://help.salesforce.com/s?language=en_US)

-   Name
    
    Name of the insured party in this relationship.
    
-   Parent Quote Line Item
    
    The quote line item Id of the insured item this insured party is attached to in this relationship.
    
-   Child Quote Line Item
    
    The quote line item of this insured party.
    
-   Attribute Selected Values
    
    The attributes and values that the customer set for this insured party.
    

Did this article solve your issue?

Let us know so we can improve!

YesNo