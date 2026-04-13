---
title: "Process a Commission Statement"
source: "https://help.salesforce.com/s/articleView?id=ind.insurance_brokerage_commission_statement_process.htm&language=en_US&type=5"
scraped: "2026-04-13"
filter: "ind.insurance_"
---# Process a Commission Statement

Process a Commission Statement[](https://help.salesforce.com/s?language=en_US)

You are here:

1.  [Salesforce Help](/s/?language=en_US)
2.  [Docs](/s/products?language=en_US)
3.  [Digital Insurance](https://help.salesforce.com/s/articleView?id=ind.insurance_admin_standard.htm&language=en_US&type=5)

# Process a Commission Statement

To process a commission statement, click the Process button on the respective commission statement record page or call the commission processing API.

### Required Editions

<table class="slds-table slds-table_bordered slds-m-bottom_small edition" lwc-3eigj2skqo3=""><colgroup lwc-3eigj2skqo3=""><col style="width:100%" lwc-3eigj2skqo3=""></colgroup><tbody lwc-3eigj2skqo3=""><tr class="" lwc-3eigj2skqo3=""><td style="vertical-align:top;" class="slds-cell-wrap" lwc-3eigj2skqo3="">Available in: Lightning Experience</td></tr><tr class="" lwc-3eigj2skqo3=""><td style="vertical-align:top;" class="slds-cell-wrap" lwc-3eigj2skqo3="">Available in: <strong lwc-3eigj2skqo3="">Professional</strong>, <strong lwc-3eigj2skqo3="">Enterprise</strong>, and <strong lwc-3eigj2skqo3="">Unlimited</strong> Editions where Financial Service Cloud and Insurance Brokerage are enabled</td></tr></tbody></table>

| User Permissions Needed |
| --- |
| To process a commission statement: | Insurance Commissions Management, Basic CSV Data Import User, and Insurance Brokerage User |

For information on how the API processes the commission statement, see [Commission Processing](https://developer.salesforce.com/docs/atlas.en-us.insurance_developer_guide.meta/insurance_developer_guide/connect_resources_commission_processing.htm).

-   **[How the Process Commission Flow Works](https://help.salesforce.com/s/articleView?id=ind.insurance_brokerage_commission_statement_process_flow.htm&language=en_US&type=5)**  
    The Process Commission flow processes producer commissions by identifying the insurance policy, computing and creating producer commission records, and updating the status of the associated commission statement line item.
-   **[Reprocess Commission Statement Line Items](https://help.salesforce.com/s/articleView?id=ind.insurance_brokerage_commission_statement_reprocess_line_items.htm&language=en_US&type=5)**  
    Reprocess the commission statement line items that fail processing. To reprocess the line items, fix the issues and click Process.

Did this article solve your issue?

Let us know so we can improve!

YesNo