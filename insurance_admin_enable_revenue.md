---
title: "Enable Revenue Settings for Insurance"
source: "https://help.salesforce.com/s/articleView?id=ind.insurance_admin_enable_revenue.htm&language=en_US&type=5"
scraped: "2026-04-13"
filter: "ind.insurance_"
---# Enable Revenue Settings for Insurance

Enable Revenue Settings for Insurance[](https://help.salesforce.com/s?language=en_US)

You are here:

1.  [Salesforce Help](/s/?language=en_US)
2.  [Docs](/s/products?language=en_US)
3.  [Digital Insurance](https://help.salesforce.com/s/articleView?id=ind.insurance_admin_standard.htm&language=en_US&type=5)

# Enable Revenue Settings for Insurance

Digital Insurance works with Revenue Cloud to manage products and other tasks. Before you can use Insurance products, pricing, and rules to create quotes and manage policies, you must enable some Revenue Cloud settings.

### Required Editions

<table class="slds-table slds-table_bordered slds-m-bottom_small edition" lwc-3eigj2skqo3=""><colgroup lwc-3eigj2skqo3=""><col lwc-3eigj2skqo3=""></colgroup><tbody lwc-3eigj2skqo3=""><tr class="" lwc-3eigj2skqo3=""><td style="vertical-align:top;" class="slds-cell-wrap" lwc-3eigj2skqo3="">Available in: Lightning Experience</td></tr><tr class="" lwc-3eigj2skqo3=""><td style="vertical-align:top;" class="slds-cell-wrap" lwc-3eigj2skqo3="">Available in: <strong lwc-3eigj2skqo3="">Enterprise</strong>, <strong lwc-3eigj2skqo3="">Unlimited</strong>, and <strong lwc-3eigj2skqo3="">Developer</strong> Editions</td></tr></tbody></table>

| User Permissions Needed |
| --- |
| To work with configuration rules and constraints with Constraints Engine: | 
Product Configurator

 |
| To work with the Product and Price Configuration API: | ProductAndPriceConfiguration API |

1.  Set up quotes.
    1.  From Setup, in the Quick Find box, enter Quotes Settings, and then select **Quotes Settings**.
    2.  In Quotes Settings, select **Create Quotes Without a Related Opportunity**.
2.  Set up orders.
    1.  From Setup, in the Quick Find box, enter Order Settings, and then select **Order Settings**.
    2.  Select **Enable Orders**.
    3.  Select **Enable Negative Quantity**.
    4.  Select **Enable Zero Quantity**.
    5.  Select **Enable Enhanced Commerce Orders**.
3.  Set up Revenue Settings.
    1.  From Setup, in the Quick Find box, enter Revenue Settings, and then select **Revenue Settings**.
    2.  Select**Enable Revenue Cloud Features**.
    3.  Enable **Add Estimated Taxes to Quotes and Orders**.
    4.  Enable Product Configurator: Select **Configure Products at Runtime**.
    5.  Enable **Transaction processing for quotes and orders**.
4.  Using Salesforce Workbench or your preferred REST client, POST the following payload to `/services/data/v63.0/tooling/sobjects/TransactionProcessingType`:
    
    ```
    { 
        "SaveType": "Standard", 
        "Description": "Add a description here",    
        "DeveloperName": "AddYourOwnType",
        "MasterLabel": "Add a Label",
        "RuleEngine": "StandardConfigurator" 
    }
    ```
    
    Choose your own values for the Description, DeveloperName, and MasterLabel fields. You use the MasterLabel to refer to the pricing procedure when setting up a quote’s transaction type.
    

Did this article solve your issue?

Let us know so we can improve!

YesNo