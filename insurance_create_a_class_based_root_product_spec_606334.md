---
title: "Create a Class-Based Root Product Spec"
source: "https://help.salesforce.com/s/articleView?id=ind.insurance_create_a_class_based_root_product_spec_606334.htm&language=en_US&type=5"
scraped: "2026-04-14"
filter: "ind.insurance_"
---# Create a Class-Based Root Product Spec

Create a Class-Based Root Product Spec[](https://help.salesforce.com/s?language=en_US)

You are here:

1.  [Salesforce Help](/s/?language=en_US)
2.  [Docs](/s/products?language=en_US)
3.  [Digital Insurance](https://help.salesforce.com/s/articleView?id=ind.insurance_admin_standard.htm&language=en_US&type=5)

# Create a Class-Based Root Product Spec

To create a product model based on a product class, first create the initial product class-based root product spec.

A root product spec based on a product class shows coverages, insured items, insured parties, and rating facts inherited from the class with a gray box icon next to the name of the item.

1.  Start following the steps in [Create the Root Product Spec and Add Details](https://help.salesforce.com/s/articleView?id=ind.insurance_create_the_root_product_spec_and_add_details_605811.htm&language=en_US&type=5 "Create a new root product spec and add details to it.").
2.  In step 3, in the Parent Class field, choose the product class you want to base this product model on.
3.  Fill out the rest of the details you need for this root product spec. Except for the **Rating Procedure Name** and **Rating Procedure Type**, product details do not pass from the product class to root product specs.
    
    Tip
    
    Skip the **Rating Procedure Name** and **Rating Procedure Type** if you want this root product model to inherit these things from the product class.
    
4.  Click **Save**.
    
    The root product spec appears. It contains coverages, insured items, insured parties, rating facts, root product attributes, and rules.
    
5.  To customize this product, make changes to any of the parts of the root product spec that were inherited from the product class. See [Make Changes to Inherited Parts of the Root Product Spec](https://help.salesforce.com/s/articleView?id=ind.insurance_make_changes_to_inherited_parts_of_the_root_product_spec_606371.htm&language=en_US&type=5 "After you create a product class-based root product spec, you can make some changes to the parts that are inherited from the product class. But some inherited things can't be changed on the root product spec.").
6.  (Optional) Add taxes and fees to the root product spec. See [Add Taxes and Fees to the Root Product Spec](https://help.salesforce.com/s/articleView?id=ind.insurance_add_taxes_and_fees_to_the_root_product_spec_606124.htm&language=en_US&type=5 "To apply taxes and fees to insurance product premiums, you can attach them to root products.").
7.  Add a price book entry for this product. See [Add a Price Book Entry](https://help.salesforce.com/s/articleView?id=ind.insurance_add_a_price_book_entry_606216.htm&language=en_US&type=5 "After you create a product, add it to a price book.").
8.  Set up the product simulator on the Simulate tab. See [Set Up the Product Rating Simulator](https://help.salesforce.com/s/articleView?id=ind.insurance_set_up_the_product_rating_simulator_606240.htm&language=en_US&type=5 "To set up a product rating simulator, complete an analysis, set up a rating procedure, and then map the rating procedure to the product model.").

Did this article solve your issue?

Let us know so we can improve!

YesNo