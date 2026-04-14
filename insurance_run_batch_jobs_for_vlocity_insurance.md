---
title: "Run Batch Jobs for Insurance"
source: "https://help.salesforce.com/s/articleView?id=ind.insurance_run_batch_jobs_for_vlocity_insurance.htm&language=en_US&type=5"
scraped: "2026-04-14"
filter: "ind.insurance_"
---# Run Batch Jobs for Insurance

Run Batch Jobs for Insurance[](https://help.salesforce.com/s?language=en_US)

You are here:

1.  [Salesforce Help](/s/?language=en_US)
2.  [Docs](/s/products?language=en_US)
3.  [Digital Insurance](https://help.salesforce.com/s/articleView?id=ind.insurance_admin_standard.htm&language=en_US&type=5)

# Run Batch Jobs for Insurance

Insurance provides several Apex batch jobs that correct incomplete or erroneous Insurance records in your org. Run these batch jobs to initiate them.

1.  Click the quick access menu (Setup gear icon), and click **Developer Console**.
2.  From the Debug menu, select **Open Execute Anonymous Window**.
3.  Paste one of these code blocks into the **Enter Apex Code** dialog box.
    
    Run Fix Product Attribute Metadata batch job:
    
    ```
    vlocity_ins.FixProductAttribJSONBatchJob attrJSONBatchJob = new vlocity_ins.FixProductAttribJSONBatchJob();ID batchprocessid3 = Database.executeBatch(attrJSONBatchJob);System.debug ('Fix attribute JSON:' + batchProcessId3);
    ```
    
    Add Source Type Product Attribute Rules batch job:
    
    ```
    vlocity_ins.AttributeRuleUpgradeBatch upgradeAttrRuleBatchJob = new vlocity_ins.AttributeRuleUpgradeBatch();ID batchProcessId2 = Database.executeBatch(upgradeAttrRuleBatchJob);System.debug('Add source type to attribute rule process id:' + batchProcessId2);
    ```
    
    Fix Incomplete Override Definition batch job:
    
    ```
    vlocity_ins.FixIncompleteOverrideDefinitionBatch fixOverrideBatchJob = new vlocity_ins.FixIncompleteOverrideDefinitionBatch();ID batchProcessId1 = Database.executeBatch(fixOverrideBatchJob);System.debug('Fix Incomplete Override Definition process id:' + batchProcessId1);
    ```
    
4.  Click **Execute**.
5.  Repeat steps 3 and 4 with the remaining code blocks.

Did this article solve your issue?

Let us know so we can improve!

YesNo