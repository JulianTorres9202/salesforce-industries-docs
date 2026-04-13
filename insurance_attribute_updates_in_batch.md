---
title: "Attribute Updates in Batch Mode"
source: "https://help.salesforce.com/s/articleView?id=ind.insurance_attribute_updates_in_batch.htm&language=en_US&type=5"
scraped: "2026-04-13"
filter: "ind.insurance_"
---# Attribute Updates in Batch Mode

Attribute Updates in Batch Mode[](https://help.salesforce.com/s?language=en_US)

You are here:

1.  [Salesforce Help](/s/?language=en_US)
2.  [Docs](/s/products?language=en_US)
3.  [Digital Insurance](https://help.salesforce.com/s/articleView?id=ind.insurance_admin_standard.htm&language=en_US&type=5)

# Attribute Updates in Batch Mode

Prevent APEX CPU timeout errors from occurring when you update or delete attributes on a coverage spec that's shared across several products. Add PushAttributeInBatchMode to the **Insurance Configuration Setup** custom setting and define it as true.

This setting is available in Spring '23 and later.

1.  From Setup, enter Custom Settings in the Quick Find box, then select **Custom Settings**.
2.  Next to **Insurance Configuration Setup**, click **Manage**.
3.  Click **New**.
4.  For **Name**, enter PushAttributeInBatchMode. For **Setup Value**, enter true.
5.  Click **Save**.

Did this article solve your issue?

Let us know so we can improve!

YesNo