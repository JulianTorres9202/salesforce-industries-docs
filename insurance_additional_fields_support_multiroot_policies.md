---
title: "Support for Additional Fields"
source: "https://help.salesforce.com/s/articleView?id=ind.insurance_additional_fields_support_multiroot_policies.htm&language=en_US&type=5"
scraped: "2026-04-13"
filter: "ind.insurance_"
---# Support for Additional Fields

Support for Additional Fields[](https://help.salesforce.com/s?language=en_US)

You are here:

1.  [Salesforce Help](/s/?language=en_US)
2.  [Docs](/s/products?language=en_US)
3.  [Digital Insurance](https://help.salesforce.com/s/articleView?id=ind.insurance_admin_standard.htm&language=en_US&type=5)

# Support for Additional Fields

Use the additional fields option to include custom fields or override Quote fields in both parent and child multiroot policies.

[](https://help.salesforce.com/s?language=en_US)

-   You can include additional fields as an option in the `InsPolicyService.createMultiRootPolicy` and `InsPolicyService.createMultiRootPolicyVersion` services.
    
-   You can use ‌the `additionalFields` option to add fields that aren’t part of the Quote object, including custom fields or Quote fields that you want to override.
    
-   Additional fields are supported for both parent and child policies at the root policy level.
    
-   The `additionalFields` option updates fields only at the Insurance Policy object level.
    
-   The parent multiroot policy uses the MULTI\_ROOT\_PARENT\_POLICY as an identifier in the `additionalFields` JSON structure.
    
-   The child policy uses the product code as an identifier for the product in the `additionalFields` JSON structure.
    

Did this article solve your issue?

Let us know so we can improve!

YesNo