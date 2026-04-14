---
title: "Create a Parent-Child Hierarchy for Trailing Documents"
source: "https://help.salesforce.com/s/articleView?id=ind.insurance_create_a_parent_child_hierarchy_for_trailing_documents_609114.htm&language=en_US&type=5"
scraped: "2026-04-14"
filter: "ind.insurance_"
---# Create a Parent-Child Hierarchy for Trailing Documents

Create a Parent-Child Hierarchy for Trailing Documents[](https://help.salesforce.com/s?language=en_US)

You are here:

1.  [Salesforce Help](/s/?language=en_US)
2.  [Docs](/s/products?language=en_US)
3.  [Digital Insurance](https://help.salesforce.com/s/articleView?id=ind.insurance_admin_standard.htm&language=en_US&type=5)

# Create a Parent-Child Hierarchy for Trailing Documents

Organize documents associated with different objects within directories. To create the directories, use a custom formula field named UniqueField in the Trailing Document Placeholder object.

When you set up the formula options, add one for each object for which you want a parent-child relationship. In the case of trailing documents, the parent is the object, and the children are the documents.

This example includes parent-child formulas for Quote and Case:

Did this article solve your issue?

Let us know so we can improve!

YesNo