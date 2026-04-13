---
title: "Adjust the Total Price of a Single Root Quote"
source: "https://help.salesforce.com/s/articleView?id=ind.insurance_adjust_the_total_price_of_a_single_root_quote_612763.htm&language=en_US&type=5"
scraped: "2026-04-13"
filter: "ind.insurance_"
---# Adjust the Total Price of a Single Root Quote

Adjust the Total Price of a Single Root Quote[](https://help.salesforce.com/s?language=en_US)

You are here:

1.  [Salesforce Help](/s/?language=en_US)
2.  [Docs](/s/products?language=en_US)
3.  [Digital Insurance](https://help.salesforce.com/s/articleView?id=ind.insurance_admin_standard.htm&language=en_US&type=5)

# Adjust the Total Price of a Single Root Quote

With the Vlocity Manual Pricing component, users can adjust the total price of a single root quote manually. When they enter price adjustments, the quote automatically refreshes to show the adjustment amount and the updated price in real time.

Note

Users can’t adjust the total price for multi-root quotes.

1.  On the Quote page, add the Vlocity Manual Pricing component.
    1.  On a quote, click the Setup menu and select Edit Page.
    2.  Click the right sidebar, then click **Add Tab**.
    3.  Click the new tab and enter label values.
        
        <table class="slds-table slds-table_bordered slds-m-bottom_small" lwc-3eigj2skqo3=""><colgroup lwc-3eigj2skqo3=""><col style="width:50%" lwc-3eigj2skqo3=""><col style="width:50%" lwc-3eigj2skqo3=""></colgroup><tbody lwc-3eigj2skqo3=""><tr class="" lwc-3eigj2skqo3=""><td style="vertical-align:top;" class="slds-cell-wrap" lwc-3eigj2skqo3=""><p style="margin-bottom:0;" lwc-3eigj2skqo3=""><strong class="uicontrol" lwc-3eigj2skqo3="">Tab Label</strong></p></td><td style="vertical-align:top;" class="slds-cell-wrap" lwc-3eigj2skqo3=""><p style="margin-bottom:0;" lwc-3eigj2skqo3=""><kbd lwc-3eigj2skqo3="">Custom</kbd></p></td></tr><tr class="" lwc-3eigj2skqo3=""><td style="vertical-align:top;" class="slds-cell-wrap" lwc-3eigj2skqo3=""><p style="margin-bottom:0;" lwc-3eigj2skqo3=""><strong class="uicontrol" lwc-3eigj2skqo3="">Custom Label</strong></p></td><td style="vertical-align:top;" class="slds-cell-wrap" lwc-3eigj2skqo3=""><p style="margin-bottom:0;" lwc-3eigj2skqo3=""><kbd lwc-3eigj2skqo3="">Adjustments</kbd></p></td></tr></tbody></table>
        
    4.  Find the Vlocity Manual Pricing Component, then drag it to the new Adjustments tab.
2.  On a root product, add adjustment attributes.
    1.  On a product, click the Attributes tab, then click New in the right sidebar or under the attribute list.
    2.  Enter attribute values.
        
        <table class="slds-table slds-table_bordered slds-m-bottom_small" lwc-3eigj2skqo3=""><colgroup lwc-3eigj2skqo3=""><col style="width:50%" lwc-3eigj2skqo3=""><col style="width:50%" lwc-3eigj2skqo3=""></colgroup><tbody lwc-3eigj2skqo3=""><tr class="" lwc-3eigj2skqo3=""><td style="vertical-align:top;" class="slds-cell-wrap" lwc-3eigj2skqo3=""><p style="margin-bottom:0;" lwc-3eigj2skqo3=""><strong class="uicontrol" lwc-3eigj2skqo3="">Value Data Type</strong></p></td><td style="vertical-align:top;" class="slds-cell-wrap" lwc-3eigj2skqo3=""><p style="margin-bottom:0;" lwc-3eigj2skqo3="">For value, enter <kbd lwc-3eigj2skqo3="">Adjustment</kbd>. For data type, enter <kbd lwc-3eigj2skqo3="">Single Value</kbd>, <kbd lwc-3eigj2skqo3="">Slider</kbd>, or <kbd lwc-3eigj2skqo3="">Equalizer</kbd> based on how users enter adjustments for this attribute.</p></td></tr><tr class="" lwc-3eigj2skqo3=""><td style="vertical-align:top;" class="slds-cell-wrap" lwc-3eigj2skqo3=""><p style="margin-bottom:0;" lwc-3eigj2skqo3=""><strong class="uicontrol" lwc-3eigj2skqo3="">Adjustment Units</strong></p></td><td style="vertical-align:top;" class="slds-cell-wrap" lwc-3eigj2skqo3=""><p style="margin-bottom:0;" lwc-3eigj2skqo3=""><kbd lwc-3eigj2skqo3="">Currency</kbd> or <kbd lwc-3eigj2skqo3="">Percentage</kbd>.</p></td></tr><tr class="" lwc-3eigj2skqo3=""><td style="vertical-align:top;" class="slds-cell-wrap" lwc-3eigj2skqo3=""><p style="margin-bottom:0;" lwc-3eigj2skqo3=""><strong class="uicontrol" lwc-3eigj2skqo3="">Adjustment Comments</strong></p></td><td style="vertical-align:top;" class="slds-cell-wrap" lwc-3eigj2skqo3=""><p style="margin-bottom:0;" lwc-3eigj2skqo3=""><kbd lwc-3eigj2skqo3="">Required</kbd>, <kbd lwc-3eigj2skqo3="">Optional</kbd>, or <kbd lwc-3eigj2skqo3="">Not Used</kbd>, based on whether users enter descriptive information about price adjustments.</p></td></tr></tbody></table>
        

[](https://help.salesforce.com/s?language=en_US)

When users view quotes on a product, they can enter price adjustments for each adjustment attribute.

Did this article solve your issue?

Let us know so we can improve!

YesNo