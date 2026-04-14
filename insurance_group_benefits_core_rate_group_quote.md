---
title: "Rate a Group Quote"
source: "https://help.salesforce.com/s/articleView?id=ind.insurance_group_benefits_core_rate_group_quote.htm&language=en_US&type=5"
scraped: "2026-04-14"
filter: "ind.insurance_"
---# Rate a Group Quote

Rate a Group Quote[](https://help.salesforce.com/s?language=en_US)

You are here:

1.  [Salesforce Help](/s/?language=en_US)
2.  [Docs](/s/products?language=en_US)
3.  [Digital Insurance](https://help.salesforce.com/s/articleView?id=ind.insurance_admin_standard.htm&language=en_US&type=5)

# Rate a Group Quote

Use rating to calculate premiums for group quotes based on census data, plan selection, and pricing procedures. Rating runs either at the member level or the group summary level depending on the value selected in the Census Rating Type field on the quote.

### Required Editions

<table class="slds-table slds-table_bordered slds-m-bottom_small edition" lwc-3eigj2skqo3=""><colgroup lwc-3eigj2skqo3=""><col style="width:100%" lwc-3eigj2skqo3=""></colgroup><tbody lwc-3eigj2skqo3=""><tr class="" lwc-3eigj2skqo3=""><td style="vertical-align:top;" class="slds-cell-wrap" lwc-3eigj2skqo3="">Available in: Lightning Experience</td></tr><tr class="" lwc-3eigj2skqo3=""><td style="vertical-align:top;" class="slds-cell-wrap" lwc-3eigj2skqo3="">Available in: <strong class="uicontrol" lwc-3eigj2skqo3="">Professional</strong>, <strong class="uicontrol" lwc-3eigj2skqo3="">Enterprise</strong>, and<strong class="uicontrol" lwc-3eigj2skqo3=""> Unlimited</strong> Editions of Digital Insurance with Digital Insurance Product Admin Add On, Digital Insurance Group Benefits AddOn, Digital Insurance Group Enrollment AddOn,Digital Insurance Group Benefits Customer Community AddOn, and Digital Insurance Group Benefits Partner Community AddOn licenses</td></tr></tbody></table>

| User Permissions Needed |
| --- |
| To rate a group quote | Digital Insurance Group Census Quote Contract Management, Digital Insurance Group Census Quote Contract Management Partner Community |

Create separate pricing procedures for member-based and summary-based plans, and then define the corresponding procedure plan definitions.

Considerations

-   The quote must include at least one group insurance product.
-   The census must contain either summary data (for summary-based rating) or at least one member record (for member-based rating).
-   Configure each group insurance product with at least one coverage record for every group summary and placeholder group census member combination.
-   Census Rating Type field controls how rating is applied:
    -   Member-based: Calculates premiums at the family or member level by applying member attributes, coverages, and plan details.
    -   Summary-based: Calculates premiums for all members based on summary information about the group census or group class along with plans, coverages and its attribute selection.
-   If you upload a new census or change group member and dependent values such as birth date or gender, run the Rate action again to apply the new data.
-   You can rate up to 30 summary-based plans and 150,000 census members at a time.
-   You can rate up to 30 member-based plans and 3,000 members at a time.
-   If a quote contains more than 30 plans, don't use Rate All Plans. Instead:
    -   Rate the first 30 plans individually with Rate Plan. Wait for those ratings to complete.
    -   Continue with the next set of up to 30 plans.

How premiums are calculated

-   Coverage Premium:
    -   Member-Based Rating – The pricing procedure returns coverage premiums for each member. These premiums are aggregated across all members in a group class or group census (based on configuration) to calculate the cumulative coverage premium. This cumulative amount is reflected on the quote line item for the coverage product.
    -   Summary-Based Rating – The pricing procedure returns coverage premiums at the summary level. The returned premium is treated as the cumulative coverage premium for the entire group class or group census (based on configuration).
-   Group Summary Aggregation – For both member-based and summary-based rating, the quote line item for the group summary product aggregates all coverage premiums associated with that group summary.

1.  From the App Launcher, find and select **Quotes**.
2.  Open the quote you want to rate.
3.  Choose one of the following actions:
    
    -   To rate the entire quote, click **Rate Quote**.
    -   To rate an individual plan, open the row action menu next to the quote line item and click **Rate**.
    
4.  Wait for the rating process to complete. Status messages show the progress of the latest request. If you make changes after the status shows Completed, the status still shows Completed.
5.  Review the calculated premiums in the Quote Line Item Grid.

Did this article solve your issue?

Let us know so we can improve!

YesNo