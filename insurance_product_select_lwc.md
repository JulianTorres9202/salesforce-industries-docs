---
title: "Insurance Product Selection Lightning Web Component"
source: "https://help.salesforce.com/s/articleView?id=ind.insurance_product_select_lwc.htm&language=en_US&type=5"
scraped: "2026-04-14"
filter: "ind.insurance_"
---# Insurance Product Selection Lightning Web Component

Insurance Product Selection Lightning Web Component[](https://help.salesforce.com/s?language=en_US)

You are here:

1.  [Salesforce Help](/s/?language=en_US)
2.  [Docs](/s/products?language=en_US)
3.  [Digital Insurance](https://help.salesforce.com/s/articleView?id=ind.insurance_admin_standard.htm&language=en_US&type=5)

# Insurance Product Selection Lightning Web Component

The Insurance Product Selection Lightning Web Component enables end users to effortlessly compare multiple rated insurance products and choose the optimal plan directly within a guided OmniScript flow.

### Required Editions

<table class="slds-table slds-table_bordered slds-m-bottom_small edition" lwc-3eigj2skqo3=""><colgroup lwc-3eigj2skqo3=""><col style="width:100%" lwc-3eigj2skqo3=""></colgroup><tbody lwc-3eigj2skqo3=""><tr class="" lwc-3eigj2skqo3=""><td style="vertical-align:top;" class="slds-cell-wrap" lwc-3eigj2skqo3="">Available in: Lightning Experience</td></tr><tr class="" lwc-3eigj2skqo3=""><td style="vertical-align:top;" class="slds-cell-wrap" lwc-3eigj2skqo3="">Available in: <strong lwc-3eigj2skqo3="">Enterprise</strong>, <strong lwc-3eigj2skqo3="">Unlimited</strong>, and <strong lwc-3eigj2skqo3="">Developer</strong> Editions with the DigitalInsurancePlatform and Omnistudio licenses</td></tr></tbody></table>

Quickly compare up to three different root products side-by-side to understand variations in coverages and pricing. This component passes multiple rating inputs to the Insurance Rating API, which rates several root products and returns the calculated premiums and details. The UI displays product cards showing the Premium for each option, enabling the user to select one and proceed.

These properties are available to configure how the component interacts with the Rating API and displays data:

[](https://help.salesforce.com/s?language=en_US)

-   `ratedProdDescriptions`: A user-defined map allowing you to provide specific descriptions for each rated root product displayed in the UI
-   `ratingInputs`: The collection of user inputs and product codes to be rated
-   `ratingOptions`: A map containing rating settings such as specific pricing procedures
-   `rootProductCodes`: Multiple root products to use with one set of child inputs
-   `transactionType`: The type of transaction, such as Endorsement or New Business

If you want to use the same child inputs on multiple root products, set those inputs to have `reusable=true`, and pass the root products in `rootProductCode`s instead of `ratingInputs`.

Here’s a sample payload with multiple roots:

```
{​
"ratingInputs": [{​
  "productCode": "auto",
  "instanceKeys":["Audi"], "reusable": true,
  "attributes": {​
    "autoValue": "20000",
    "autoAge": "5",
    }
  }],
"rootProductCodes": ["autoSilver", "autoPlatinum", "autoBronze", "autoGold"]
}
```

-   **[Add Insurance Product Selection Lightning Web Component](https://help.salesforce.com/s/articleView?id=ind.insurance_admin_setup_add_product_select_lwc.htm&language=en_US&type=5)**  
    Use Omnistudio Designer to add the Product Selection Lightning web component and configure its side panel settings.

Did this article solve your issue?

Let us know so we can improve!

YesNo