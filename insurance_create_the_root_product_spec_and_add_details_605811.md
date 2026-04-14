---
title: "Create the Root Product Spec and Add Details"
source: "https://help.salesforce.com/s/articleView?id=ind.insurance_create_the_root_product_spec_and_add_details_605811.htm&language=en_US&type=5"
scraped: "2026-04-14"
filter: "ind.insurance_"
---# Create the Root Product Spec and Add Details

Create the Root Product Spec and Add Details[](https://help.salesforce.com/s?language=en_US)

You are here:

1.  [Salesforce Help](/s/?language=en_US)
2.  [Docs](/s/products?language=en_US)
3.  [Digital Insurance](https://help.salesforce.com/s/articleView?id=ind.insurance_admin_standard.htm&language=en_US&type=5)

# Create the Root Product Spec and Add Details

Create a new root product spec and add details to it.

1.  On the **Products** list page, click **New**.
2.  On the **New Product** window, under **Select a record type** choose **Product**.
3.  Enter information into the following fields:
    
    [](https://help.salesforce.com/s?language=en_US)
    
    -   **Product Name**: Required. Enter a descriptive name for this product.
        
        This product name will appear on UIs your users see.
        
    -   **Product Code**: Make this code short, descriptive, and unique so that other users can identify this product by reading this code.
        
        Tip
        
        A descriptive, easy-to-read, consistent product code naming convention will make it easier to identify your products.
        
        Vlocity Insurance uses product codes when you form expressions for rules.
        
    -   **Active**: Check Active if you want this product to be available in Vlocity.
        
        Tip
        
        You may want to hold off checking Active on root product specs until you've completed and tested them.
        
        You can come back to the Details tab of the root product spec and check Active after you've completed and tested it.
        
    -   **Status**: If you use a product approval process, such as all products must be reviewed and approved before they're activated, set a status here.
        
        Note
        
        Selecting **Active** in the **Status** field does NOT make it available for use in Vlocity. To make a product available, check the **Active** checkbox.
        
    -   **Effective Date**: The date this root product spec becomes effective/available to customers.
        
        SomeVlocity Insurance services use the effective date of the product.
        
    -   **Product Family**, **Line of Business**, **Type**, and **Sub Type**: Choose values for one or more of these options if your company uses these options to sort its product catalog.
        
        Leave one or more of these fields blank if this product doesn't fit into them, or your company doesn't use them.
        
        Most insurers that use this option have large product catalogs, and need Product Families to help them slice and dice their catalog to make it easier to find specific products.
        
        The [InsProductService:getRatedProducts](https://help.salesforce.com/s/articleView?id=ind.insurance_insproductservice__getratedproducts.htm&language=en_US&type=5 "Use this service to get an array of one or more products, priced using rating procedures attached to those products. This service also includes extra features such as tax and fee calculations, filtering, and performance optimization.") service can use any of these key/value pairs as filters.
        
    -   **Carrier**: Enter the name of the carrier within your organization that backs the type of policy that this product is a template for.
        
        Leave this field blank if you don't have different carriers for different types of insurance.
        
    -   **Parent Class**: Leave blank.
        
    -   **Term**: Set the term for this product. Vlocity uses the Term value in revenue scheduling for purchased policies.
        
    -   **Revenue Scheduling Enabled**: Select if revenue scheduling will be used for this product.
        
    -   **Custom Attribute Processes**: Leave blank for root products. This option is only used for Insured Items and Insured Parties.
        
    -   **Rating Procedure Name**: You can leave this blank when you're first creating a root product spec.
        
        Later, after you've created the rating procedure you'll used with this product, you can come back and enter its name here.
        
    -   **Rating Procedure Type**: You can leave this blank when you're first creating a root product spec.
        
        Later, after you've created the rating procedure you'll used with this product, you can come back and enter its type here.
        
    -   **Configurable**: Leave blank.
        
    -   **Product Description**: Add a description of this root product spec that'll help Vlocity users after you understand its purpose.
        
    
4.  Click **Save**.

Did this article solve your issue?

Let us know so we can improve!

YesNo