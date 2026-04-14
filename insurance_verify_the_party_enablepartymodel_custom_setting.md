---
title: "Verify the Party.EnablePartyModel Custom Setting"
source: "https://help.salesforce.com/s/articleView?id=ind.insurance_verify_the_party_enablepartymodel_custom_setting.htm&language=en_US&type=5"
scraped: "2026-04-14"
filter: "ind.insurance_"
---# Verify the Party.EnablePartyModel Custom Setting

Verify the Party.EnablePartyModel Custom Setting[](https://help.salesforce.com/s?language=en_US)

You are here:

1.  [Salesforce Help](/s/?language=en_US)
2.  [Docs](/s/products?language=en_US)
3.  [Digital Insurance](https://help.salesforce.com/s/articleView?id=ind.insurance_admin_standard.htm&language=en_US&type=5)

# Verify the Party.EnablePartyModel Custom Setting

Before you upgrade managed packages, make sure the Party.EnablePartyModel custom setting exists in your org.

Note If you're installing a managed package for the first time, the Party.EnablePartyModel custom setting must be enabled. But if you're upgrading, it can be enabled or disabled, as long as it exists.

1.  From Setup, in the **Quick Find** box, enter Custom Settings.
2.  Click **Custom Settings**.
3.  Click **Trigger Setup**.
4.  Next to **Trigger Setup** click **Manage**.
5.  If Party.EnablePartyModel appears in the list, you're done. If not, click **New**. The Trigger Setup Edit page opens.
6.  In the **Name** field, enter Party.EnablePartyModel.
7.  Click **Save**.

Did this article solve your issue?

Let us know so we can improve!

YesNo