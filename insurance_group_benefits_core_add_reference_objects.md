---
title: "Add Reference Objects for Extended Attributes"
source: "https://help.salesforce.com/s/articleView?id=ind.insurance_group_benefits_core_add_reference_objects.htm&language=en_US&type=5"
scraped: "2026-04-14"
filter: "ind.insurance_"
---# Add Reference Objects for Extended Attributes

Add Reference Objects for Extended Attributes[](https://help.salesforce.com/s?language=en_US)

You are here:

1.  [Salesforce Help](/s/?language=en_US)
2.  [Docs](/s/products?language=en_US)
3.  [Digital Insurance](https://help.salesforce.com/s/articleView?id=ind.insurance_admin_standard.htm&language=en_US&type=5)

# Add Reference Objects for Extended Attributes

Extended attributes use census objects to supply product attribute values dynamically. To enable this, first add the relevant census objects to the reference object picklist.

### Required Editions

<table class="slds-table slds-table_bordered slds-m-bottom_small edition" lwc-3eigj2skqo3=""><colgroup lwc-3eigj2skqo3=""><col style="width:100%" lwc-3eigj2skqo3=""></colgroup><tbody lwc-3eigj2skqo3=""><tr class="" lwc-3eigj2skqo3=""><td style="vertical-align:top;" class="slds-cell-wrap" lwc-3eigj2skqo3="">Available in: Lightning Experience</td></tr><tr class="" lwc-3eigj2skqo3=""><td style="vertical-align:top;" class="slds-cell-wrap" lwc-3eigj2skqo3="">Available in: <strong class="uicontrol" lwc-3eigj2skqo3="">Professional</strong>, <strong class="uicontrol" lwc-3eigj2skqo3="">Enterprise</strong>, and<strong class="uicontrol" lwc-3eigj2skqo3=""> Unlimited</strong> Editions of Digital Insurance with Digital Insurance Product Admin Add On, Digital Insurance Group Benefits AddOn, Digital Insurance Group Enrollment AddOn,Digital Insurance Group Benefits Customer Community AddOn, and Digital Insurance Group Benefits Partner Community AddOn licenses</td></tr></tbody></table>

| User Permissions Needed |
| --- |
| To create group benefits product model | Product catalog management administrator |

1.  In the object manager, find and select **Product Classification Attribute**.
2.  Navigate to Fields & Relationships and open the Reference Object field.
3.  In Reference Object Picklist Values section, click **New**.
4.  Enter the API names of the Group Census Member and Group Census Group Class Summary objects.
    
    Tip You can find the API name of the object by searching for the object in Object Manager
    
5.  Save your changes.

Did this article solve your issue?

Let us know so we can improve!

YesNo