---
title: "Add a Configurable Value to an Attribute on a Child Spec"
source: "https://help.salesforce.com/s/articleView?id=ind.insurance_add_a_configurable_value_to_an_attribute_on_a_child_spec_605442.htm&language=en_US&type=5"
scraped: "2026-04-13"
filter: "ind.insurance_"
---# Add a Configurable Value to an Attribute on a Child Spec

Add a Configurable Value to an Attribute on a Child Spec[](https://help.salesforce.com/s?language=en_US)

You are here:

1.  [Salesforce Help](/s/?language=en_US)
2.  [Docs](/s/products?language=en_US)
3.  [Digital Insurance](https://help.salesforce.com/s/articleView?id=ind.insurance_admin_standard.htm&language=en_US&type=5)

# Add a Configurable Value to an Attribute on a Child Spec

A configurable attribute value gives users the flexibility to enter or select a value.

Before You Begin

Add the attribute to the child spec. See [Add Attributes to a Child Spec](https://help.salesforce.com/s/articleView?id=ind.insurance_add_attributes_to_a_child_spec_605346.htm&language=en_US&type=5 "Most child specs include at least one attribute. When you add attributes to a child spec, you also configure them with controls and values.").

1.  Select the attribute and select **Is Configurable**.
2.  Select a **Value Data Type**.
3.  Depending on the **Value Data Type** you selected, choose an additional control (or not).
    
    | 
    Value Data Type
    
     | 
    
    Controls
    
     |
    | --- | --- |
    | 
    
    Currency
    
     | 
    
    **Dropdown** lets users choose from preset amounts.
    
    -   Enter a **Display Value** that your users will see and be able to select. Often this value will have a currency symbol before it. For example, $500.
        
    -   Enter a **Value** that Vlocity will use. This usually doesn't have a currency symbol. For example, 500.
        
    
    **Single Value** lets users enter any amount. Enter a default value or leave it blank.
    
     |
    | 
    
    Percentage
    
     | 
    
    **Single Value** lets users enter any amount. Enter a default value or leave it blank.
    
    **Slider** lets users choose a percentage.
    
    -   Replace **Enter Min** and **Enter Max** with the minimum and maximum values for the slider.
        
    -   Replace **Start Value** with the value you want the slider to be set to by default.
        
    -   [](https://help.salesforce.com/s?language=en_US)
        
        Replace **Enter Step** with a number that is the increment you want the equalizer to step by.
        
    
     |
    | 
    
    Text
    
     | 
    
    **Text** lets users enter a few words. **Text Area** lets users enter a longer chunk of text.
    
    Enter default text in the **Value** field or leave it blank.
    
     |
    | 
    
    Number
    
     | 
    
    [](https://help.salesforce.com/s?language=en_US)**Single Value** lets users enter any numeric value. Enter a default value or leave it blank.
    
    **Slider** lets users choose from a range of numbers.
    
    [](https://help.salesforce.com/s?language=en_US)
    
    -   Replace **Enter Min** and **Enter Max** with the minimum and maximum values for the slider.
        
    -   Replace **Start Value** with the value you want the slider to be set to by default.
        
    
     |
    | 
    
    Checkbox
    
     | 
    
    Lets users select or deselect this attribute.
    
    Select the checkbox to default it to selected when end-users see it. Users will be able to deselect the checkbox when they interact with the spec.
    
     |
    | 
    
    Datetime
    
     | 
    
    Lets users enter a date and time.
    
     |
    | 
    
    Date
    
     | 
    
    Lets users enter a date.
    
     |
    | 
    
    Adjustment
    
     | 
    
    Select a second control in the right-side control field that appears.
    
    For **Single Value**, enter a value in the **Value** field or leave it blank.
    
    [](https://help.salesforce.com/s?language=en_US)**Slider** lets customers choose an adjustment amount.
    
    [](https://help.salesforce.com/s?language=en_US)
    
    -   Replace **Enter Min** and **Enter Max** with the minimum and maximum values for the slider.
        
    -   Replace **Start Value** with the value you want the slider to be set to by default.
        
    
    **Equalizer** defines a numerical amount above or below an initial value.
    
    -   Replace **Enter Variant** with a number one can increase or decrease the initial value by. For example, an underwriter can deviate from the initial value by this amount.
        
    -   Replace **Enter Step** with a number that is the increment you want the equalizer to step by. For example, this is the increment by which the underwriter can change the value.
        
    -   In **Units**, select **Percentage** or **Currency**.
        
    -   In **Adjustment Comments**, select **Required**, **Optional**, or **Not Used**.
        
    
     |
    | 
    
    Picklist
    
     | 
    
    **Radiobutton** lets users choose one item from a list of radio buttons. **Dropdown** lets users choose one item from a dropdown list. For either one:
    
    [](https://help.salesforce.com/s?language=en_US)
    
    -   Enter a **Display Value** that your users will see and be able to select. Often this value will have a currency symbol before it. For example, $500.
        
    -   Enter a **Value** that Vlocity will use. This usually doesn't have a currency symbol. For example, 500.
        
    
     |
    | 
    
    Multi Picklist
    
     | 
    
    **Checkbox** lets users choose multiple items from a list of checkboxes. **Dropdown** lets users choose multiple items from a dropdown list. For either one:
    
    [](https://help.salesforce.com/s?language=en_US)
    
    -   Enter a **Display Value** that your users will see and be able to select. Often this value will have a currency symbol before it. For example, $500.
        
    -   Enter a **Value** that Vlocity will use. This usually doesn't have a currency symbol. For example, 500.
        
    
     |
    | 
    
    Multivalue Picklist
    
     | 
    
    [](https://help.salesforce.com/s?language=en_US)Lets you input two or more attribute values for one attribute, split by a divider character (such as / or #). You can enter multiple values for users to choose from.
    
    [](https://help.salesforce.com/s?language=en_US)In **Value Decoder**, enter the meaning of each attribute value and the divider character. For example, the Value Decoder for an auto liability attribute can be perPerson/totalLimit/perAccident.
    
    [](https://help.salesforce.com/s?language=en_US)Note
    
    We recommend you don't use spaces in the Value Decoder.
    
    If you use spaces in the Value Decoder, you'll need to add `var:"` to wrap them if you use them in rules.
    
    As a best practice, enter a **Display Value** that mirrors the format of the Value Decoder and uses the same divider character. For example, if your Value Decoder is perPerson/totalLimit/perAccident, one Display Value can be $100K/$300K/$50K.
    
    For **Value**, enter a value that Vlocity will use as data. This value must follow the same format as the Value Decoder. For example, if your Value Decoder is perPerson/totalLimit/perAccident, one value can be 100000/300000/50000.
    
     |
    

Did this article solve your issue?

Let us know so we can improve!

YesNo