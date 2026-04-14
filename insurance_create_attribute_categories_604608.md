---
title: "Create Attribute Categories"
source: "https://help.salesforce.com/s/articleView?id=ind.insurance_create_attribute_categories_604608.htm&language=en_US&type=5"
scraped: "2026-04-14"
filter: "ind.insurance_"
---# Create Attribute Categories

Create Attribute Categories[](https://help.salesforce.com/s?language=en_US)

You are here:

1.  [Salesforce Help](/s/?language=en_US)
2.  [Docs](/s/products?language=en_US)
3.  [Digital Insurance](https://help.salesforce.com/s/articleView?id=ind.insurance_admin_standard.htm&language=en_US&type=5)

# Create Attribute Categories

Attribute categories make it easy for users to find and use the right attributes when they create product specs.

Before You Begin

Create a plan. Organize your attributes into logical groupings and use those as attribute categories.

1.  Go to the Vlocity Attributes Designer page.
2.  Click **New**.
3.  Enter a **Name** for your attribute category.
4.  Enter a **Display Sequence** number.
    
    The lower the **Display Sequence** number, the higher up it will display in the Vlocity UI. To learn how Vlocity uses display sequence numbers for attributes and attribute categories, see Attribute Sequencing.
    
    Each attribute category must have a unique **Display Sequence** number.
    
5.  Enter a **Code** that describes this attribute category.
    
    Make the code unique and descriptive, so other users can understand the attribute category when reading its code in other places in Vlocity.
    
6.  Leave the **Active** option checked.
7.  For **Applicable Sub-Type**, choose **Product Attribute**.
    
    Important
    
    You must choose **Product Attribute** in this field if you want this attribute to show up when you're creating insurance products. It defaults to **Profile Attribute** so you must choose **Product Attribute** manually.
    
    The following settings don't apply to product attribute categories, so you can leave them alone: 
    
    -   **UI Control Type**: Leave the default setting.
        
    -   **Applicable Type**: Leave the default setting.
        
    -   **Color Code**: Leave blank.
        
    -   **User Attributes Created Private**: Leave blank.
        
    

Did this article solve your issue?

Let us know so we can improve!

YesNo