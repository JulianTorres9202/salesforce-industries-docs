---
title: "Set Up Pricing Discount for Multiroot Quotes"
source: "https://help.salesforce.com/s/articleView?id=ind.insurance_set_up_pricing_discount.htm&language=en_US&type=5"
scraped: "2026-04-14"
filter: "ind.insurance_"
---# Set Up Pricing Discount for Multiroot Quotes

Set Up Pricing Discount for Multiroot Quotes[](https://help.salesforce.com/s?language=en_US)

You are here:

1.  [Salesforce Help](/s/?language=en_US)
2.  [Docs](/s/products?language=en_US)
3.  [Digital Insurance](https://help.salesforce.com/s/articleView?id=ind.insurance_admin_standard.htm&language=en_US&type=5)

# Set Up Pricing Discount for Multiroot Quotes

Pricing Discount is an out-of-the-box solution used for calculating discounts on premiums for multiroot quotes. Your users can set up how discounts are calculated and applied to root-level products during the rating process.

### Required Editions

<table class="slds-table slds-table_bordered slds-m-bottom_small edition" lwc-3eigj2skqo3=""><colgroup lwc-3eigj2skqo3=""><col lwc-3eigj2skqo3=""></colgroup><tbody lwc-3eigj2skqo3=""><tr class="" lwc-3eigj2skqo3=""><td style="vertical-align:top;" class="slds-cell-wrap" lwc-3eigj2skqo3="">Available in: Lightning Experience</td></tr><tr class="" lwc-3eigj2skqo3=""><td style="vertical-align:top;" class="slds-cell-wrap" lwc-3eigj2skqo3="">Available in: <strong lwc-3eigj2skqo3="">Enterprise</strong>, <strong lwc-3eigj2skqo3="">Unlimited</strong>, and <strong lwc-3eigj2skqo3="">Developer</strong> Editions with the Insurance Industries managed package.</td></tr></tbody></table>

Complete these setup tasks:

1.  [Add attributes](https://help.salesforce.com/s/articleView?id=ind.insurance_add_attributes_directly_to_a_root_product_spec_606113.htm&language=en_US&type=5) and configure ‌them for rating at the root-product level.
    
    These attributes store the quote metadata that contains the number of root products in the quote.
    
2.  Create your own [integration procedure](https://help.salesforce.com/s/articleView?id=xcloud.os_omnistudio_integration_procedures_48334.htm&language=en_US&type=5) by using Omnistudio to calculate the pricing discount for multiroot quotes. This integration procedure adds the number of root products in the quote to the attributes ‌created earlier.
    
    -   Create and configure an [integration procedure](https://help.salesforce.com/s/articleView?id=xcloud.os_omnistudio_integration_procedures_48334.htm&language=en_US&type=5).
    -   In the Input Parameters pane, specify these key-value pairs.[](https://help.salesforce.com/s?language=en_US)
        -   ContextId: _quote ID_
        -   RootQLI: _RootQLIId_
            
    
3.  Create a [decision matrix](https://help.salesforce.com/s/articleView?id=ind.decision_matrices.htm&language=en_US&type=5). The decision matrix contains the mapping between the number of root products and the discount percentage.
4.  To calculate the discount, build an [expression set](https://help.salesforce.com/s/articleView?id=ind.expression_sets.htm&language=en_US&type=5) or modify an existing expression set.
    
    This expression set uses the decision matrix created previously to determine the discount. For example, if a user wants to apply a discount at the coverage level, the discount percentage decision matrix must be called in the coverage calculation step of the expression set.
    

Did this article solve your issue?

Let us know so we can improve!

YesNo