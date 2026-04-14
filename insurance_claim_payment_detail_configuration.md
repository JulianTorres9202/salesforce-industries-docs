---
title: "Customize Data Entry with Payment Detail Configuration"
source: "https://help.salesforce.com/s/articleView?id=ind.insurance_claim_payment_detail_configuration.htm&language=en_US&type=5"
scraped: "2026-04-14"
filter: "ind.insurance_"
---# Customize Data Entry with Payment Detail Configuration

Customize Data Entry with Payment Detail Configuration[](https://help.salesforce.com/s?language=en_US)

You are here:

1.  [Salesforce Help](/s/?language=en_US)
2.  [Docs](/s/products?language=en_US)
3.  [Digital Insurance](https://help.salesforce.com/s/articleView?id=ind.insurance_admin_standard.htm&language=en_US&type=5)

# Customize Data Entry with Payment Detail Configuration

When a claim adjuster adds a financial item such as a loss or expense, the system needs to identify the form to present and the calculation logic to use. Claim admins can specify this behavior for each product.

### Required Editions

<table class="slds-table slds-table_bordered slds-m-bottom_small edition" lwc-3eigj2skqo3=""><colgroup lwc-3eigj2skqo3=""><col style="width:100%" lwc-3eigj2skqo3=""></colgroup><tbody lwc-3eigj2skqo3=""><tr class="" lwc-3eigj2skqo3=""><td style="vertical-align:top;" class="slds-cell-wrap" lwc-3eigj2skqo3=""><a title="Give users access to Claims Management features. Review the supported edition and permission sets for Claims Management." href="https://help.salesforce.com/s/articleView?id=ind.insurance_claim_perm_set_licenses.htm&amp;language=en_US&amp;type=5" lwc-3eigj2skqo3="">View supported editions.</a></td></tr></tbody></table>

The payment detail configuration is a mapping that links a specific coverage product to a custom user interface or custom logic.

-   **Field Sets:** You can create custom Field Sets on the Claim Coverage Payment Detail (CCPD) object. By configuring a product to a field set, you define the exact fields that appear in the data entry form for that item.
-   **Expression Sets and Integration Procedures:** For more advanced scenarios involving Loss Items, you can configure an Expression Set or Integration Procedure to override the default system logic for calculating adjusted amounts or processing limits.
-   **Loss and Expense Mapping:** The configuration is separate for Loss and Expense items. Expense item mapping typically requires only a Field Set as complex calculation overrides are less common.

-   **[Create Field Sets](https://help.salesforce.com/s/articleView?id=ind.insurance_claim_create_fld_set.htm&language=en_US&type=5)**  
    Salesforce has a drag-and-drop WYSIWYG tool for creating field sets.
-   **[Configure Payment Detail for Claims Financials](https://help.salesforce.com/s/articleView?id=ind.insurance_claim_configure_payment_detail.htm&language=en_US&type=5)**  
    Customize the Claim Coverage Payment Detail (CCDP) intake form and override default calculations.

Did this article solve your issue?

Let us know so we can improve!

YesNo