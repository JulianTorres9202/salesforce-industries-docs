---
title: "Tracking Earned and Unearned Revenue"
source: "https://help.salesforce.com/s/articleView?id=ind.insurance_tracking_earned_and_unearned_revenue_622091.htm&language=en_US&type=5"
scraped: "2026-04-14"
filter: "ind.insurance_"
---# Tracking Earned and Unearned Revenue

Tracking Earned and Unearned Revenue[](https://help.salesforce.com/s?language=en_US)

You are here:

1.  [Salesforce Help](/s/?language=en_US)
2.  [Docs](/s/products?language=en_US)
3.  [Digital Insurance](https://help.salesforce.com/s/articleView?id=ind.insurance_admin_standard.htm&language=en_US&type=5)

# Tracking Earned and Unearned Revenue

You can use Insurance for revenue recognition for insurance policies. Revenue recognition tracks revenue per-policy as follows:

-   Earned Revenue
    
    The portions of the total policy premium that have been paid to a given date
    
-   Unearned Revenue
    
    The portions of the total policy premium that have not been paid yet
    

The earned revenue is posted to the carrier's accounting system as revenue on the income statement, and the unearned portion is posted as a deferred revenue on its balance sheet.

For example, an insurance policy you sell has a one-year term with monthly payments. Five months into the policy term, your earned revenue = 5/12 of the total policy premium. Your unearned revenue = 7/12 of the total policy premium, which is subject to modification or cancellation by the policy holder.

## Services

The revenue tracking feature uses the following ApexVlocity Insurance services:

-   [InsPolicyRevenueScheduleService:createRevenueSchedule](https://help.salesforce.com/s/articleView?id=ind.insurance_inspolicyrevenuescheduleservice__createrevenueschedule.htm&language=en_US&type=5 "This service creates a monthly revenue schedule for a policy, starting on the effective date of the policy and ending on the expiration date of the policy term.")
    
-   [InsPolicyRevenueScheduleService:modifyRevenueSchedule](https://help.salesforce.com/s/articleView?id=ind.insurance_inspolicyrevenuescheduleservice__modifyrevenueschedule.htm&language=en_US&type=5 "This service takes in the modifications done to the policy. Based on the changes to total policy premium and the modification date, it recalculates the revenue schedule to adjust the unpaid monthly premiums (unearned revenue).")
    
-   [InsPolicyRevenueScheduleService:cancelRevenueSchedule](https://help.salesforce.com/s/articleView?id=ind.insurance_inspolicyrevenuescheduleservice__cancelrevenueschedule.htm&language=en_US&type=5 "When a policy is canceled, this service adjusts the revenue schedule to calculate revenue until the cancellation date.")
    

[](https://help.salesforce.com/s?language=en_US)

## Adding Revenue Tracking to OmniScripts

You can add revenue tracking to Integration Procedures and OmniScripts.

To create revenue tracking for new policies, follow the steps in [Create Revenue Tracking for a New Policy](https://help.salesforce.com/s/articleView?id=ind.insurance_tracking_earned_and_unearned_revenue_622091.htm&language=en_US&type=5 "You can use Insurance for revenue recognition for insurance policies. Revenue recognition tracks revenue per-policy as follows:") in a quote-to-policy OmniScript.

To modify revenue tracking for an updated policy, follow the steps in [Modify Revenue Tracking for an Existing Policy](https://help.salesforce.com/s/articleView?id=ind.insurance_tracking_earned_and_unearned_revenue_622091.htm&language=en_US&type=5 "You can use Insurance for revenue recognition for insurance policies. Revenue recognition tracks revenue per-policy as follows:") in the OmniScript you use for policy updates. To cancel revenue tracking for a canceled policy, follow the steps in [Cancel Revenue Tracking for a Canceled Policy](https://help.salesforce.com/s/articleView?id=ind.insurance_tracking_earned_and_unearned_revenue_622091.htm&language=en_US&type=5 "You can use Insurance for revenue recognition for insurance policies. Revenue recognition tracks revenue per-policy as follows:") in the OmniScript you use for policy cancellation.

[](https://help.salesforce.com/s?language=en_US)

## Create Revenue Tracking for a New Policy

To add revenue tracking to a new insurance policy when it's created:

1.  After the Create Policy remote action, add an action that creates a transaction record for the policy.
    
    For example, you can add an Omnistudio Data Mapper Post Action that includes the following fields:
    
    Add back image
    
2.  Add a Remote Action to the OmniScript after the Data Mapper Post Action in step 1.
    
3.  In Remote Class, enter InsPolicyRevenueScheduleService.
    
4.  In Remote Method, enter create.
    
5.  Under Remote Options, enter two new key/value pairs:
    
    1.  For the first pair, key = assetId, value = %policyId%.
        
    2.  For the second pair, use a merge field to get the transaction ID created in step 1. For example:
        
        key = transactionId, value = %transactionId\_for\_policy\_creation%
        
6.  (Optional) Under Conditional View, click **Add Condition**. Enter a condition under which you do not want the revenue tracking action to appear in the OmniScript.
    

[](https://help.salesforce.com/s?language=en_US)

## Modify Revenue Tracking for an Existing Policy

To set up Vlocity to modify a revenue schedule, you must do the following:

1.  Capture the modification the user made to the policy.
    
2.  Capture the modification amount of the policy premium.
    
3.  Create a modification transaction.
    
4.  Use the modify revenue schedule service to calculate the changes to the revenue schedule.
    

Here's an example that shows one way to create an OmniScript that modifies the revenue schedule:

1.  Create a calculation procedure that takes changes a user to makes to a policy and calculates a modified revenue schedule.
    
2.  Create a Data Mapper Transform to use as a Pre-Transform Data Mapper Interface in the next step.
    
    This Data Mapper Transform must have the following Input JSON Paths and Output JSON Paths:
    
3.  Add a Calculation Action to the OmniScript after the policy update Remote Action.
    
    1.  In the Remote Options section, verify that the Remote Class and Remote Method are those you use for calculation procedures. Enter a Configuration Name.
        
    2.  Select the **Include Inputs** checkbox.
        
    3.  In **Pre-Transform Data Mapper Interface**, select the Data Mapper Transform you created in step 2.
        
    
4.  Add a Data Mapper Post Action after the Calculation Action.
    
    1.  Verify that the following fields exist for Asset Transaction:
        
    2.  In the Type field, enter a **Default Value** that works across all the policies that will use this Integration Procedure. Use this default value for every policy, don't change or customize it. The value gets taken up by the service in the remote action following this Data Mapper.
        
        For example:
        
5.  Add a Remote Action after the Data Mapper Post Action.
    
    1.  Remote Class = `InsPolicyRevenueScheduleService`
        
    2.  Remote Method = `modify`.
        
    3.  Remote Options include the following key/value pairs:
        
        | 
        Key
        
         | 
        
        Value
        
         |
        | --- | --- |
        | 
        
        `assetId`
        
         | 
        
        `%policyId%`
        
         |
        | 
        
        `transactionId`
        
         | 
        
        `%transactionId_for_policy_modification%`
        
         |
        | 
        
        `effectiveDate`
        
         | 
        
        `%policy:modificationDate%`
        
         |
        

If you plan to add revenue schedule modification to multiple OmniScripts, you can create an Integration Procedure using steps 1-5. You can then add the Integration Procedure to any OmniScript.

[](https://help.salesforce.com/s?language=en_US)

## Cancel Revenue Tracking for a Canceled Policy

To set up Vlocity to cancel a revenue schedule, you must do the following:

1.  Calculate a refund amount.
    
2.  Create a transaction that captures the cancellation.
    
3.  Set up the cancel revenue schedule service to use the transaction to calculate the cancellation of the revenue schedule.
    

Here's an example that shows one way to create an OmniScript that cancels a revenue schedule:

1.  Create a calculation procedure that takes policy cancellation and calculates a canceled revenue schedule.
    
2.  Create a Data Mapper Transform to use as a Pre-Transform Data Mapper Interface in the next step.
    
    This Data Mapper Transform must have the following Input JSON Paths and Output JSON Paths:
    
3.  Add a Calculation Action to the OmniScript after the policy update Remote Action.
    
    1.  In the Remote Options section, verify that the Remote Class and Remote Method are those you use for calculation procedures. Enter a Configuration Name.
        
    2.  Select the **Include Inputs** checkbox.
        
    3.  In **Pre-Transform Data Mapper Interface**, select the Data Mapper Transform you created in step 2.
        
    
4.  Add a Data Mapper Post Action after the Calculation Action.
    
    1.  Verify that the following fields exist for Asset:
        
    2.  Verify that the following fields exist for Asset Transaction:
        
    3.  Enter a formula similar to the following to make the transaction amount captured into a negative amount (refund):
        
5.  Add a Remote Action after the Data Mapper Post Action.
    
    1.  Remote Class = `InsPolicyRevenueScheduleService`
        
    2.  Remote Method = `cancel`.
        
    3.  Remote Options include the following key/value pairs:
        
        | 
        Key
        
         | 
        
        Value
        
         |
        | --- | --- |
        | 
        
        `assetId`
        
         | 
        
        `%policyId%`
        
         |
        | 
        
        `transactionId`
        
         | 
        
        `%transactionId_for_policy_cancellation%`
        
         |
        | 
        
        `effectiveDate`
        
         | 
        
        `%policy:cancellationDate%`
        
         |
        
6.  Add a Response Action after the Remote Action to echo the policy ID.
    

If you plan to add revenue schedule cancellation to multiple OmniScripts, you can create an Integration Procedure using steps 1-5. You can then add the Integration Procedure to any OmniScript.

-   **[Configuring the Asset Page to Track Revenue](https://help.salesforce.com/s/articleView?id=ind.insurance_configuring_the_asset_page_to_track_revenue_622116.htm&language=en_US&type=5)**  
    To see the revenue schedule, with earned and unearned revenue, go to the policy (asset) object for a specific policy.
-   **[Revenue Schedule Display Lightning Web Components](https://help.salesforce.com/s/articleView?id=ind.insurance_revenue_schedule_display_lightning_web_components_622377.htm&language=en_US&type=5)**  
    You can view the **Revenue Schedule** for a policy on the Policy (Asset) record. The **Revenue Schedule** tab displays two Lightning Web Components (LWC): Vlocity Insurance Revenue Charts and Vlocity Insurance Revenue Schedule.

Did this article solve your issue?

Let us know so we can improve!

YesNo