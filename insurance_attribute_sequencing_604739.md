---
title: "Attribute Sequencing"
source: "https://help.salesforce.com/s/articleView?id=ind.insurance_attribute_sequencing_604739.htm&language=en_US&type=5"
scraped: "2026-04-13"
filter: "ind.insurance_"
---# Attribute Sequencing

Attribute Sequencing[](https://help.salesforce.com/s?language=en_US)

You are here:

1.  [Salesforce Help](/s/?language=en_US)
2.  [Docs](/s/products?language=en_US)
3.  [Digital Insurance](https://help.salesforce.com/s/articleView?id=ind.insurance_admin_standard.htm&language=en_US&type=5)

# Attribute Sequencing

You add Display Sequence numbers to both attribute categories and attributes. Vlocity uses these sequence numbers to order the display attribute categories and attributes. Vlocity displays the first attribute category starting with the lowest display sequence number, then all the attributes in the first attribute category. Then it displays the second attribute category in the sequence, with all its attributes.

For example, you have three attribute categories with Display Sequence numbers 1, 2, and 3. Each of these attribute categories has five attributes with Display Sequence numbers 1, 2, 3, 4, and 5.

Here's what this display order looks like: 

```
Attribute Category DS 1 
    Attribute1 DS 1 
    Attribute1 DS 2 
    Attribute1 DS 3 
    Attribute1 DS 4 
    Attribute1 DS 5 
Attribute Category DS 2 
    Attribute2 DS 1 
    Attribute2 DS 2 
    Attribute2 DS 3 
    Attribute2 DS 4 
    Attribute2 DS 5 
Attribute Category DS 3 
    Attribute3 DS 1 
    Attribute3 DS 2 
    Attribute3 DS 3 
    Attribute3 DS 4 
    Attribute3 DS 5
```

Did this article solve your issue?

Let us know so we can improve!

YesNo