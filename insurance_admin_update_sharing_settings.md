---
title: "Create and Update Sharing Rules for Insurance Coexistence"
source: "https://help.salesforce.com/s/articleView?id=ind.insurance_admin_update_sharing_settings.htm&language=en_US&type=5"
scraped: "2026-04-13"
filter: "ind.insurance_"
---# Create and Update Sharing Rules for Insurance Coexistence

Create and Update Sharing Rules for Insurance Coexistence[](https://help.salesforce.com/s?language=en_US)

You are here:

1.  [Salesforce Help](/s/?language=en_US)
2.  [Docs](/s/products?language=en_US)
3.  [Digital Insurance](https://help.salesforce.com/s/articleView?id=ind.insurance_admin_standard.htm&language=en_US&type=5)

# Create and Update Sharing Rules for Insurance Coexistence

Create and edit sharing rules for Product, Quote, Insurance Policy, and Claim to add the record type or the value of the Record Source field to the sharing criteria. The updated criteria ensures users have access to only the records they need.

### Required Editions

<table class="slds-table slds-table_bordered slds-m-bottom_small edition" lwc-3eigj2skqo3=""><colgroup lwc-3eigj2skqo3=""><col lwc-3eigj2skqo3=""></colgroup><tbody lwc-3eigj2skqo3=""><tr class="" lwc-3eigj2skqo3=""><td style="vertical-align:top;" class="slds-cell-wrap" lwc-3eigj2skqo3="">Available in: <strong lwc-3eigj2skqo3="">Performance</strong>, <strong lwc-3eigj2skqo3="">Enterprise</strong>, <strong lwc-3eigj2skqo3="">Unlimited</strong>, and <strong lwc-3eigj2skqo3="">Developer</strong> Editions with Digital Insurance, and Insurance CRM or the Insurance Industries and Insurance Industries Extension managed packages.</td></tr></tbody></table>

When you launch a new line of business, say Home Insurance, using Digital Insurance, give access to the associated products, quotes, insurance policies, and claims to only the teams managing this line of business. Also, update existing sharing rules so that the Home Insurance team doesn’t have access to records managed using Insurance managed package or Insurance CRM workflows for your older lines of business. In your criteria-based sharing rules, filter by the record type for products, quotes, insurance policies, and claims. Alternatively, filter quotes, insurance policies, and claims by the value of the Record Source field, which indicates the originating solution. The Record Source field is empty for Insurance managed package and Insurance CRM records, and has the value Digital Insurance for Digital Insurance records.

#### See Also

-   [Create Sharing Rules](https://help.salesforce.com/s/articleView?id=platform.security_sharing_rules_create.htm&language=en_US&type=5)
-   [Edit Sharing Rules](https://help.salesforce.com/s/articleView?id=platform.security_sharing_rules_edit.htm&language=en_US&type=5)

Did this article solve your issue?

Let us know so we can improve!

YesNo