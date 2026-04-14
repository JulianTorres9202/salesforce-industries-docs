---
title: "Create Extended Attributes for Reference Object IDs"
source: "https://help.salesforce.com/s/articleView?id=ind.insurance_group_benefits_core_create_extended_attributes_for_reference_object_ids.htm&language=en_US&type=5"
scraped: "2026-04-14"
filter: "ind.insurance_"
---# Create Extended Attributes for Reference Object IDs

Create Extended Attributes for Reference Object IDs[](https://help.salesforce.com/s?language=en_US)

You are here:

1.  [Salesforce Help](/s/?language=en_US)
2.  [Docs](/s/products?language=en_US)
3.  [Digital Insurance](https://help.salesforce.com/s/articleView?id=ind.insurance_admin_standard.htm&language=en_US&type=5)

# Create Extended Attributes for Reference Object IDs

For each extended attribute that you configure, create an additional extended attribute in the same product or product classification for the Id field of every unique sObject or custom object referenced in that configuration. For example, if you use the Contact and Group Census Member objects to reference the State and Age fields in the Member product classification, create two more extended attributes in the same classification, one for Contact and one for Group Census Member, to reference their Id fields.

### Required Editions

<table class="slds-table slds-table_bordered slds-m-bottom_small edition" lwc-3eigj2skqo3=""><colgroup lwc-3eigj2skqo3=""><col style="width:100%" lwc-3eigj2skqo3=""></colgroup><tbody lwc-3eigj2skqo3=""><tr class="" lwc-3eigj2skqo3=""><td style="vertical-align:top;" class="slds-cell-wrap" lwc-3eigj2skqo3="">Available in: Lightning Experience</td></tr><tr class="" lwc-3eigj2skqo3=""><td style="vertical-align:top;" class="slds-cell-wrap" lwc-3eigj2skqo3="">Available in: <strong class="uicontrol" lwc-3eigj2skqo3="">Professional</strong>, <strong class="uicontrol" lwc-3eigj2skqo3="">Enterprise</strong>, and<strong class="uicontrol" lwc-3eigj2skqo3=""> Unlimited</strong> Editions of Digital Insurance with Digital Insurance Product Admin Add On, Digital Insurance Group Benefits AddOn, Digital Insurance Group Enrollment AddOn,Digital Insurance Group Benefits Customer Community AddOn, and Digital Insurance Group Benefits Partner Community AddOn licenses</td></tr></tbody></table>

| User Permissions Needed |
| --- |
| To create group benefits product model | Product catalog management administrator |

The extended attribute for the Id field renders a standard lookup field in the configurator user interface and loads all available Contact and Group Census Member records for selection.

1.  Create an attribute definition of data type text.
    
    Ensure that the code for the attribute definition is same as the API name of the sObject or custom object.
    
2.  Associate the attribute to the product classification.
3.  Configure the attribute in the assigned attribute for product classification to update reference object and reference field name. Reference field name will be the Id of the sObject or custom object.
4.  Clear Read Only so users can select the record during quote configuration.
5.  Save your changes.

Repeat the procedure for each object in the table to add the required Id attributes.

| Attribute Definition | DataType | Code | Attribute Category | product classification |
| --- | --- | --- | --- | --- |
| Group Census Member | Text | GroupCensusMember | Basic Information | Member |
| Group Summary | Text | GrpCensusGrpClassSummary | Summary Reference Record | Group Summary |

Did this article solve your issue?

Let us know so we can improve!

YesNo