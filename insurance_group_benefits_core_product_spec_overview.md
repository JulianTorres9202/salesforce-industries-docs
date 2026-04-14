---
title: "Product Specification Hierarchy for Group Benefits"
source: "https://help.salesforce.com/s/articleView?id=ind.insurance_group_benefits_core_product_spec_overview.htm&language=en_US&type=5"
scraped: "2026-04-14"
filter: "ind.insurance_"
---# Product Specification Hierarchy for Group Benefits

Product Specification Hierarchy for Group Benefits[](https://help.salesforce.com/s?language=en_US)

You are here:

1.  [Salesforce Help](/s/?language=en_US)
2.  [Docs](/s/products?language=en_US)
3.  [Digital Insurance](https://help.salesforce.com/s/articleView?id=ind.insurance_admin_standard.htm&language=en_US&type=5)

# Product Specification Hierarchy for Group Benefits

The product model for group benefits is built on a clear hierarchy where each layer serves a distinct purpose. The following table summarizes the role of each product spec, the type used, common attributes, and examples you’ll work with in the Medical Platinum model.

### Required Editions

<table class="slds-table slds-table_bordered slds-m-bottom_small edition" lwc-3eigj2skqo3=""><colgroup lwc-3eigj2skqo3=""><col style="width:100%" lwc-3eigj2skqo3=""></colgroup><tbody lwc-3eigj2skqo3=""><tr class="" lwc-3eigj2skqo3=""><td style="vertical-align:top;" class="slds-cell-wrap" lwc-3eigj2skqo3="">Available in: Lightning Experience</td></tr><tr class="" lwc-3eigj2skqo3=""><td style="vertical-align:top;" class="slds-cell-wrap" lwc-3eigj2skqo3="">Available in: <strong class="uicontrol" lwc-3eigj2skqo3="">Professional</strong>, <strong class="uicontrol" lwc-3eigj2skqo3="">Enterprise</strong>, and<strong class="uicontrol" lwc-3eigj2skqo3=""> Unlimited</strong> Editions of Digital Insurance with Digital Insurance Product Admin Add On, Digital Insurance Group Benefits AddOn, Digital Insurance Group Enrollment AddOn,Digital Insurance Group Benefits Customer Community AddOn, and Digital Insurance Group Benefits Partner Community AddOn licenses</td></tr></tbody></table>

| Product spec | description | type | common attributes | example |
| --- | --- | --- | --- | --- |
| Product | Bundled root insurance product against which a policy is issued. | Product | \- | Medical Platinum, Medical HMO, Dental Gold |
| Group Summary | Bundled Product that can be either multi-instance representing the sub-group within a group census or single-instance representing the entire group census | Product Classification | TotalMembers, AverageAge, Number\_of\_Employee\_with\_Spouse | Executive, Manager, Associate |
| Group Census Member | Bundled product (multi-instance) that represents the members within a group, which is also a insured party. | Product Classification | Age, Name, Gender, SmokerStatus, IsObese | John Doe, Jane Doe |
| Coverage | Non-bundled product that represents the risks against which the insured party is covered. | Product | Total Members, Number of Employee+Spouse, Avg, Age | Orthodontia, Surgery, Out-Patient, Critical Illness |

Did this article solve your issue?

Let us know so we can improve!

YesNo