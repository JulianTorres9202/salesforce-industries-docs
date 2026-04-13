---
title: "Create a Commission Statement and Related Line Items"
source: "https://help.salesforce.com/s/articleView?id=ind.insurance_brokerage_commission_statement_and_line_items_create.htm&language=en_US&type=5"
scraped: "2026-04-13"
filter: "ind.insurance_"
---# Create a Commission Statement and Related Line Items

Create a Commission Statement and Related Line Items

You are here:

1.  [Salesforce Help](/s/?language=en_US)
2.  [Docs](/s/products?language=en_US)
3.  [Digital Insurance](https://help.salesforce.com/s/articleView?id=ind.insurance_admin_standard.htm&language=en_US&type=5)

[](https://help.salesforce.com/s?language=en_US)

# Create a Commission Statement and Related Line Items

Create a commission statement that summarizes the total commission earned by a producer or salesperson over a specific period, such as a month or a quarter. The statement provides a detailed breakdown of the commission amounts and the sources from which they are derived. Ensure transparency and accountability, by helping producers understand how their commission is calculated and from which sales or policies it’s generated.

### Required Editions

<table class="slds-table slds-table_bordered slds-m-bottom_small edition" lwc-3eigj2skqo3=""><colgroup lwc-3eigj2skqo3=""><col style="width:100%" lwc-3eigj2skqo3=""></colgroup><tbody lwc-3eigj2skqo3=""><tr class="" lwc-3eigj2skqo3=""><td style="vertical-align:top;" class="slds-cell-wrap" lwc-3eigj2skqo3="">Available in: Lightning Experience</td></tr><tr class="" lwc-3eigj2skqo3=""><td style="vertical-align:top;" class="slds-cell-wrap" lwc-3eigj2skqo3="">Available in: <strong lwc-3eigj2skqo3="">Professional</strong>, <strong lwc-3eigj2skqo3="">Enterprise</strong>, and <strong lwc-3eigj2skqo3="">Unlimited</strong> Editions where Financial Service Cloud and Insurance Brokerage are enabled</td></tr></tbody></table>

| User Permissions Needed |
| --- |
| To assign producer split arrangement to an account: | Insurance Commissions Management, Basic CSV Data Import User, and Insurance Brokerage User |

[](https://help.salesforce.com/s?language=en_US)

## Create a Commission Statement

Create a commission statement that represents a commission summary associated with a party or commission statement line item.

### Required Editions

<table class="slds-table slds-table_bordered slds-m-bottom_small edition" lwc-3eigj2skqo3=""><colgroup lwc-3eigj2skqo3=""><col style="width:100%" lwc-3eigj2skqo3=""></colgroup><tbody lwc-3eigj2skqo3=""><tr class="" lwc-3eigj2skqo3=""><td style="vertical-align:top;" class="slds-cell-wrap" lwc-3eigj2skqo3="">Available in: Lightning Experience</td></tr><tr class="" lwc-3eigj2skqo3=""><td style="vertical-align:top;" class="slds-cell-wrap" lwc-3eigj2skqo3="">Available in: <strong lwc-3eigj2skqo3="">Professional</strong>, <strong lwc-3eigj2skqo3="">Enterprise</strong>, and <strong lwc-3eigj2skqo3="">Unlimited</strong> Editions where Financial Service Cloud and Insurance Brokerage are enabled</td></tr></tbody></table>

| User Permissions Needed |
| --- |
| To create a commission statement: | Insurance Commissions Management, Basic CSV Data Import User, and Insurance Brokerage User |

1.  From the App Launcher, find and select **Commission Statements**.
2.  Click **New**.
3.  In the New Commission Statement window, enter these details.
    
    | field name | description |
    | --- | --- |
    | Name | The name of the commission statement summary record. |
    | Account | The account that's associated with the commission statement. |
    | Statement Date | The date when the commission statement was generated for an account. |
    | Status | Specifies the status of the commission statement summary. |
    | Payment Amount | The amount paid by the payor account. |
    | Payment Method | Specifies the payment method used to pay the commission. |
    | Payment Reference Identifier | The identifier of the external transaction associated with the commission payment. |
    | Accounting Date | The accounting date of the commission statement. |
    
4.  Save your changes
    
    A message confirms that the commission statement is created.
    

[](https://help.salesforce.com/s?language=en_US)

## Create a Commission Statement Line Item

Create a commission statement line item that represents commission information associated with a service or an item. You can either upload a CSV file or manually create the line items.

### Required Editions

<table class="slds-table slds-table_bordered slds-m-bottom_small edition" lwc-3eigj2skqo3=""><colgroup lwc-3eigj2skqo3=""><col style="width:100%" lwc-3eigj2skqo3=""></colgroup><tbody lwc-3eigj2skqo3=""><tr class="" lwc-3eigj2skqo3=""><td style="vertical-align:top;" class="slds-cell-wrap" lwc-3eigj2skqo3="">Available in: Lightning Experience</td></tr><tr class="" lwc-3eigj2skqo3=""><td style="vertical-align:top;" class="slds-cell-wrap" lwc-3eigj2skqo3="">Available in: <strong lwc-3eigj2skqo3="">Professional</strong>, <strong lwc-3eigj2skqo3="">Enterprise</strong>, and <strong lwc-3eigj2skqo3="">Unlimited</strong> Editions where Financial Service Cloud and Insurance Brokerage are enabled</td></tr></tbody></table>

| User Permissions Needed |
| --- |
| To create a commission statement line item: | Insurance Commissions Management, Basic CSV Data Import User, and Insurance Brokerage User |

1.  From the App Launcher, go to **Commission Statements**, and open a commission statement record for which you want to create line items.
2.  From the commission statement record page, click the **Related** tab.
3.  In the Commission Statement Line Items section, click **CSV Import**.
4.  In the Import window, click **Upload Files**.
5.  After the file is imported, click **Done**.
6.  Preview the uploaded CSV file and then click **Next**.
    
    The Salesforce object is autopopulated.
    
7.  Select Insert for the Import Type field, and click **Next**.
8.  Enable **View Unmapped Columns** and verify that the fields are automapped.
    
    When the uploaded CSV file contains standard fields, the CSV file is automapped. If you upload a nonstandard CSV file, you must manually map the fields in the source data to the fields in the Salesforce Object column.
    
    [](https://help.salesforce.com/s?language=en_US)Tip To avoid manual mapping of fields for statements that the carrier uploads for processing next time, select Save mapping configuration, enter a name for the file, and click Save & Download. When you upload a nonstandard CSV file again, in the Map Column step, select Use a saved mapping configuration and upload the previously saved file with the right mappings.
    
9.  Click **Next**, and then click **Start Import**.
10.  To manually create the line items, in the Commission Statement Line Items section, click **New**.
11.  Enter the required details and save your changes.

The commission statement line items are created.

Did this article solve your issue?

Let us know so we can improve!

YesNo