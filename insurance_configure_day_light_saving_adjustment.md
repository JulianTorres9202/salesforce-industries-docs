---
title: "Automate Daylight Saving Time Transitions"
source: "https://help.salesforce.com/s/articleView?id=ind.insurance_configure_day_light_saving_adjustment.htm&language=en_US&type=5"
scraped: "2026-04-14"
filter: "ind.insurance_"
---# Automate Daylight Saving Time Transitions

Automate Daylight Saving Time Transitions[](https://help.salesforce.com/s?language=en_US)

You are here:

1.  [Salesforce Help](/s/?language=en_US)
2.  [Docs](/s/products?language=en_US)
3.  [Digital Insurance](https://help.salesforce.com/s/articleView?id=ind.insurance_admin_standard.htm&language=en_US&type=5)

# Automate Daylight Saving Time Transitions

Configure your org with custom settings to automatically adjust time-sensitive insurance processes during Daylight Saving Time (DST) changes. Enable a custom setting to keep policy workflows accurate by aligning date and time values with your org’s time zone during DST start and end dates. The setting is off by default but can be turned on when DST alignment is required.

### Required Editions

<table class="slds-table slds-table_bordered slds-m-bottom_small edition" lwc-3eigj2skqo3=""><colgroup lwc-3eigj2skqo3=""><col lwc-3eigj2skqo3=""></colgroup><tbody lwc-3eigj2skqo3=""><tr class="" lwc-3eigj2skqo3=""><td style="vertical-align:top;" class="slds-cell-wrap" lwc-3eigj2skqo3="">Available in: Lightning Experience</td></tr><tr class="" lwc-3eigj2skqo3=""><td style="vertical-align:top;" class="slds-cell-wrap" lwc-3eigj2skqo3="">Available in: <strong lwc-3eigj2skqo3="">Professional</strong>, <strong lwc-3eigj2skqo3="">Enterprise</strong>, and <strong lwc-3eigj2skqo3="">Unlimited</strong> Editions with the Insurance Industries managed package and the Insurance Industries Extension managed package.</td></tr></tbody></table>

1.  From Setup, in the Quick Find box, find and select **Custom Settings**.
2.  Next to Insurance Configuration Setup, click **Manage**.
3.  Click **New** to create a new custom setting.
4.  Enter these values
    
    -   Name: EnableDSTAdjustment
    -   Value: true
    
5.  Save your changes.

Did this article solve your issue?

Let us know so we can improve!

YesNo