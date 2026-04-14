---
title: "Assign Attributes to Insurance Product Classifications"
source: "https://help.salesforce.com/s/articleView?id=ind.insurance_group_benefits_core_assign_attributes_to_product_classifications.htm&language=en_US&type=5"
scraped: "2026-04-14"
filter: "ind.insurance_"
---# Assign Attributes to Insurance Product Classifications

Assign Attributes to Insurance Product Classifications[](https://help.salesforce.com/s?language=en_US)

You are here:

1.  [Salesforce Help](/s/?language=en_US)
2.  [Docs](/s/products?language=en_US)
3.  [Digital Insurance](https://help.salesforce.com/s/articleView?id=ind.insurance_admin_standard.htm&language=en_US&type=5)

# Assign Attributes to Insurance Product Classifications

After you create a product classification, assign attributes to it. Attributes define the information you want to capture at runtime. For example, the Member product classification uses the Basic Information category and Contact information. Assigning attributes ensures that every product inheriting the classification automatically carries these characteristics.

### Required Editions

<table class="slds-table slds-table_bordered slds-m-bottom_small edition" lwc-3eigj2skqo3=""><colgroup lwc-3eigj2skqo3=""><col style="width:100%" lwc-3eigj2skqo3=""></colgroup><tbody lwc-3eigj2skqo3=""><tr class="" lwc-3eigj2skqo3=""><td style="vertical-align:top;" class="slds-cell-wrap" lwc-3eigj2skqo3="">Available in: Lightning Experience</td></tr><tr class="" lwc-3eigj2skqo3=""><td style="vertical-align:top;" class="slds-cell-wrap" lwc-3eigj2skqo3="">Available in: <strong class="uicontrol" lwc-3eigj2skqo3="">Professional</strong>, <strong class="uicontrol" lwc-3eigj2skqo3="">Enterprise</strong>, and<strong class="uicontrol" lwc-3eigj2skqo3=""> Unlimited</strong> Editions of Digital Insurance with Digital Insurance Product Admin Add On, Digital Insurance Group Benefits AddOn, Digital Insurance Group Enrollment AddOn,Digital Insurance Group Benefits Customer Community AddOn, and Digital Insurance Group Benefits Partner Community AddOn licenses</td></tr></tbody></table>

| User Permissions Needed |
| --- |
| To create group benefits product model | Product catalog management administrator |

Because every attribute in this model already belongs to an attribute category, assign attributes by category. This approach is faster and less error-prone than selecting attributes one by one.

1.  Select the product classification you want to update. For example, Member.
2.  Navigate to the Attributes tab.
3.  In the Attributes section, click **Assign**.
4.  Select Assign Attributes by category to assign a collection of attributes to the product classification.
5.  Click **Next**.
6.  For Member classification, assign these attribute categories:
    
    -   Basic Information: First Name, Last Name, Age, Gender, Marital Status, Smoker Status
    -   Contact Information: Email, State, City, Contact Number
    
7.  Click **Assign**.
8.  Save your changes.

The selected attributes are now associated with the product classification. Any product that inherits this classification automatically includes the attributes for configuration and rating.

Follow the same procedure to add these attributes:

| Product classification | attibute categories |
| --- | --- |
| Group Summary | 
-   Summary Reference Record
-   Summary Information

 |
| Coverage | 

-   In-Network Coverage Terms
-   Out-Network Coverage Terms

 |

Did this article solve your issue?

Let us know so we can improve!

YesNo