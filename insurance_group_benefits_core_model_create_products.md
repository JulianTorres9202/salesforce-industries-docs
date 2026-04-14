---
title: "Create Insurance Products for Group Benefits"
source: "https://help.salesforce.com/s/articleView?id=ind.insurance_group_benefits_core_model_create_products.htm&language=en_US&type=5"
scraped: "2026-04-14"
filter: "ind.insurance_"
---# Create Insurance Products for Group Benefits

Create Insurance Products for Group Benefits[](https://help.salesforce.com/s?language=en_US)

You are here:

1.  [Salesforce Help](/s/?language=en_US)
2.  [Docs](/s/products?language=en_US)
3.  [Digital Insurance](https://help.salesforce.com/s/articleView?id=ind.insurance_admin_standard.htm&language=en_US&type=5)

# Create Insurance Products for Group Benefits

Create products for the Medical Platinum hierarchy. Root product is the top-level spec that defines an insurance product, such as a health, dental, or vision plan. It can include one or more group classes, members, and coverages.

### Required Editions

<table class="slds-table slds-table_bordered slds-m-bottom_small edition" lwc-3eigj2skqo3=""><colgroup lwc-3eigj2skqo3=""><col style="width:100%" lwc-3eigj2skqo3=""></colgroup><tbody lwc-3eigj2skqo3=""><tr class="" lwc-3eigj2skqo3=""><td style="vertical-align:top;" class="slds-cell-wrap" lwc-3eigj2skqo3="">Available in: Lightning Experience</td></tr><tr class="" lwc-3eigj2skqo3=""><td style="vertical-align:top;" class="slds-cell-wrap" lwc-3eigj2skqo3="">Available in: <strong class="uicontrol" lwc-3eigj2skqo3="">Professional</strong>, <strong class="uicontrol" lwc-3eigj2skqo3="">Enterprise</strong>, and<strong class="uicontrol" lwc-3eigj2skqo3=""> Unlimited</strong> Editions of Digital Insurance with Digital Insurance Product Admin Add On, Digital Insurance Group Benefits AddOn, Digital Insurance Group Enrollment AddOn,Digital Insurance Group Benefits Customer Community AddOn, and Digital Insurance Group Benefits Partner Community AddOn licenses</td></tr></tbody></table>

| User Permissions Needed |
| --- |
| To create group benefits product model | Product catalog management administrator |

1.  From the App Launcher, find and select **Products**.
2.  Click **New**.
3.  Select **Product** as the record type.
4.  Click **Next**.
5.  Enter these field values:
    
    -   Name: Medical Platinum
    -   Product Code: medPlatinum
    -   Product Type: Bundle
    -   Status: Active
    -   Description: Medical Platinum root insurance product
    
6.  Click **Save**.

Repeat the process to create additional products for group summary, group census member, and coverages.

| Product spec | record type | product name | based on | product code | bundle |
| --- | --- | --- | --- | --- | --- |
| Group Summary | Group Summary | Group Summary | GroupSummary | groupSummary | Yes |
| Group Census Member | Group Census Member | Member – Medical Platinum | Member | medPlatinumMember | Yes |
| Coverage | Coverage | Preventive Care & Wellness | Coverage | pcw | No |
| Coverage | Coverage | Out-Patient | Coverage | outPatient | No |
| Coverage | Coverage | Maternity Care | Coverage | maternityCare | No |
| Coverage | Coverage | Critical Illness & Surgery | Coverage | cis | No |

Note

-   Product Catalog Management dynamically makes all products based on the classification available at the time of selection at run time. However, for Group Summary product classification, only one active product should inherit this classification.
-   For consistency, concatenate the root product code with "Member". For example, if the root product code is medPlatinum, use medPlatinumMember for the group census member product.

Did this article solve your issue?

Let us know so we can improve!

YesNo