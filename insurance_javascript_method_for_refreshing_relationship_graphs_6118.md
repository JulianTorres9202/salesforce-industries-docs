---
title: "JavaScript Method for Refreshing Relationship Graphs"
source: "https://help.salesforce.com/s/articleView?id=ind.insurance_javascript_method_for_refreshing_relationship_graphs_6118.htm&language=en_US&type=5"
scraped: "2026-04-14"
filter: "ind.insurance_"
---# JavaScript Method for Refreshing Relationship Graphs

JavaScript Method for Refreshing Relationship Graphs[](https://help.salesforce.com/s?language=en_US)

You are here:

1.  [Salesforce Help](/s/?language=en_US)
2.  [Docs](/s/products?language=en_US)
3.  [Digital Insurance](https://help.salesforce.com/s/articleView?id=ind.insurance_admin_standard.htm&language=en_US&type=5)

# JavaScript Method for Refreshing Relationship Graphs

If you embed a Relationship Graph in another Lightning Web Component, you can use the JavaScript refreshGraph method to refresh the Relationship Graph.

Where: Available in Vlocity Health and Insurance Spring '21 and later releases.

Who: Lightning Web Component developers can use this method in .js files.

Why: If another embedded Lightning Web Component lets you change data that might affect the graph, that Lightning Web Component component can refresh the graph after any such change.

How: In the Lightning Web Component's .html file, embed the Relationship Graph component. In the .js file, call the refreshGraph method.

Did this article solve your issue?

Let us know so we can improve!

YesNo