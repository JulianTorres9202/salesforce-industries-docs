---
title: "Add Insurance Policy Lightning Web Component"
source: "https://help.salesforce.com/s/articleView?id=ind.insurance_admin_setup_add_insurance_policy_lwc.htm&language=en_US&type=5"
scraped: "2026-04-13"
filter: "ind.insurance_"
---# Add Insurance Policy Lightning Web Component

Add Insurance Policy Lightning Web Component[](https://help.salesforce.com/s?language=en_US)

You are here:

1.  [Salesforce Help](/s/?language=en_US)
2.  [Docs](/s/products?language=en_US)
3.  [Digital Insurance](https://help.salesforce.com/s/articleView?id=ind.insurance_admin_standard.htm&language=en_US&type=5)

# Add Insurance Policy Lightning Web Component

Use Lightning App Builder to add the Insurance Policy Lightning web component and configure its side panel settings.

### Required Editions

<table class="slds-table slds-table_bordered slds-m-bottom_small edition" lwc-3eigj2skqo3=""><colgroup lwc-3eigj2skqo3=""><col style="width:100%" lwc-3eigj2skqo3=""></colgroup><tbody lwc-3eigj2skqo3=""><tr class="" lwc-3eigj2skqo3=""><td style="vertical-align:top;" class="slds-cell-wrap" lwc-3eigj2skqo3="">Available in: Lightning Experience</td></tr><tr class="" lwc-3eigj2skqo3=""><td style="vertical-align:top;" class="slds-cell-wrap" lwc-3eigj2skqo3="">Available in: <strong lwc-3eigj2skqo3="">Enterprise</strong>, <strong lwc-3eigj2skqo3="">Unlimited</strong>, and <strong lwc-3eigj2skqo3="">Developer</strong> Editions with the DigitalInsuranceProductAdministrationAddOn, DigitalInsurancePolicyAdministrationAddOn licenses</td></tr></tbody></table>

| User Permissions Needed |
| --- |
| To add Insurance Policy Lightning web component: | DigitalInsuranceProductAdmin, DigitalInsuranceProductAdminRunTime, DigitalInsurancePolicyAdmin, FSCInsurance |

[](https://help.salesforce.com/s?language=en_US)Note The Insurance Policy Lightning web component data grid includes these default columns: Policy Line Item, Product, Effective Date, Expiration Date, Total Standard Premium, and Total Term Premium. You can’t modify these columns and the corresponding fields through Lightning App Builder. You can only add the Insurance Policy Lightning web component and customize the side panel settings.

1.  On the Insurance Policy details page, from Setup, select **Edit Page**.
2.  Add a new custom tab and give your tab a unique, descriptive label.
3.  In Lightning App Builder, drag the Insurance Policy component on to the new tab in the page layout.
4.  To show the side panel settings, select the component.
5.  Select **Show side panel when the user selects a policy line item**.
    
    This setting is selected by default. If you disable this setting, the side panel doesn’t appear when a user selects an insurance policy line item. Instead, the user is redirected to the details page of the line item.
    
6.  Select the side panel fields for Insurance Policy, Insurance Policy Asset, Insurance Policy Coverage, and Insurance Policy Participant.
    
    You can choose from both standard and custom fields for each policy line item. By default, users see the predefined fields. If you configure or modify the side panel fields, your selected fields replace the predefined fields.
    

Did this article solve your issue?

Let us know so we can improve!

YesNo