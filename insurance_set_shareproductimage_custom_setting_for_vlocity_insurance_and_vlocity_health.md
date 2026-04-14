---
title: "Set the ShareProductImage Custom Setting for Insurance"
source: "https://help.salesforce.com/s/articleView?id=ind.insurance_set_shareproductimage_custom_setting_for_vlocity_insurance_and_vlocity_health.htm&language=en_US&type=5"
scraped: "2026-04-14"
filter: "ind.insurance_"
---# Set the ShareProductImage Custom Setting for Insurance

Set the ShareProductImage Custom Setting for Insurance[](https://help.salesforce.com/s?language=en_US)

You are here:

1.  [Salesforce Help](/s/?language=en_US)
2.  [Docs](/s/products?language=en_US)
3.  [Digital Insurance](https://help.salesforce.com/s/articleView?id=ind.insurance_admin_standard.htm&language=en_US&type=5)

# Set the ShareProductImage Custom Setting for Insurance

You can turn on the ShareProductImage custom setting to support product image sharing.

1.  From **Setup**, in the **Quick Find** box, enter Custom Settings, and then select **Custom Settings**.
2.  Click **Manage** next to **Trigger Setup**.
3.  Click **Edit** next to **ContentDocumentLink.ShareProductImage**.
4.  Verify that the **Trigger On** checkbox is selected.
    
    If it isn't selected, select it and then click **Save**.
    
5.  [](https://help.salesforce.com/s?language=en_US)If the **ContentDocumentLink.ShareProductImage** trigger does not exist:
    1.  Click **New** on the **Trigger Setup** page.
    2.  For **Name**, enter ContentDocumentLink.ShareProductImage.
    3.  Select the **Trigger On** checkbox.
    4.  Save the trigger.

[](https://help.salesforce.com/s?language=en_US)

Head back to the manual post-upgrade steps and complete the next task in the list.

Did this article solve your issue?

Let us know so we can improve!

YesNo