---
title: "Claim Financials Setup and Runtime Experience"
source: "https://help.salesforce.com/s/articleView?id=ind.insurance_claim_dynamic_data_capture.htm&language=en_US&type=5"
scraped: "2026-04-14"
filter: "ind.insurance_"
---# Claim Financials Setup and Runtime Experience

Claim Financials Setup and Runtime Experience[](https://help.salesforce.com/s?language=en_US)

You are here:

1.  [Salesforce Help](/s/?language=en_US)
2.  [Docs](/s/products?language=en_US)
3.  [Digital Insurance](https://help.salesforce.com/s/articleView?id=ind.insurance_admin_standard.htm&language=en_US&type=5)

# Claim Financials Setup and Runtime Experience

Use the configuration-driven framework for Claim Coverage Payment Detail (CCPD) forms to tailor the payment details data capture process as per your business needs. Define both the user interface layout and the underlying calculation logic without requiring custom code. The result is a dynamic system that ensures data is captured accurately and efficiently, adapting automatically to the context of the claim.

### Required Editions

<table class="slds-table slds-table_bordered slds-m-bottom_small edition" lwc-3eigj2skqo3=""><colgroup lwc-3eigj2skqo3=""><col style="width:100%" lwc-3eigj2skqo3=""></colgroup><tbody lwc-3eigj2skqo3=""><tr class="" lwc-3eigj2skqo3=""><td style="vertical-align:top;" class="slds-cell-wrap" lwc-3eigj2skqo3=""><a title="Give users access to Claims Management features. Review the supported edition and permission sets for Claims Management." href="https://help.salesforce.com/s/articleView?id=ind.insurance_claim_perm_set_licenses.htm&amp;language=en_US&amp;type=5" lwc-3eigj2skqo3="">View supported editions.</a></td></tr></tbody></table>

## The Setup Experience

Admins can design unique data capture experiences for different financial scenarios. The configuration is centered around mapping a specific Policy Coverage Product to a set of UI and business logic rules.

-   **Coverage-Specific Layouts:** Configure distinct forms for both Loss and Expense items on a per-policy coverage product basis.
-   **Dynamic Field Display:** By associating a coverage product with a designated Field Set, you can dynamically extend the CCPD form to include the precise standard and custom fields required for that context.
-   **Custom Calculation Logic:** The framework allows for overriding the predefined calculation logic for adjustments and limits by linking the product to a custom Expression Set or Integration Procedure.

## The Runtime Experience

For the claim adjuster, the administrative configurations translate into a seamless and intuitive workflow where the system handles the complexity internally.

-   **Context-Aware Forms:** When an adjuster adds a financial item, the system automatically presents a tailored form layout with fields that are specific to the selected coverage.
-   **Automated Logic Application:** The underlying business rules, including any custom adjustment logic and validations defined by the administrator, are applied dynamically in the background.
-   **Efficiency and Accuracy:** Eliminate the need for manual intervention, making sure that the correct data is captured accurately and efficiently by using the configuration-driven behavior.

Did this article solve your issue?

Let us know so we can improve!

YesNo