---
title: "Add Insurance Product Configuration Lightning Web Component"
source: "https://help.salesforce.com/s/articleView?id=ind.insurance_admin_setup_add_product_config_lwc.htm&language=en_US&type=5"
scraped: "2026-04-13"
filter: "ind.insurance_"
---# Add Insurance Product Configuration Lightning Web Component

Add Insurance Product Configuration Lightning Web Component[](https://help.salesforce.com/s?language=en_US)

You are here:

1.  [Salesforce Help](/s/?language=en_US)
2.  [Docs](/s/products?language=en_US)
3.  [Digital Insurance](https://help.salesforce.com/s/articleView?id=ind.insurance_admin_standard.htm&language=en_US&type=5)

# Add Insurance Product Configuration Lightning Web Component

Use OmniScript Designer to add the Product Selection Lightning web component and configure its side panel settings.

### Required Editions

<table class="slds-table slds-table_bordered slds-m-bottom_small edition" lwc-3eigj2skqo3=""><colgroup lwc-3eigj2skqo3=""><col style="width:100%" lwc-3eigj2skqo3=""></colgroup><tbody lwc-3eigj2skqo3=""><tr class="" lwc-3eigj2skqo3=""><td style="vertical-align:top;" class="slds-cell-wrap" lwc-3eigj2skqo3="">Available in: Lightning Experience</td></tr><tr class="" lwc-3eigj2skqo3=""><td style="vertical-align:top;" class="slds-cell-wrap" lwc-3eigj2skqo3="">Available in: <strong lwc-3eigj2skqo3="">Enterprise</strong>, <strong lwc-3eigj2skqo3="">Unlimited</strong>, and <strong lwc-3eigj2skqo3="">Developer</strong> Editions with the DigitalInsuranceProductAdministrationAddOn, DigitalInsurancePolicyAdministrationAddOn licenses</td></tr></tbody></table>

| User Permissions Needed |
| --- |
| To add Insurance Policy Lightning web component: | DigitalInsuranceProductAdmin, Omnistudio User Permission |

1.  In the OmniScript Designer, drag a Custom LWC to a Step.
2.  Under **Lightning Web Component Name**, type the Product Selection component API Name: `industries_insurance_foundation:prodCfg`.
3.  In the properties panel, map the input data. Since this LWC extends the `OmniscriptBaseMixin`, it can read directly from the OmniScript data JSON, but you should explicitly map the following custom properties if they aren't automatically picked up:
    -   `ratingInputs`: Map this to the node in your data JSON containing the product configuration (attributes, product codes).
    -   `contextId`: Map this to the Context ID (often `%ContextId%`).
    -   `ratingOptions`: Map this to a JSON node specifying options like `pricingProcedure`.

#### See Also

-   [Custom LWC Element](https://help.salesforce.com/s/articleView?id=xcloud.os_custom_lwc_element_17587.htm&language=en_US&type=5)

Did this article solve your issue?

Let us know so we can improve!

YesNo