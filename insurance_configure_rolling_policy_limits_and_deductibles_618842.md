---
title: "Configure Rolling or Lifetime Policy Limits and Deductibles"
source: "https://help.salesforce.com/s/articleView?id=ind.insurance_configure_rolling_policy_limits_and_deductibles_618842.htm&language=en_US&type=5"
scraped: "2026-04-14"
filter: "ind.insurance_"
---# Configure Rolling or Lifetime Policy Limits and Deductibles

Configure Rolling or Lifetime Policy Limits and Deductibles[](https://help.salesforce.com/s?language=en_US)

You are here:

1.  [Salesforce Help](/s/?language=en_US)
2.  [Docs](/s/products?language=en_US)
3.  [Digital Insurance](https://help.salesforce.com/s/articleView?id=ind.insurance_admin_standard.htm&language=en_US&type=5)

# Configure Rolling or Lifetime Policy Limits and Deductibles

Track policies that cap a benefit over a rolling time period. For example, set a limit of two cleanings every 12 months for dental coverage.

You can use rolling 12-month limits and deductibles out of the box, and configure additional rolling time periods for any number of days or months. The amount that accumulates toward a limit or deductible on a current policy rolls over into the limit or deductible on a new policy version.

For each rolling time period:

-   Create an Insurance Term Configuration record in Custom Metadata Types.
    
-   Add the record value to the Vlocity Attribute object's Duration Type picklist.
    

1.  From Setup, in the Quick Find box, enter Custom Metadata Types, and then select **Custom Metadata Types**.
2.  Find **Insurance Term Configuration**, then click **Manage Records** next to it.
3.  Click **New**.
4.  Enter details about the rolling time period.
    
    <table class="slds-table slds-table_bordered slds-m-bottom_small" lwc-3eigj2skqo3=""><colgroup lwc-3eigj2skqo3=""><col style="width:50%" lwc-3eigj2skqo3=""><col style="width:50%" lwc-3eigj2skqo3=""></colgroup><tbody lwc-3eigj2skqo3=""><tr class="" lwc-3eigj2skqo3=""><td style="vertical-align:top;" class="slds-cell-wrap" lwc-3eigj2skqo3=""><p style="margin-bottom:0;" lwc-3eigj2skqo3=""><strong class="uicontrol" lwc-3eigj2skqo3="">Label</strong></p></td><td style="vertical-align:top;" class="slds-cell-wrap" lwc-3eigj2skqo3=""><p style="margin-bottom:0;" lwc-3eigj2skqo3="">A description of the rolling time period, for example Rolling 24 Month or Rolling 36 Month.</p></td></tr><tr class="" lwc-3eigj2skqo3=""><td style="vertical-align:top;" class="slds-cell-wrap" lwc-3eigj2skqo3=""><p style="margin-bottom:0;" lwc-3eigj2skqo3=""><strong class="uicontrol" lwc-3eigj2skqo3="">Insurance Term Configuration Name</strong></p></td><td style="vertical-align:top;" class="slds-cell-wrap" lwc-3eigj2skqo3=""><p style="margin-bottom:0;" lwc-3eigj2skqo3="">API name. You can accept the default value or edit it. Use this value when you add the rolling time period to the Vlocity Attribute object's Duration Type picklist.</p></td></tr><tr class="" lwc-3eigj2skqo3=""><td style="vertical-align:top;" class="slds-cell-wrap" lwc-3eigj2skqo3=""><p style="margin-bottom:0;" lwc-3eigj2skqo3=""><strong class="uicontrol" lwc-3eigj2skqo3="">Duration Unit of Measure</strong></p></td><td style="vertical-align:top;" class="slds-cell-wrap" lwc-3eigj2skqo3=""><p style="margin-bottom:0;" lwc-3eigj2skqo3="">How to measure the time period, in days or months.</p></td></tr><tr class="" lwc-3eigj2skqo3=""><td style="vertical-align:top;" class="slds-cell-wrap" lwc-3eigj2skqo3=""><p style="margin-bottom:0;" lwc-3eigj2skqo3=""><strong class="uicontrol" lwc-3eigj2skqo3="">Duration Value</strong></p></td><td style="vertical-align:top;" class="slds-cell-wrap" lwc-3eigj2skqo3=""><p style="margin-bottom:0;" lwc-3eigj2skqo3="">The number of days or months in the time period.</p></td></tr><tr class="" lwc-3eigj2skqo3=""><td style="vertical-align:top;" class="slds-cell-wrap" lwc-3eigj2skqo3=""><p style="margin-bottom:0;" lwc-3eigj2skqo3=""><strong class="uicontrol" lwc-3eigj2skqo3="">Type</strong></p></td><td style="vertical-align:top;" class="slds-cell-wrap" lwc-3eigj2skqo3=""><p style="margin-bottom:0;" lwc-3eigj2skqo3=""><strong class="uicontrol" lwc-3eigj2skqo3="">Rolling</strong>.</p></td></tr></tbody></table>
    
    Tip
    
    [](https://help.salesforce.com/s?language=en_US)If **Duration Unit of Measure**, **Duration Value**, and **Type** are missing from the configuration, click the quick access menu and choose **Edit Layout** to add these fields to the page layout.
    
5.  In the Quick Find box, enter Object Manager, and then select **Object Manager**. Then find and select **Vlocity Attribute**.
6.  Click **Fields & Relationships**, then find and select **Duration Type**.
7.  Scroll to the field values and click **New**.
8.  For the picklist value, enter the API name of the rolling time period record. Make sure this value matches the record's **Insurance Term Configuration Name** exactly, not the **Label**.

[](https://help.salesforce.com/s?language=en_US)

Users who configure power attributes can select the rolling time periods that you configure and add to the duration type picklist.

Did this article solve your issue?

Let us know so we can improve!

YesNo