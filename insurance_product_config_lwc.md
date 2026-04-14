---
title: "Insurance Product Configuration Lightning Web Component"
source: "https://help.salesforce.com/s/articleView?id=ind.insurance_product_config_lwc.htm&language=en_US&type=5"
scraped: "2026-04-14"
filter: "ind.insurance_"
---# Insurance Product Configuration Lightning Web Component

Insurance Product Configuration Lightning Web Component[](https://help.salesforce.com/s?language=en_US)

You are here:

1.  [Salesforce Help](/s/?language=en_US)
2.  [Docs](/s/products?language=en_US)
3.  [Digital Insurance](https://help.salesforce.com/s/articleView?id=ind.insurance_admin_standard.htm&language=en_US&type=5)

# Insurance Product Configuration Lightning Web Component

Dynamically see how policy attribute changes affect the premium, enabling efficient, real-time quote generation. This component accepts multiple rating inputs and calls the Insurance Rating POST and PATCH APIs to update attribute values for specific coverages.

### Required Editions

<table class="slds-table slds-table_bordered slds-m-bottom_small edition" lwc-3eigj2skqo3=""><colgroup lwc-3eigj2skqo3=""><col style="width:100%" lwc-3eigj2skqo3=""></colgroup><tbody lwc-3eigj2skqo3=""><tr class="" lwc-3eigj2skqo3=""><td style="vertical-align:top;" class="slds-cell-wrap" lwc-3eigj2skqo3="">Available in: Lightning Experience</td></tr><tr class="" lwc-3eigj2skqo3=""><td style="vertical-align:top;" class="slds-cell-wrap" lwc-3eigj2skqo3="">Available in: <strong lwc-3eigj2skqo3="">Enterprise</strong>, <strong lwc-3eigj2skqo3="">Unlimited</strong>, and <strong lwc-3eigj2skqo3="">Developer</strong> Editions with the DigitalInsurancePlatform and Omnistudio licenses</td></tr></tbody></table>

This component allows users to modify attributes for a selected product such as coverage limits, and immediately view updated pricing. When the user adjusts a value (such as changing a deductible), the component calls the Rating API by using `POST` or `PATCH` to re-rate the product, then shows the updated `NetUnitPrice` and Tax Amount in the Price Summary.

The following settings are available to manage the configuration state and API calls:

-   `contextId`: The identifier for the current quote or transaction context required to update an existing quote.
-   `ratingInputs`: The initial set of inputs defining the product configuration.
-   `ratingOptions`: (Optional) Configuration for the pricing procedure and rule execution.
-   `transactionType`: Specifies the business transaction type.

-   **[Add Insurance Product Configuration Lightning Web Component](https://help.salesforce.com/s/articleView?id=ind.insurance_admin_setup_add_product_config_lwc.htm&language=en_US&type=5)**  
    Use OmniScript Designer to add the Product Selection Lightning web component and configure its side panel settings.

Did this article solve your issue?

Let us know so we can improve!

YesNo