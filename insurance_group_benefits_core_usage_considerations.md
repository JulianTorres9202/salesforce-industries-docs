---
title: "Group Benefits Usage Considerations"
source: "https://help.salesforce.com/s/articleView?id=ind.insurance_group_benefits_core_usage_considerations.htm&language=en_US&type=5"
scraped: "2026-04-14"
filter: "ind.insurance_"
---# Group Benefits Usage Considerations

Group Benefits Usage Considerations[](https://help.salesforce.com/s?language=en_US)

You are here:

1.  [Salesforce Help](/s/?language=en_US)
2.  [Docs](/s/products?language=en_US)
3.  [Digital Insurance](https://help.salesforce.com/s/articleView?id=ind.insurance_admin_standard.htm&language=en_US&type=5)

# Group Benefits Usage Considerations

Use of Insurance Group Benefits impacts the consumption of credits used for billing in these usage types.

### Required Editions

<table class="slds-table slds-table_bordered slds-m-bottom_small edition" lwc-3eigj2skqo3=""><colgroup lwc-3eigj2skqo3=""><col style="width:100%" lwc-3eigj2skqo3=""></colgroup><tbody lwc-3eigj2skqo3=""><tr class="" lwc-3eigj2skqo3=""><td style="vertical-align:top;" class="slds-cell-wrap" lwc-3eigj2skqo3="">Available in: Classic and Lightning Experience</td></tr><tr class="" lwc-3eigj2skqo3=""><td style="vertical-align:top;" class="slds-cell-wrap" lwc-3eigj2skqo3="">Available in: <strong class="uicontrol" lwc-3eigj2skqo3="">Professional</strong>, <strong class="uicontrol" lwc-3eigj2skqo3="">Enterprise</strong>, and<strong class="uicontrol" lwc-3eigj2skqo3=""> Unlimited</strong> Editions</td></tr></tbody></table>

| Usage Type | description | notes |
| --- | --- | --- |
| Group Quoting and Rating | Tracks credits used for Group Quoting | 
Credits are consumed when any of the following actions occur.

-   Create a quote from UI or through API.
-   For every configuration change in quote, such as update attributes, add or remove coverage from UI or through API.
-   Click **Rate Quote** or **Rate** on the quote page.

 |
| Enrollment | Tracks credits used for Enrollment and census management | 

Credits are consumed when any of the following actions occur.

-   Click **Upload Census** in the group census page
-   Click **Configure Plan** in the group census page.
-   Click **Enroll** in the group census page.
-   Invoke the Plan Eligibility API.
-   Invoke the Individual Rating API.

 |

Note The exact number of credits utilized are function of number of members and number of plans.

Group Benefits Credits usage isn’t reported in Digital Wallet. Your usage statement will be sent via email on a monthly basis. For details about how the Group Benefits Credits usage type is billed, see the Group Benefits Rate Card. For more information on how usage is billed, refer to your contract or contact your account executive.

Did this article solve your issue?

Let us know so we can improve!

YesNo