---
title: "insOsMultiInstanceChildProducts Lightning Web Component"
source: "https://help.salesforce.com/s/articleView?id=ind.insurance_insosmultiinstancechildproducts_lightning_web_component.htm&language=en_US&type=5"
scraped: "2026-04-14"
filter: "ind.insurance_"
---# insOsMultiInstanceChildProducts Lightning Web Component

insOsMultiInstanceChildProducts Lightning Web Component[](https://help.salesforce.com/s?language=en_US)

You are here:

1.  [Salesforce Help](/s/?language=en_US)
2.  [Docs](/s/products?language=en_US)
3.  [Digital Insurance](https://help.salesforce.com/s/articleView?id=ind.insurance_admin_standard.htm&language=en_US&type=5)

# insOsMultiInstanceChildProducts Lightning Web Component

The insOsMultiInstanceChildProducts Lightning web component displays two levels of insured items, and coverages for the second level of insured items, in a quote OmniScript.

For example, for a commercial quote, this component displays:

-   All the Location insured items (such as 500 Maple Drive and 123 Elm Street)
    
-   For each Location, all the related Building insured items (such as Warehouse and Factory)
    
-   For each Building, all the related eligible coverages (such as Earthquake and Wildfire)
    

Here's a preview of the OmniScript step for configuring buildings:

-   Location insured items (1)
    
-   Building insured item (2)
    
-   Building coverages (3)
    

The component lets users edit attributes configured with "Is Configurable" selected, and it hides attributes configured with "Is Hidden" selected.

Here's a closer look at the OmniScript step for configuring buildings:

## insOsMultiInstanceChildProducts Custom Lightning Web Component Properties

A guided flow that walks users through the configuration of a commercial root product typically uses enableEdit, initJSON, initAction, and rePriceAction custom Lightning web component properties.

For commercial product quote flows, you typically use initAction to configure the getRatedProducts service. This service fetches the product JSON to feed into insOsMultiInstanceProducts. In OmniScript steps:

-   An initAction configures the `InsProductService: getRatedProducts` service to fetch product JSON and feed it into insOsMultiInstanceProducts.
    
-   insOsMultiInstanceProducts displays the root, parent, and child insured items, as well as the parent insured item coverages. A user configures and reprices the _parent_ insured item coverages and attributes in this LWC. The user's changes are passed to the next step of the flow as initJSON.
    
-   insOsMultiInstanceChildProducts uses the product JSON passed in from the previous step as initJSON to display the child insured items and their coverages. Here is where a user configures and reprices the _child_ insured item coverages.
    

When you configure the insOsMultiInstanceChildProducts Lightning web component, configure the reprice method and its options in the JSON Editor in custom Lightning web component properties.

| 
Property

 | 

Details

 |
| --- | --- |
| 

enableEdit

 | 

Use enableEdit to enable insured item and insured party attribute edits in insOsMultiInstanceProducts.

Note:

-   Attribute rules for insured item attribute and insured party attribute changes are not currently supported.
    
-   insOsMultiInstanceChildProducts does not support enableEdit.
    

In an OmniScript step that calls insOsMultiInstanceProducts, add enableEdit as a custom Lightning web component property using the format enable-edit, and define it as true.

 |
|  |
| 

initJSON

 | 

Use initJSON as an alternative to remote calls. It passes the entire product JSON structure as the data source to a Lightning web component.

The insOsMultiInstanceChildProducts Lightning web component often uses initJSON.

Add initJSON as a custom Lightning web component property using the format init-json. In this example, insOsMultiInstanceChildProducts takes the product JSON passed to it from the previous step.

 |
|  |
| 

initAction and rePriceAction

 | 

For initAction, configure the optionsMap and inputMap that get passed to `InsProductService: getRatedProducts`. This method gets called on the first load to fetch product data.

For rePriceAction, configure the optionsMap and inputMap for `InsProductService: rePriceProduct`. This method gets called every time a user makes a change to product attributes and reprices the product.

In the Custom Lightning Web Component Properties pane, click Edit Properties as JSON to configure initAction and rePriceAction.

 |
|  |

Did this article solve your issue?

Let us know so we can improve!

YesNo