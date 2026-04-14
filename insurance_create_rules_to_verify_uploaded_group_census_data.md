---
title: "Create Rules to Verify Uploaded Group Census Data"
source: "https://help.salesforce.com/s/articleView?id=ind.insurance_create_rules_to_verify_uploaded_group_census_data.htm&language=en_US&type=5"
scraped: "2026-04-14"
filter: "ind.insurance_"
---# Create Rules to Verify Uploaded Group Census Data

Create Rules to Verify Uploaded Group Census Data[](https://help.salesforce.com/s?language=en_US)

You are here:

1.  [Salesforce Help](/s/?language=en_US)
2.  [Docs](/s/products?language=en_US)
3.  [Digital Insurance](https://help.salesforce.com/s/articleView?id=ind.insurance_admin_standard.htm&language=en_US&type=5)

# Create Rules to Verify Uploaded Group Census Data

Use triggers and validation rules that identify incomplete and invalid census data. This helps insurance carrier administrators and brokers identify and resolve exceptions efficiently.

Important These rules apply to the Group Census Member object in the Salesforce data model.

1.  From Setup, in Object Manager, find and select **Group Census Member**. Go to **Triggers**, and then click **New**.
    
    Define triggers that set a record's **Status** based on values in certain standard or custom fields.
    
    For example, define a trigger that sets **Status** to Completed if **Smoker Status** is specified, or to Incomplete if **Smoker Status** is null or blank.
    
    ```json
    trigger ContextExampleTrigger on GroupCensusMember (before insert, before update) {
    
        if (Trigger.isInsert) {
                       for(GroupCensusMember a : Trigger.New) {
                    if (String.isBlank(a.SmokerStatus) || a.SmokerStatus.equals('None')) {
                        a.Status = 'Incomplete';
                    } else {
                        a.Status = 'Completed';
                    }
                }  
                // Process before insert
                 
        }
        else if (Trigger.isUpdate) {
            for(GroupCensusMember a : Trigger.New) {
                    if (String.isNotBlank(a.SmokerStatus) && !a.SmokerStatus.equals('None')) {
                        a.Status = 'Completed';
                    } else {
                        a.Status = 'Incomplete';
                    }
                } 
        }
    }
    ```
    
2.  From Setup, in Object Manager, find and select **Group Census Member**. Go to **Validation Rules**, and then click **New**.
    
    Define criteria a record must meet before a user can save the record.
    
    For example, define a validation rule that verifies **Full Time Equivalent** is less than 1.
    

Did this article solve your issue?

Let us know so we can improve!

YesNo