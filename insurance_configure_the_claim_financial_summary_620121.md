---
title: "Configure the Claim Financial Summary"
source: "https://help.salesforce.com/s/articleView?id=ind.insurance_configure_the_claim_financial_summary_620121.htm&language=en_US&type=5"
scraped: "2026-04-14"
filter: "ind.insurance_"
---# Configure the Claim Financial Summary

Configure the Claim Financial Summary[](https://help.salesforce.com/s?language=en_US)

You are here:

1.  [Salesforce Help](/s/?language=en_US)
2.  [Docs](/s/products?language=en_US)
3.  [Digital Insurance](https://help.salesforce.com/s/articleView?id=ind.insurance_admin_standard.htm&language=en_US&type=5)

# Configure the Claim Financial Summary

Claims adjusters can monitor financials using charts that answer key questions: What are the losses worth and how much of the reserve is left? How much has been spent on loss and expenses payments? How do claim recoveries impact financial exposure? How much of the deductible or limit has a policyholder consumed?

1.  On a claim, click the quick access menu (the gear icon) and select **Edit Page**.
2.  Click the Tabs component, then click **Add Tab**.
3.  Click the new tab. For **Tab Label**, enter Summary.
4.  Find the **Vlocity Policy Terms Standing** component, then drag it to the new Summary tab.
5.  Find the **Vlocity Claim Items Chart** component, then drag it to the new Summary tab.
6.  In the Summary panel, click the Financial Summary chart and select **Vlocity Claim Items Chart** settings.
    
    If your org tracks claim recoveries by using the Claim Recovery object, use these chart settings to control how estimated and actual recovery amounts impact the overall financial exposure calculation.
    
    <table class="slds-table slds-table_bordered slds-m-bottom_small" lwc-3eigj2skqo3=""><colgroup lwc-3eigj2skqo3=""><col style="width:50%" lwc-3eigj2skqo3=""><col style="width:50%" lwc-3eigj2skqo3=""></colgroup><tbody lwc-3eigj2skqo3=""><tr class="" lwc-3eigj2skqo3=""><td style="vertical-align:top;" class="slds-cell-wrap" lwc-3eigj2skqo3=""><p style="margin-bottom:0;" lwc-3eigj2skqo3=""><strong class="uicontrol" lwc-3eigj2skqo3="">Include Pursued Recovery</strong></p></td><td style="vertical-align:top;" class="slds-cell-wrap" lwc-3eigj2skqo3=""><p style="margin-bottom:0;" lwc-3eigj2skqo3="">Select this check box to subtract estimated recovery amounts from the Financial Exposure value at the center of the chart.</p></td></tr><tr class="" lwc-3eigj2skqo3=""><td style="vertical-align:top;" class="slds-cell-wrap" lwc-3eigj2skqo3=""><p style="margin-bottom:0;" lwc-3eigj2skqo3=""><strong class="uicontrol" lwc-3eigj2skqo3="">Include Accepted Recovery</strong></p></td><td style="vertical-align:top;" class="slds-cell-wrap" lwc-3eigj2skqo3=""><p style="margin-bottom:0;" lwc-3eigj2skqo3="">Select this check box to subtract actual recovery amounts from the Financial Exposure value at the center of the chart.</p></td></tr></tbody></table>
    
    Note
    
    This applies to the Salesforce FSC ClaimRecovery object, not the vlocity\_ClaimRecovery\_\_c object.
    
7.  Click **Save**.

Did this article solve your issue?

Let us know so we can improve!

YesNo