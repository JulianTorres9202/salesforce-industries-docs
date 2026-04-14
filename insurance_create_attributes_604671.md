---
title: "Create Attributes"
source: "https://help.salesforce.com/s/articleView?id=ind.insurance_create_attributes_604671.htm&language=en_US&type=5"
scraped: "2026-04-14"
filter: "ind.insurance_"
---# Create Attributes

Create Attributes[](https://help.salesforce.com/s?language=en_US)

You are here:

1.  [Salesforce Help](/s/?language=en_US)
2.  [Docs](/s/products?language=en_US)
3.  [Digital Insurance](https://help.salesforce.com/s/articleView?id=ind.insurance_admin_standard.htm&language=en_US&type=5)

# Create Attributes

Product attributes define coverages, insured items, and other parts of insurance products and health plans. They correspond to anything that's important to quoting, rating, and writing an insurance policy.

Note

Looking to create a power attribute such as a limit, deductible, copay, coinsurance, or out-of-pocket max? See [Create Power Attributes](https://help.salesforce.com/s/articleView?id=ind.insurance_create_power_attributes_604759.htm&language=en_US&type=5 "Use power attributes to track limits, deductibles, copays, coinsurance, and out of pocket maximums. Create power attributes the same way you create regular attributes, in the same attribute categories, and then complete some extra configuration steps.").

1.  Go to the Vlocity Attribute Categories page.
2.  Click the name of the attribute category you want to add attributes to.
3.  On the bottom of the left pane, click **\+ Add New Attribute**.
4.  Enter a **Name** for this attribute.
5.  Enter a **Code** for this attribute.
    
    Make the code short but descriptive. This code appears in other places in Vlocity and it's useful to be able to read the code and understand the purpose of the attribute.
    
6.  Leave **Active** checked unless you want this attribute to be inactive.
7.  Leave **Filterable** checked to let services and templates use this attribute to filter insurance products and health plans for rating and display.
    
    If you deselect this option, this attribute won't be usable to filter plans. To learn more about how Vlocity uses filterable attributes, see [Attribute Filtering](https://help.salesforce.com/s/articleView?id=ind.insurance_attribute_filtering_604731.htm&language=en_US&type=5 "When you create an attribute, you select whether or not it is filterable. This choice impacts how the attribute can be found and used by other parts of Vlocity.").
    
8.  Leave **Configurable** checked to let users configure the attribute when and where it's time to use it.
9.  Enter a **Display Sequence** to specify where this attribute will appear in lists of attributes displayed.
    
    To learn how Vlocity uses display sequence numbers for attributes and attribute categories, see [Attribute Sequencing](https://help.salesforce.com/s/articleView?id=ind.insurance_attribute_sequencing_604739.htm&language=en_US&type=5 "You add Display Sequence numbers to both attribute categories and attributes. Vlocity uses these sequence numbers to order the display attribute categories and attributes. Vlocity displays the first attribute category starting with the lowest display sequence number, then all the attributes in the first attribute category. Then it displays the second attribute category in the sequence, with all its attributes.").
    
    Each attribute within one attribute category must have a unique **Display Sequence** number.
    
10.  Select an **Attribute Group Type** for this attribute, if this attribute will be used for group insurance products such as health, dental, vision, or group life.
     
     To learn more about attribute groups, see [Attribute Grouping](https://help.salesforce.com/s/articleView?id=ind.insurance_attribute_grouping_604747.htm&language=en_US&type=5 "Group Types are used for attributes that become part of group insurance products.").
     
11.  Click **Save**.
     
     The following settings and actions don't apply to product attributes, so you can leave them alone:
     
     -   **Cloneable**
         
     -   **Private**
         
     -   **Add New Assignment Rule**
         
     
     Tip
     
     Prevent APEX CPU timeout errors from occurring when you update or delete attributes on a coverage spec that's shared across several products. Add PushAttributeInBatchMode to the **Insurance Configuration Setup** custom setting and define it as true. See [Attribute Updates in Batch Mode](https://help.salesforce.com/s/articleView?id=ind.insurance_attribute_updates_in_batch.htm&language=en_US&type=5 "Prevent APEX CPU timeout errors from occurring when you update or delete attributes on a coverage spec that's shared across several products. Add PushAttributeInBatchMode to the Insurance Configuration Setup custom setting and define it as true.").
     

-   **[Attribute Filtering](https://help.salesforce.com/s/articleView?id=ind.insurance_attribute_filtering_604731.htm&language=en_US&type=5)**  
    When you create an attribute, you select whether or not it is filterable. This choice impacts how the attribute can be found and used by other parts of Vlocity.
-   **[Attribute Sequencing](https://help.salesforce.com/s/articleView?id=ind.insurance_attribute_sequencing_604739.htm&language=en_US&type=5)**  
    You add Display Sequence numbers to both attribute categories and attributes. Vlocity uses these sequence numbers to order the display attribute categories and attributes. Vlocity displays the first attribute category starting with the lowest display sequence number, then all the attributes in the first attribute category. Then it displays the second attribute category in the sequence, with all its attributes.
-   **[Attribute Grouping](https://help.salesforce.com/s/articleView?id=ind.insurance_attribute_grouping_604747.htm&language=en_US&type=5)**  
    Group Types are used for attributes that become part of group insurance products.
-   **[Attribute Updates in Batch Mode](https://help.salesforce.com/s/articleView?id=ind.insurance_attribute_updates_in_batch.htm&language=en_US&type=5)**  
    Prevent APEX CPU timeout errors from occurring when you update or delete attributes on a coverage spec that's shared across several products. Add PushAttributeInBatchMode to the **Insurance Configuration Setup** custom setting and define it as true.

Did this article solve your issue?

Let us know so we can improve!

YesNo