---
title: "Set Up Group Benefits Product Model"
source: "https://help.salesforce.com/s/articleView?id=ind.insurance_group_benefits_core_product_modelling.htm&language=en_US&type=5"
scraped: "2026-04-14"
filter: "ind.insurance_"
---# Set Up Group Benefits Product Model

Set Up Group Benefits Product Model[](https://help.salesforce.com/s?language=en_US)

You are here:

1.  [Salesforce Help](/s/?language=en_US)
2.  [Docs](/s/products?language=en_US)
3.  [Digital Insurance](https://help.salesforce.com/s/articleView?id=ind.insurance_admin_standard.htm&language=en_US&type=5)

# Set Up Group Benefits Product Model

Model group insurance products like Medical Platinum with group classes, census members, and coverages in a reusable hierarchy. This flexible structure supports different group benefit plans and keeps quoting, rating, and enrollment consistent. It also helps insurers deliver accurate group quotes and provide members with a smoother plan selection experience.

### Required Editions

<table class="slds-table slds-table_bordered slds-m-bottom_small edition" lwc-3eigj2skqo3=""><colgroup lwc-3eigj2skqo3=""><col style="width:100%" lwc-3eigj2skqo3=""></colgroup><tbody lwc-3eigj2skqo3=""><tr class="" lwc-3eigj2skqo3=""><td style="vertical-align:top;" class="slds-cell-wrap" lwc-3eigj2skqo3="">Available in: Lightning Experience</td></tr><tr class="" lwc-3eigj2skqo3=""><td style="vertical-align:top;" class="slds-cell-wrap" lwc-3eigj2skqo3="">Available in: <strong class="uicontrol" lwc-3eigj2skqo3="">Professional</strong>, <strong class="uicontrol" lwc-3eigj2skqo3="">Enterprise</strong>, and<strong class="uicontrol" lwc-3eigj2skqo3=""> Unlimited</strong> Editions of Digital Insurance with Digital Insurance Product Admin Add On, Digital Insurance Group Benefits AddOn, Digital Insurance Group Enrollment AddOn,Digital Insurance Group Benefits Customer Community AddOn, and Digital Insurance Group Benefits Partner Community AddOn licenses</td></tr></tbody></table>

This guide walks through building a sample group insurance product called Medical Platinum. The model includes:

-   Group Classes: Executives, Managers, Associates
-   Census Members: Employees and dependents
-   Group Coverages: Preventive Care, Surgery, Critical Illness

By the end, you’ll have a complete product hierarchy that can be used in group quoting and rating.

To get the most out of Salesforce Insurance it helps to have a good understanding of Product Catalog Management, Pricing, Product Discovery, and Attribute Management. These concepts form the foundation for modeling group benefits products.

Key Objects in Group Product Modeling

-   Product – Represents sellable insurance plans or components. A product can be a simple plan (no hierarchy) or a bundled product, such as a group health plan with multiple coverages.
-   Product Component Group – Groups related components inside a bundle. For example, the Coverages group holds all coverage products under a member product.
-   Product Classification – Provides a template for creating similar products that share attributes. For example, the Member classification includes attributes such as Age, Gender, and Smoker Status.
-   Attribute – Defines product characteristics. For example, Deductible, Copay, and Coinsurance for coverages, or Age and Gender for members.
-   Hierarchy – Represents the product structure. For example:

What’s Next

The rest of this guide takes you step by step through building the Medical Platinum product model. You’ll:

-   Create attributes and categories to capture product details.
-   Define product classifications as reusable templates.
-   Build products and connect them in a bundle hierarchy.
-   Associate attributes with products and classifications.
-   Configure extended attributes to pull values from census and summary objects.
-   Organize products into catalogs and categories for plan selection.
-   Set up pricing and selling models to support quoting and rating.

-   **[Product Specification Hierarchy for Group Benefits](https://help.salesforce.com/s/articleView?id=ind.insurance_group_benefits_core_product_spec_overview.htm&language=en_US&type=5)**  
    The product model for group benefits is built on a clear hierarchy where each layer serves a distinct purpose. The following table summarizes the role of each product spec, the type used, common attributes, and examples you’ll work with in the Medical Platinum model.
-   **[Attribute Management for Group Benefits](https://help.salesforce.com/s/articleView?id=ind.insurance_group_benefits_core_attribute_management.htm&language=en_US&type=5)**  
    Attributes define the details of your group benefit products, such as age for members or deductible for coverages. Building attributes is a step-by-step process: first define reusable picklists, then create attributes, and finally organize them into categories. This approach keeps your model structured and reusable across products.
-   **[Manage Classifications and Products for Group Benefits](https://help.salesforce.com/s/articleView?id=ind.insurance_group_benefits_core_cover_manage_products.htm&language=en_US&type=5)**  
    Product classifications and products define the structure of your group insurance model. A classification acts as a template to group attributes and make them reusable across products. Products represent the actual insurance plans and components that are bundled into your hierarchy. Together, they form the foundation of the group benefits product model.
-   **[Set Up Group Benefits Product Category and Catalog](https://help.salesforce.com/s/articleView?id=ind.insurance_group_benefits_core_product_category_and_catalog.htm&language=en_US&type=5)**  
    A catalog organizes all of your group insurance offerings into a single structure, while categories group products into meaningful sections (for example, Medical or Dental). In Group Benefits, catalogs and categories control how products are displayed during quoting and plan selection.

Did this article solve your issue?

Let us know so we can improve!

YesNo