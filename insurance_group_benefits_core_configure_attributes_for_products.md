---
title: "Configure Attributes for Insurance Products"
source: "https://help.salesforce.com/s/articleView?id=ind.insurance_group_benefits_core_configure_attributes_for_products.htm&language=en_US&type=5"
scraped: "2026-04-14"
filter: "ind.insurance_"
---# Configure Attributes for Insurance Products

Configure Attributes for Insurance Products[](https://help.salesforce.com/s?language=en_US)

You are here:

1.  [Salesforce Help](/s/?language=en_US)
2.  [Docs](/s/products?language=en_US)
3.  [Digital Insurance](https://help.salesforce.com/s/articleView?id=ind.insurance_admin_standard.htm&language=en_US&type=5)

# Configure Attributes for Insurance Products

Products inherit attributes from their classification, but you can override them at the product level.

### Required Editions

<table class="slds-table slds-table_bordered slds-m-bottom_small edition" lwc-3eigj2skqo3=""><colgroup lwc-3eigj2skqo3=""><col style="width:100%" lwc-3eigj2skqo3=""></colgroup><tbody lwc-3eigj2skqo3=""><tr class="" lwc-3eigj2skqo3=""><td style="vertical-align:top;" class="slds-cell-wrap" lwc-3eigj2skqo3="">Available in: Lightning Experience</td></tr><tr class="" lwc-3eigj2skqo3=""><td style="vertical-align:top;" class="slds-cell-wrap" lwc-3eigj2skqo3="">Available in: <strong class="uicontrol" lwc-3eigj2skqo3="">Professional</strong>, <strong class="uicontrol" lwc-3eigj2skqo3="">Enterprise</strong>, and<strong class="uicontrol" lwc-3eigj2skqo3=""> Unlimited</strong> Editions of Digital Insurance with Digital Insurance Product Admin Add On, Digital Insurance Group Benefits AddOn, Digital Insurance Group Enrollment AddOn,Digital Insurance Group Benefits Customer Community AddOn, and Digital Insurance Group Benefits Partner Community AddOn licenses</td></tr></tbody></table>

| User Permissions Needed |
| --- |
| To create group benefits product model | Product catalog management administrator |

1.  Select the product for which you want to view and override the inherited attributes configuration.
2.  Navigate to the Attributes tab.
3.  Click the down arrow icon next to an inherited attribute and click **Configure**.
4.  In the New Product Attribute Definition window, edit the fields as necessary. For more details about the fields, see [Working with Product Attribute Fields](https://help.salesforce.com/s/articleView?id=ind.product_catalog_attribute_fields.htm&language=en_US&type=5).
5.  To display attributes of currency, number, and percent data types as sliders at run time, configure product attributes of these data types and specify these details:
    
    -   Select **Slider** under Display Type.
    -   Enter a minimum value.
    -   Enter a maximum value.
    -   Enter a step value.
    -   Enter a default value.
    
    You can override inherited attributes on individual products based on your business requirements. If no changes are needed, use the default behavior from the product classification.
    

Did this article solve your issue?

Let us know so we can improve!

YesNo