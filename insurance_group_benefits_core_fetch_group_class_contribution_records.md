---
title: "Fetch Group Class Contribution Records for Premium Calculation"
source: "https://help.salesforce.com/s/articleView?id=ind.insurance_group_benefits_core_fetch_group_class_contribution_records.htm&language=en_US&type=5"
scraped: "2026-04-14"
filter: "ind.insurance_"
---# Fetch Group Class Contribution Records for Premium Calculation

Fetch Group Class Contribution Records for Premium Calculation[](https://help.salesforce.com/s?language=en_US)

You are here:

1.  [Salesforce Help](/s/?language=en_US)
2.  [Docs](/s/products?language=en_US)
3.  [Digital Insurance](https://help.salesforce.com/s/articleView?id=ind.insurance_admin_standard.htm&language=en_US&type=5)

# Fetch Group Class Contribution Records for Premium Calculation

During enrollment, fetch all the valid group class contribution records for the group class associated with each member.

### Required Editions

<table class="slds-table slds-table_bordered slds-m-bottom_small edition" lwc-3eigj2skqo3=""><colgroup lwc-3eigj2skqo3=""><col style="width:100%" lwc-3eigj2skqo3=""></colgroup><tbody lwc-3eigj2skqo3=""><tr class="" lwc-3eigj2skqo3=""><td style="vertical-align:top;" class="slds-cell-wrap" lwc-3eigj2skqo3="">Available in: Lightning Experience</td></tr><tr class="" lwc-3eigj2skqo3=""><td style="vertical-align:top;" class="slds-cell-wrap" lwc-3eigj2skqo3="">Available in: <strong class="uicontrol" lwc-3eigj2skqo3="">Professional</strong>, <strong class="uicontrol" lwc-3eigj2skqo3="">Enterprise</strong>, and<strong class="uicontrol" lwc-3eigj2skqo3=""> Unlimited</strong> Editions of Digital Insurance with Digital Insurance Product Admin Add On, Digital Insurance Group Benefits AddOn, Digital Insurance Group Enrollment AddOn,Digital Insurance Group Benefits Customer Community AddOn, and Digital Insurance Group Benefits Partner Community AddOn licenses</td></tr></tbody></table>

Valid records are group class contributions with a start date on or before the contract start date, an end date on or after the contract end date, and a type that's not blank or null.

The logic used to select the group class contribution record from the fetched list to calculate premium for a specific census member and plan combination are described in the later sections.

The system applies contribution rules at the coverage premium level and not the overall premium). This ensures that if a rule exists for a specific coverage, it takes precedence over plan-level or category-level rules. For each of the below mentioned cases, if there are multiple group class contribution records, the most recently modified group class contribution record is picked up to calculate premium.

Subscriber (Primary Member)

The system selects contribution records in this sequence of priority:

-   Coverage Contract Group Plan = Rule Contract Group Plan
-   Coverage Product = Rule Product
-   Coverage Parent Contract Group Plan = Rule Contract Group Plan
-   Product associated with Coverage Parent Contract Group Plan = Rule Product
-   Product Category of the above Product = Rule Product Category

Dependent

The system selects contribution records in this sequence of priority:

-   Coverage Contract Group Plan = Rule Contract Group Plan
-   Coverage Product = Rule Product
-   Coverage Parent Contract Group Plan = Rule Contract Group Plan
-   Product associated with Coverage Parent Contract Group Plan = Rule Product
-   Product Category of the above Product = Rule Product Category
-   If no dependent match is found, the system falls back to Subscriber rules, in this order:
    -   Coverage Contract Group Plan = Rule Contract Group Plan
    -   Coverage Product = Rule Product
    -   Coverage Parent Contract Group Plan = Rule Contract Group Plan
    -   Product associated with Coverage Parent Contract Group Plan = Rule Product
    -   Product Category of the above Product = Rule Product Category

Example: Contribution Rules and Priority Order

Let’s assume the following hierarchy:

-   Product Category: Dental
-   Plan: Dental Silver
-   Coverages: Preventive Care, Orthodontia

Contribution rules might be defined as follows:

-   Preventive Care coverage → Employer pays 20%
-   Dental Silver Plan → Employer pays 15%
-   Dental Category (all dental products) → Employer pays 10%

In this case:

-   If Preventive Care coverage is selected, the 20% coverage-level rule applies.
-   If no coverage-level rule exists for Surgery coverage under Dental Silver, the system looks at the plan level (Dental Silver = 15%).
-   If no plan-level rule exists for Dental Gold, the system falls back to the broader product category (Dental = 10%).

Did this article solve your issue?

Let us know so we can improve!

YesNo