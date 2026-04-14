---
title: "Configure Extended Attributes for Product Classifications or Products"
source: "https://help.salesforce.com/s/articleView?id=ind.insurance_group_benefits_core_update_configuration_in_product_classification.htm&language=en_US&type=5"
scraped: "2026-04-14"
filter: "ind.insurance_"
---# Configure Extended Attributes for Product Classifications or Products

Configure Extended Attributes for Product Classifications or Products[](https://help.salesforce.com/s?language=en_US)

You are here:

1.  [Salesforce Help](/s/?language=en_US)
2.  [Docs](/s/products?language=en_US)
3.  [Digital Insurance](https://help.salesforce.com/s/articleView?id=ind.insurance_admin_standard.htm&language=en_US&type=5)

# Configure Extended Attributes for Product Classifications or Products

If you want the attribute to have the same behavior across all products inheriting the product classification, update the configuration in product classification. For example, configure First Name and Last Name as extended attributes on the Member classification so that every product based on this classification automatically inherits them.

### Required Editions

<table class="slds-table slds-table_bordered slds-m-bottom_small edition" lwc-3eigj2skqo3=""><colgroup lwc-3eigj2skqo3=""><col style="width:100%" lwc-3eigj2skqo3=""></colgroup><tbody lwc-3eigj2skqo3=""><tr class="" lwc-3eigj2skqo3=""><td style="vertical-align:top;" class="slds-cell-wrap" lwc-3eigj2skqo3="">Available in: Lightning Experience</td></tr><tr class="" lwc-3eigj2skqo3=""><td style="vertical-align:top;" class="slds-cell-wrap" lwc-3eigj2skqo3="">Available in: <strong class="uicontrol" lwc-3eigj2skqo3="">Professional</strong>, <strong class="uicontrol" lwc-3eigj2skqo3="">Enterprise</strong>, and<strong class="uicontrol" lwc-3eigj2skqo3=""> Unlimited</strong> Editions of Digital Insurance with Digital Insurance Product Admin Add On, Digital Insurance Group Benefits AddOn, Digital Insurance Group Enrollment AddOn,Digital Insurance Group Benefits Customer Community AddOn, and Digital Insurance Group Benefits Partner Community AddOn licenses</td></tr></tbody></table>

| User Permissions Needed |
| --- |
| To create group benefits product model | Product catalog management administrator |

1.  Open the product classification or product where you want to configure the attribute.
2.  Navigate to the Attributes tab.
3.  In the Attributes section, click the down arrow next to an assigned attribute and click **Edit**.
4.  In Reference Object, select the object to pull data from. For example, select GroupCensusMember.
    
    The reference field name dynamically populates the list of available fields on the selected object.
    
5.  Select the field that you want to refer to for populating the attribute value. For example, select FirstName.
6.  Mark the field as read only to prevent updates to the values fetched from reference object and fields.
7.  Save your changes.

Repeat the same procedure for these attributes.

Product Classification: Group Summary

| reference object | Attribute | Reference field name |
| --- | --- | --- |
| Group Census Group Class Summary | Part Time Member Count | Part Time Member Count |
| Full Time Member Count | Full Time Member Count |
| Member Without Dependent Count | Member Without Dependent Count |
| Member With Spouse Count | Member With Spouse Count |
| Member With One Child Count | Member With One Child Count |
| Member With More Than Two Children Count | Member With More Than Two Children Count |
| Member With More Than One Child Count | Member With More Than One Child Count |
| Member With Dependent Count | Member With Dependent Count |
| Total Members | Total Members |
| Total Dependents | Total Dependents |
| Number of Primary Members | Number of Primary Members |
| Group Census Group Class Summary Name | Group Census Group Class Summary Name |

Product Classification: Member

Note Before you begin, create a custom formula field on the Group Census Member sObject with data type Number that uses the Birthdate field and Date functions.

| Reference object | attribute | reference field name |
| --- | --- | --- |
| Group Census Member | First Name | First Name |
| Last Name | Last Name |
| Age | Age |
| Gender | Gender |
| Marital Status | Marital Status |
| Smoker Status | Smoker Status |

Did this article solve your issue?

Let us know so we can improve!

YesNo