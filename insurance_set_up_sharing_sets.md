---
title: "Set Up Sharing Sets"
source: "https://help.salesforce.com/s/articleView?id=ind.insurance_set_up_sharing_sets.htm&language=en_US&type=5"
scraped: "2026-04-14"
filter: "ind.insurance_"
---# Set Up Sharing Sets

Set Up Sharing Sets[](https://help.salesforce.com/s?language=en_US)

You are here:

1.  [Salesforce Help](/s/?language=en_US)
2.  [Docs](/s/products?language=en_US)
3.  [Digital Insurance](https://help.salesforce.com/s/articleView?id=ind.insurance_admin_standard.htm&language=en_US&type=5)

# Set Up Sharing Sets

Create a sharing set to give your Insurance Client Portal users access to the records that are relevant for using the insurance service processes. A sharing set grants portal users access to a record associated with an account or contact that matches the user's account or contact. Grant access to records through access mapping, which defines access for each object in the sharing set.

<table class="slds-table slds-table_bordered slds-m-bottom_small" lwc-3eigj2skqo3=""><colgroup lwc-3eigj2skqo3=""><col style="width:100%" lwc-3eigj2skqo3=""></colgroup><tbody lwc-3eigj2skqo3=""><tr class="" lwc-3eigj2skqo3=""><td style="vertical-align:top;" class="slds-cell-wrap" lwc-3eigj2skqo3=""><strong lwc-3eigj2skqo3="">REQUIRED EDITIONS</strong></td></tr><tr class="" lwc-3eigj2skqo3=""><td style="vertical-align:top;" class="slds-cell-wrap" lwc-3eigj2skqo3="">Available in: Lightning Experience in <strong class="uicontrol" lwc-3eigj2skqo3="">Professional</strong>, <strong class="uicontrol" lwc-3eigj2skqo3="">Enterprise</strong>, and <strong class="uicontrol" lwc-3eigj2skqo3="">Unlimited</strong> editions where Financial Services Cloud license is enabled with FSC Insurance add-on.</td></tr></tbody></table>

<table class="slds-table slds-table_bordered slds-m-bottom_small" lwc-3eigj2skqo3=""><colgroup lwc-3eigj2skqo3=""><col style="width:50%" lwc-3eigj2skqo3=""><col style="width:50%" lwc-3eigj2skqo3=""></colgroup><tbody lwc-3eigj2skqo3=""><tr class="" lwc-3eigj2skqo3=""><td style="vertical-align:top;" colspan="2" class="slds-cell-wrap" lwc-3eigj2skqo3=""><strong lwc-3eigj2skqo3="">USER PERMISSIONS NEEDED</strong></td></tr><tr class="" lwc-3eigj2skqo3=""><td style="vertical-align:top;" class="slds-cell-wrap" lwc-3eigj2skqo3="">To create or update sharing sets:</td><td style="vertical-align:top;" class="slds-cell-wrap" lwc-3eigj2skqo3="">Customize Application</td></tr></tbody></table>

1.  From Setup, in the Quick Find box, enter Digital Experiences, and then select **Settings**.
2.  In the Sharing Sets related list, click **New**.
3.  Enter a label for the sharing set.
4.  In the Select Profiles section, select your cloned community user profile, and click **Add**.
5.  Under Select Objects, select **Case**, **Insurance Policy**, and **Service Catalog Request**, and then click **Add**.
6.  In the Configured Access section, next to each object, click **Set Up** and configure access for the objects as shown in this table.
    
    | Object | ACCESS DETERMINED BY | Access Level |
    | --- | --- | --- |
    | Case | User:Account = Case:Owner.Account | Read/Write |
    | Insurance Policy | User:Account = Insurance Policy:NameInsured | Read Only |
    | Service Catalog Request | User:Account = Service Catalog Request:Case.Account | Read Only |
    
7.  Save your changes.

Did this article solve your issue?

Let us know so we can improve!

YesNo