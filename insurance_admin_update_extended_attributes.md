---
title: "Update Existing Extended Attribute Definitions"
source: "https://help.salesforce.com/s/articleView?id=ind.insurance_admin_update_extended_attributes.htm&language=en_US&type=5"
scraped: "2026-04-13"
filter: "ind.insurance_"
---# Update Existing Extended Attribute Definitions

Update Existing Extended Attribute Definitions[](https://help.salesforce.com/s?language=en_US)

You are here:

1.  [Salesforce Help](/s/?language=en_US)
2.  [Docs](/s/products?language=en_US)
3.  [Digital Insurance](https://help.salesforce.com/s/articleView?id=ind.insurance_admin_standard.htm&language=en_US&type=5)

# Update Existing Extended Attribute Definitions

Prior to the Summer '25 release, AttributeNameOverride was used to look for an object in the record picker. If you have extended attribute definitions created prior to that release, check them to be sure the Code field of the attribute definition is set to the object's API name.

1.  Find the existing attribute definition for all the existing extended attributes, such as Asset Record Name or Contact Record Name.
2.  Update the **Code** field (1) to the referred object’s API name, for example Asset.

Example[](https://help.salesforce.com/s?language=en_US)

Be sure to test your change using the configurator.

Did this article solve your issue?

Let us know so we can improve!

YesNo