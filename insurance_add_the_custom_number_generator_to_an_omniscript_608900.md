---
title: "Add the Custom Number Generator to an OmniScript"
source: "https://help.salesforce.com/s/articleView?id=ind.insurance_add_the_custom_number_generator_to_an_omniscript_608900.htm&language=en_US&type=5"
scraped: "2026-04-13"
filter: "ind.insurance_"
---# Add the Custom Number Generator to an OmniScript

Add the Custom Number Generator to an OmniScript[](https://help.salesforce.com/s?language=en_US)

You are here:

1.  [Salesforce Help](/s/?language=en_US)
2.  [Docs](/s/products?language=en_US)
3.  [Digital Insurance](https://help.salesforce.com/s/articleView?id=ind.insurance_admin_standard.htm&language=en_US&type=5)

# Add the Custom Number Generator to an OmniScript

Use an OmniScript to add the custom policy numbering to your policy creation experience.

1.  Drag a Remote Action onto the Structure panel.
2.  In Remote Class, enter UniqueIdGeneratorService.
3.  In Remote Method, enter generateUniqueId.
4.  Under Remote Options, click **Add New Key/Value Pair**.
5.  In the first field, enter ObjectId.
6.  In the second field, enter the ID for the object type you selected in step 7 of the task above.
    
    For example, for policy numbers, enter %assetId%.
    
7.  Add another key/value pair as follows:
    
    -   First field: ObjectSetting
        
    -   Second field: Account
        
    

[](https://help.salesforce.com/s?language=en_US)

[](https://help.salesforce.com/s?language=en_US)The OmniScript can now generate numbers as you specified anytime a user steps through it.

Did this article solve your issue?

Let us know so we can improve!

YesNo