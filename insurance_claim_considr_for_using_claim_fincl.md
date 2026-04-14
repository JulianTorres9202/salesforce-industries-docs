---
title: "Considerations for Claims Financials"
source: "https://help.salesforce.com/s/articleView?id=ind.insurance_claim_considr_for_using_claim_fincl.htm&language=en_US&type=5"
scraped: "2026-04-14"
filter: "ind.insurance_"
---# Considerations for Claims Financials

Considerations for Claims Financials[](https://help.salesforce.com/s?language=en_US)

You are here:

1.  [Salesforce Help](/s/?language=en_US)
2.  [Docs](/s/products?language=en_US)
3.  [Digital Insurance](https://help.salesforce.com/s/articleView?id=ind.insurance_admin_standard.htm&language=en_US&type=5)

# Considerations for Claims Financials

Review these considerations related to Claims Financials.

### Required Editions

<table class="slds-table slds-table_bordered slds-m-bottom_small edition" lwc-3eigj2skqo3=""><colgroup lwc-3eigj2skqo3=""><col style="width:100%" lwc-3eigj2skqo3=""></colgroup><tbody lwc-3eigj2skqo3=""><tr class="" lwc-3eigj2skqo3=""><td style="vertical-align:top;" class="slds-cell-wrap" lwc-3eigj2skqo3=""><a title="Give users access to Claims Management features. Review the supported edition and permission sets for Claims Management." href="https://help.salesforce.com/s/articleView?id=ind.insurance_claim_perm_set_licenses.htm&amp;language=en_US&amp;type=5" lwc-3eigj2skqo3="">View supported editions.</a></td></tr></tbody></table>

-   Full multi-currency functionality including calculations for adjustments and limits isn't supported.
-   If multi-currency is enabled, you'll see a currency dropdown, but backend processing defaults to the org's primary currency. For example, the primary currency is USD.
-   Creating or editing claim coverages may fail if the parent Claim record lacks a properly set Loss Date and a link to an Insurance Policy.
-   Use APIs to create a claim coverage without a mandatory participant, but these records may cause errors when viewed in the Claim Financials component due to validation.

Did this article solve your issue?

Let us know so we can improve!

YesNo