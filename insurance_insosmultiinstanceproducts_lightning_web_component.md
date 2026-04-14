---
title: "insOsMultiInstanceProducts Lightning Web Component"
source: "https://help.salesforce.com/s/articleView?id=ind.insurance_insosmultiinstanceproducts_lightning_web_component.htm&language=en_US&type=5"
scraped: "2026-04-14"
filter: "ind.insurance_"
---# insOsMultiInstanceProducts Lightning Web Component

insOsMultiInstanceProducts Lightning Web Component[](https://help.salesforce.com/s?language=en_US)

You are here:

1.  [Salesforce Help](/s/?language=en_US)
2.  [Docs](/s/products?language=en_US)
3.  [Digital Insurance](https://help.salesforce.com/s/articleView?id=ind.insurance_admin_standard.htm&language=en_US&type=5)

# insOsMultiInstanceProducts Lightning Web Component

The insOsMultiInstanceProducts Lightning web component is an enhanced version of the insOsMultiGrandchildrenProduct Lightning web component with the enableEdit option to edit insured item attributes. This component displays product information in OmniScripts that offer quote and policy purchase flows for insurance products that are multi-instance and include insured products and insured parties.

This Lightning web component helps users configure complex commercial quotes with multi-level insured item relationships and coverages. For example, a product structure with:

-   Commercial Root (1)
    
-   Commercial Root coverages such as "Valuables" (2)
    
-   Location insured item (3)
    
-   Location coverages such as "Hazard" (4)
    
-   Building insured item (5)
    
-   Building coverages such as "Earthquake" and "Wildfire" (6)
    

Note For the most complex product structures, the insOsMultiInstanceProducts Lightning web component supports coverages for the lowest-level insured item record types, not the lowest-level insured party record types. For example, in a Commercial Auto product with multiple levels of insured items, where a driver is the lowest-level insured party, insOsMultiInstanceProducts doesn't support coverage for the driver.

Use insOsMultiInstanceProducts along with insOsMultiInstanceChildProducts to build commercial quote flows for products with two levels of insured items, and coverages for the second level of insured items.

If root products are configured with multiple insured items, the insOsMultiInstanceProducts Lightning web component shows all the insured items even if they're not included in `userInputs` passed from `InsProductService:getRatedProducts`. This design makes it easier to add optional insured items in the user interface. If customers want to prevent optional insured items from appearing, they can use an Integration Procedure or Omnistudio Data Mapper to filter them out of the product JSON.

Did this article solve your issue?

Let us know so we can improve!

YesNo