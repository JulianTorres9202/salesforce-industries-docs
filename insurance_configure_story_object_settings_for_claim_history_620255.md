---
title: "Configure Story Object Settings for Claim History"
source: "https://help.salesforce.com/s/articleView?id=ind.insurance_configure_story_object_settings_for_claim_history_620255.htm&language=en_US&type=5"
scraped: "2026-04-14"
filter: "ind.insurance_"
---# Configure Story Object Settings for Claim History

Configure Story Object Settings for Claim History[](https://help.salesforce.com/s?language=en_US)

You are here:

1.  [Salesforce Help](/s/?language=en_US)
2.  [Docs](/s/products?language=en_US)
3.  [Digital Insurance](https://help.salesforce.com/s/articleView?id=ind.insurance_admin_standard.htm&language=en_US&type=5)

# Configure Story Object Settings for Claim History

Before you use Claim History, configure story object settings. Make sure each setting uses the correct **Parent Object Name** (Claim) and **Story Object Lookup Field** (vlocity\_ins\_fsc\_\_ClaimId\_\_c).

1.  [](https://help.salesforce.com/s?language=en_US)From Setup, in the Quick Find box, enter Custom Settings, and then select **Custom Settings**.
2.  [](https://help.salesforce.com/s?language=en_US)Find **Story Object Configuration**, and then click **Manage** next to it.
3.  [](https://help.salesforce.com/s?language=en_US)Find and select a setting used for Claim History. For example, find **Claim\_TrackingEntry**, and then click **Edit** next to it.
4.  For **Parent Object Name**, enter Claim.
5.  [](https://help.salesforce.com/s?language=en_US)For **Story Object Lookup Field**, enter vlocity\_ins\_fsc\_\_ClaimId\_\_c.
6.  Click **Save**.

Did this article solve your issue?

Let us know so we can improve!

YesNo