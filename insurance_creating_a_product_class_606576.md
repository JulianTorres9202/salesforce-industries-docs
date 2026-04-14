---
title: "Create a Product Class"
source: "https://help.salesforce.com/s/articleView?id=ind.insurance_creating_a_product_class_606576.htm&language=en_US&type=5"
scraped: "2026-04-14"
filter: "ind.insurance_"
---# Create a Product Class

Create a Product Class[](https://help.salesforce.com/s?language=en_US)

You are here:

1.  [Salesforce Help](/s/?language=en_US)
2.  [Docs](/s/products?language=en_US)
3.  [Digital Insurance](https://help.salesforce.com/s/articleView?id=ind.insurance_admin_standard.htm&language=en_US&type=5)

# Create a Product Class

Create a product class to use as a template for product models.

If you haven't built a product model yet, complete these prerequisites.

-   Create attribute categories and product attributes.
-   Create child specs.
-   Create insured item specs.
-   Create insured party specs.
-   Create rating fact specs.
-   Add rules to attributes and attribute values on child specs as needed.

1.  On the Products list page, click **New**.
2.  In the New Product window, choose **Class**.
3.  Enter class information.
    
    <table class="slds-table slds-table_bordered slds-m-bottom_small" lwc-3eigj2skqo3=""><colgroup lwc-3eigj2skqo3=""><col style="width:50%" lwc-3eigj2skqo3=""><col style="width:50%" lwc-3eigj2skqo3=""></colgroup><tbody lwc-3eigj2skqo3=""><tr class="" lwc-3eigj2skqo3=""><td style="vertical-align:top;" class="slds-cell-wrap" lwc-3eigj2skqo3=""><strong class="uicontrol" lwc-3eigj2skqo3="">Product Name</strong></td><td style="vertical-align:top;" class="slds-cell-wrap" lwc-3eigj2skqo3="">Required. Enter a descriptive name for this product class.</td></tr><tr class="" lwc-3eigj2skqo3=""><td style="vertical-align:top;" class="slds-cell-wrap" lwc-3eigj2skqo3=""><strong class="uicontrol" lwc-3eigj2skqo3="">Product Code</strong></td><td style="vertical-align:top;" class="slds-cell-wrap" lwc-3eigj2skqo3="">Enter a short, descriptive, unique identifier. A consistent product class code naming convention makes it easier to identify your products.</td></tr><tr class="" lwc-3eigj2skqo3=""><td style="vertical-align:top;" class="slds-cell-wrap" lwc-3eigj2skqo3=""><strong class="uicontrol" lwc-3eigj2skqo3="">Active</strong></td><td style="vertical-align:top;" class="slds-cell-wrap" lwc-3eigj2skqo3="">Select Active to make this product class available to users.</td></tr><tr class="" lwc-3eigj2skqo3=""><td style="vertical-align:top;" class="slds-cell-wrap" lwc-3eigj2skqo3=""><strong class="uicontrol" lwc-3eigj2skqo3="">Status</strong></td><td style="vertical-align:top;" class="slds-cell-wrap" lwc-3eigj2skqo3=""><p lwc-3eigj2skqo3="">If you use a process flow that checks the status of products, enter a status. For example, enter a status if you use a flow that validates that a product is reviewed and approved before it's activated.</p><p style="margin-bottom:0;" lwc-3eigj2skqo3="">Selecting Active in the Status field doesn't make a product class available to users. To make a product class available, select the Active checkbox.</p></td></tr><tr class="" lwc-3eigj2skqo3=""><td style="vertical-align:top;" class="slds-cell-wrap" lwc-3eigj2skqo3=""><strong class="uicontrol" lwc-3eigj2skqo3="">Effective Date</strong></td><td style="vertical-align:top;" class="slds-cell-wrap" lwc-3eigj2skqo3="">Enter an effective date when the product class becomes active.</td></tr><tr class="" lwc-3eigj2skqo3=""><td style="vertical-align:top;" class="slds-cell-wrap" lwc-3eigj2skqo3=""><strong class="uicontrol" lwc-3eigj2skqo3="">Parent Class</strong>, <strong class="uicontrol" lwc-3eigj2skqo3="">Parent Class Code</strong></td><td style="vertical-align:top;" class="slds-cell-wrap" lwc-3eigj2skqo3="">Leave blank.</td></tr><tr class="" lwc-3eigj2skqo3=""><td style="vertical-align:top;" class="slds-cell-wrap" lwc-3eigj2skqo3=""><strong class="uicontrol" lwc-3eigj2skqo3="">Rating Procedure Name</strong></td><td style="vertical-align:top;" class="slds-cell-wrap" lwc-3eigj2skqo3="">The name of the expression set, calculation procedure, or integration procedure that's used to rate product models based on this product class.</td></tr><tr class="" lwc-3eigj2skqo3=""><td style="vertical-align:top;" class="slds-cell-wrap" lwc-3eigj2skqo3=""><strong class="uicontrol" lwc-3eigj2skqo3="">Rating Procedure Type</strong></td><td style="vertical-align:top;" class="slds-cell-wrap" lwc-3eigj2skqo3="">Select the type of procedure used to rate product models based on this product class.</td></tr></tbody></table>
    
    The rest of the fields are optional. Information in these fields isn't inherited by the product models you create based on the product class.
    
4.  On the Coverages tab, add coverage specs to the product class.
    
    To edit attributes for coverages, insured items, insured parties, and rating facts, open the related child spec and make your changes.
    
5.  On the coverages marked **Optional**, add optional coverage rules as needed.
6.  On the **Insured Items** tab, add insured items and insured parties.
7.  On the **Rating Facts** tab, add rating facts.
8.  On the **Attributes** tab, add attributes that apply to the entire product class.
9.  Add Attribute Rules and Attribute Value Rules to the product-level attributes you added in the previous step.
10.  On the **Rules** tab, enter eligibility rules and underwriting (workflow) rules.
11.  Click **Save**.

SEE ALSO

[Product Attributes in Product Specs](https://help.salesforce.com/s/articleView?id=ind.insurance_product_attributes_in_product_specs.htm&language=en_US&type=5 "Product attributes are key pieces of the whole Vlocity Insurance and Vlocity Health platform. They define coverages, insured items, and other parts of insurance products and health plans. They correspond to anything that's important to quoting, rating, and writing an insurance policy. Attributes include inputs to rating (pricing), and characteristics that define claims.")

[Child Specs for Root Products](https://help.salesforce.com/s/articleView?id=ind.insurance_child_specs_for_root_products.htm&language=en_US&type=5 "Child specs are key building blocks for your product models. They're components of the root product specs that Insurance rates, quotes, sells, and administers for your customers.")

[Attribute Rules](https://help.salesforce.com/s/articleView?id=ind.insurance_attribute_rules_607965.htm&language=en_US&type=5 "Show users and customers exactly the right product attributes and attribute values for the insurance products that you quote, sell, and service.")

[Create Attribute Value Rules](https://help.salesforce.com/s/articleView?id=ind.insurance_create_attribute_value_rules_608112.htm&language=en_US&type=5 "Use Attribute Value Rules to determine if and when an attribute value is visible to users.")

[Optional Coverage Rules](https://help.salesforce.com/s/articleView?id=ind.insurance_optional_coverage_rules.htm&language=en_US&type=5 "Several types of rules apply to optional coverages on Insurance and Health products. Set rules up based on eligibility for optional coverage, whether optional coverages are required or selected by default, and valid combinations of optional coverages.")

Did this article solve your issue?

Let us know so we can improve!

YesNo