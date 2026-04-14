---
title: "Complete Installation Assistant Tasks Manually"
source: "https://help.salesforce.com/s/articleView?id=ind.insurance_complete_installation_assistant_tasks_manually.htm&language=en_US&type=5"
scraped: "2026-04-14"
filter: "ind.insurance_"
---# Complete Installation Assistant Tasks Manually

Complete Installation Assistant Tasks Manually[](https://help.salesforce.com/s?language=en_US)

You are here:

1.  [Salesforce Help](/s/?language=en_US)
2.  [Docs](/s/products?language=en_US)
3.  [Digital Insurance](https://help.salesforce.com/s/articleView?id=ind.insurance_admin_standard.htm&language=en_US&type=5)

# Complete Installation Assistant Tasks Manually

If you're upgrading from several versions back, you can simplify your upgrade by focusing on changes between releases and by completing certain tasks only one time.

## Release-Specific Tasks

These tasks have changed slightly between releases. We recommend that you verify the changes in each release to make sure that your org has the latest updates. Complete the tasks for the versions between your starting version and the version you upgraded to. To determine which data to update for each task, click the link to details about each task, and then note the version listed in the Release Added column. For example, you're upgrading from Spring '22 (236) to Winter '25 (252). When you add picklist values for Insurance, you note that most picklist values were added in Spring '22 or earlier. Only one picklist value is marked as added in Summer '22 (238). After you add this value, you're up to date.

For example:

| Starting Release Version | Upgraded To Version | Complete Tasks |
| --- | --- | --- |
| Spring '23 (242) | Winter ’25 (252) | None. There haven't been any updates to these tasks since the Summer '22 release. |
| Spring '22 (236) | Winter '25 (252) | Marked as added in Summer '22 (238). There haven't been any updates to these tasks since the Summer '22 release. |
| Spring '21 (230) | Spring '22 (236) | Marked as added in Summer '21 (232), Winter '22 (234), and Spring '22 (236) |
| Any release before Spring '21 (230) | Summer '21 (232) | Marked as added in Spring '21 (230) and Summer '21 (232) |

Complete these tasks for the Insurance managed package:

-   [Add Picklist Values for Insurance Releases Spring '21 Through Winter '25](https://help.salesforce.com/s/articleView?id=ind.insurance_combined_picklist_values_230_thru_246.htm&language=en_US&type=5 "Add values to picklist fields on several objects used with Insurance.")
-   [Manage Picklist Values in the Attribute Class Field of Vlocity Attribute Object for Insurance Releases Spring '21 Through Winter '25](https://help.salesforce.com/s/articleView?id=ind.insurance_combined_manage_picklist_values_in_attribute_class_field.htm&language=en_US&type=5 "Change the label and edit the API name of several values in the Attribute Class picklist on the Vlocity Attribute Object.")
-   [Add Fields to Object Field Sets for Insurance Release Spring '21 Through Winter '25](https://help.salesforce.com/s/articleView?id=ind.insurance_combined_add_fields_to_object_field_sets.htm&language=en_US&type=5 "Add fields to field sets on several objects used with Insurance.")
-   [Create Insurance Permission Sets](https://help.salesforce.com/s/articleView?id=ind.insurance_create_insurance_permission_sets.htm&language=en_US&type=5 "Use anonymous Apex to create Insurance Permission Sets.")
    
    Note You can create Insurance Permission Sets in the Summer '21 release onward. This step isn't for orgs upgrading to the Spring '21 release.
    

In addition to the tasks listed for the Insurance Managed Package, you must also complete these steps if you use the Insurance Industries Extension Managed Package:

-   [Add Picklist Values for Insurance Industries Extension Releases Spring '21 Through Winter '25](https://help.salesforce.com/s/articleView?id=ind.insurance_combined_picklist_values_230_thru_246_iie.htm&language=en_US&type=5 "Add values to picklist fields on several objects used with the Insurance Industries Extension.")
-   [Add Fields to Object Field Sets for Insurance Industries Extension Releases Spring '21 Through Winter '25](https://help.salesforce.com/s/articleView?id=ind.insurance_add_fields_to_object_field_sets_iie.htm&language=en_US&type=5 "Add fields to field sets on several objects used with Insurance Industries Extension.")
-   [Activate Record Pages From the Managed Package for Insurance Industries Extension Releases Spring '21 Through Winter '25](https://help.salesforce.com/s/articleView?id=ind.insurance_combined_activate_record_pages_from_the_managed_package_for_iie.htm&language=en_US&type=5 "Clone and activate the pre-configured record pages that are installed automatically in the managed package.")
-   [Create Insurance Industries Extension Permission Sets](https://help.salesforce.com/s/articleView?id=ind.insurance_create_insurance_industries_extension_permission_sets.htm&language=en_US&type=5 "Use anonymous Apex to create Insurance Industries Extension Permission Sets.")
    
    Note You can create Insurance Industries Extension Permission Sets in the Summer '21 release onward. This step isn't for orgs upgrading to the Spring '21 release.
    

## Required Tasks for all Releases

These tasks haven't changed since the Spring '21 release. If you're on a release after Spring '21 and you've completed these post-upgrade tasks before, you don't have to complete these tasks again.

Note If you use Group Benefits or Claims features, make sure that the useVlocityPolicyModel custom setting isn't enabled. To learn how, see [Enable or Disable the Insurance Industries Extension Data Model](https://help.salesforce.com/s/articleView?id=ind.insurance_enable_the_pre_existing_insurance_industries_extension_data_model_598317.htm&language=en_US&type=5 "When you install or upgrade to the Insurance managed package and the Insurance Industries Extension package, the Insurance Policy core object model is automatically enabled. But if you're upgrading and you're not prepared to use the Insurance Policy core object model yet, use a custom setting to disable the use of the core object model until you're ready to make the switch.").

Insurance Managed Package

-   [Manage Picklist Values in the Status Field of the Claim Line Item Object](https://help.salesforce.com/s/articleView?id=ind.insurance_manage_picklist_values_in_the_status_field_of_claim_line_item_object.htm&language=en_US&type=5 "Deactivate Status picklist values and set the default value of the Status on the Claim Line Item object.")
-   [Add Expression Set to the Rating Procedure Type Picklist for the Product Record Type](https://help.salesforce.com/s/articleView?id=ind.insurance_add_expression_set_to_the_rating_procedure_type_picklist_for_the_product_record_type.htm&language=en_US&type=5 "Add Expression Set to the Rating Procedure Type picklist for the Product record type in the Product object.")
-   [Update the Claim Line Item's Record Type Status](https://help.salesforce.com/s/articleView?id=ind.insurance_update_the_claim_line_item_s_record_type_status.htm&language=en_US&type=5 "For the Claim Line Item record type, add values to the Status picklist.")
-   [Install OmniScript Template DataPacks for Insurance](https://help.salesforce.com/s/articleView?id=ind.insurance_install_omniscript_template_datapacks_for_vlocity_insurance_and_vlocity_health.htm&language=en_US&type=5 "OmniScript templates control the look, feel, and some of the behavior of Insurance OmniScripts.")
-   [Activate Record Pages From the Managed Package for Insurance](https://help.salesforce.com/s/articleView?id=ind.insurance_activate_record_pages_from_the_managed_package_for_vlocity_insurance.htm&language=en_US&type=5 "Clone and activate the pre-configured record pages that are installed automatically in the managed package.")
-   [Enable Record Types for Insurance](https://help.salesforce.com/s/articleView?id=ind.insurance_enable_record_types_for_vlocity_insurance.htm&language=en_US&type=5 "Enabling record types for profiles gives users with that profile access to the record type. Use these steps to enable the Insurance record types listed in the table below.")
-   [Create and Set the RetainProductAttribJSON Custom Setting for Insurance](https://help.salesforce.com/s/articleView?id=ind.insurance_create_and_set_the_retainproductattribjson_custom_setting_for_vlocity_insurance_and_vlocity_health.htm&language=en_US&type=5 "Most insurance companies use lots of attributes as part of insurance products. Unless you're planning a special setup that will not use attributes much, or you're already using information saved by JSONAttribute __c, create a custom setting called RetainProductAttribJSON and set it to false. This keeps JSONAttribute__c from saving attributes and speeds up your users' experience.")
-   [Add the Create New Version Button to Calculation Matrix and Calculation Procedure Version Pages](https://help.salesforce.com/s/articleView?id=ind.insurance_add_the_create_new_version_button_to_vlocity_calculation_matrix_and_calculation_procedure_version_pages.htm&language=en_US&type=5 "The buttons that let you create new versions of calculation matrices and calculation procedures exist in Insurance, but they're not included in the page layouts by default.")
-   [Set Up Custom Field Mapper for Insurance](https://help.salesforce.com/s/articleView?id=ind.insurance_set_up_custom_field_mapper_ins_task.htm&language=en_US&type=5 "To get Quote Line Items to display correctly, download the CustomFieldMap file from Static Resources, then install it as a DataPack.")
-   [Upgrade Product Attribute Set Value Rules for Insurance](https://help.salesforce.com/s/articleView?id=ind.insurance_upgrade_product_attribute_set_value_rules_for_vlocity_insurance_and_vlocity_health.htm&language=en_US&type=5 "Fix any set value rules with incompatible or unsupported methods.")
-   [Assign Permission Sets to the Analytics Integration User](https://help.salesforce.com/s/articleView?id=ind.insurance_assign_permission_sets_to_the_analytics_integration_user.htm&language=en_US&type=5 "If your org uses Tableau CRM for Insurance, assign permission sets to the Analytics Integration User.")
-   [Run Batch Jobs for Insurance](https://help.salesforce.com/s/articleView?id=ind.insurance_run_batch_jobs_for_vlocity_insurance.htm&language=en_US&type=5 "Insurance provides several Apex batch jobs that correct incomplete or erroneous Insurance records in your org. Run these batch jobs to initiate them.")

Insurance Industries Extension Managed Package

-   [Set the Default Value of the Premium Frequency Field on the Insurance Policy Object](https://help.salesforce.com/s/articleView?id=ind.insurance_set_the_default_value_of_the_premium_frequency_field_on_the_insurance_policy_object.htm&language=en_US&type=5 "Set the default value of the Insurance Policy object's Premium Frequency picklist to Annually.")
-   [Set Up Custom Field Mapper for Insurance Industries Extension](https://help.salesforce.com/s/articleView?id=ind.insurance_set_up_custom_field_mapper_iie_task.htm&language=en_US&type=5 "To get Insurance Policy items to display correctly, download the CustomFieldMap file from Static Resources, then install it as a DataPack.")

## Optional Tasks for all Releases

These tasks haven't changed since the Spring '21 release. If you're on a release after Spring '21 and you've completed these post-upgrade tasks before, you don't have to complete these tasks again.

Insurance Managed Package

-   [Deep Product Cloning for Insurance](https://help.salesforce.com/s/articleView?id=ind.insurance_deep_product_cloning_ins.htm&language=en_US&type=5 "You can configure Insurance to deep clone an insurance policy product. A deep clone includes the coverage specs, insured item specs, rating facts, rules, attributes, and pricebook entries of the policy product.")
-   [Add Custom Setting Values to Enable Platform Cache](https://help.salesforce.com/s/articleView?id=ind.insurance_add_custom_setting_values_to_enable_platform_cache.htm&language=en_US&type=5 "To enable caching, you must first enable the platform cache in your org. Allocate a minimum of 5 MB of cache space to Organization Level Cache.")
-   [Set the ShareProductImage Custom Setting for Insurance](https://help.salesforce.com/s/articleView?id=ind.insurance_set_shareproductimage_custom_setting_for_vlocity_insurance_and_vlocity_health.htm&language=en_US&type=5 "You can turn on the ShareProductImage custom setting to support product image sharing.")
-   [Enable Push Attributes in Batch Mode](https://help.salesforce.com/s/articleView?id=ind.insurance_enable_push_attribute_in_batch_mode.htm&language=en_US&type=5 "If your product spec is referenced by a large number of products and you're hitting Salesforce limits in push attribute, you can enable push attributes in batch mode.")

-   **[Add Picklist Values for Insurance Releases Spring '21 Through Winter '25](https://help.salesforce.com/s/articleView?id=ind.insurance_combined_picklist_values_230_thru_246.htm&language=en_US&type=5)**  
    Add values to picklist fields on several objects used with Insurance.
-   **[Manage Picklist Values in the Attribute Class Field of Vlocity Attribute Object for Insurance Releases Spring '21 Through Winter '25](https://help.salesforce.com/s/articleView?id=ind.insurance_combined_manage_picklist_values_in_attribute_class_field.htm&language=en_US&type=5)**  
    Change the label and edit the API name of several values in the Attribute Class picklist on the Vlocity Attribute Object.
-   **[Add Fields to Object Field Sets for Insurance Release Spring '21 Through Winter '25](https://help.salesforce.com/s/articleView?id=ind.insurance_combined_add_fields_to_object_field_sets.htm&language=en_US&type=5)**  
    Add fields to field sets on several objects used with Insurance.
-   **[Create Insurance Permission Sets](https://help.salesforce.com/s/articleView?id=ind.insurance_create_insurance_permission_sets.htm&language=en_US&type=5)**  
    Use anonymous Apex to create Insurance Permission Sets.
-   **[Add Picklist Values for Insurance Industries Extension Releases Spring '21 Through Winter '25](https://help.salesforce.com/s/articleView?id=ind.insurance_combined_picklist_values_230_thru_246_iie.htm&language=en_US&type=5)**  
    Add values to picklist fields on several objects used with the Insurance Industries Extension.
-   **[Add Fields to Object Field Sets for Insurance Industries Extension Releases Spring '21 Through Winter '25](https://help.salesforce.com/s/articleView?id=ind.insurance_add_fields_to_object_field_sets_iie.htm&language=en_US&type=5)**  
    Add fields to field sets on several objects used with Insurance Industries Extension.
-   **[Activate Record Pages From the Managed Package for Insurance Industries Extension Releases Spring '21 Through Winter '25](https://help.salesforce.com/s/articleView?id=ind.insurance_combined_activate_record_pages_from_the_managed_package_for_iie.htm&language=en_US&type=5)**  
    Clone and activate the pre-configured record pages that are installed automatically in the managed package.
-   **[Create Insurance Industries Extension Permission Sets](https://help.salesforce.com/s/articleView?id=ind.insurance_create_insurance_industries_extension_permission_sets.htm&language=en_US&type=5)**  
    Use anonymous Apex to create Insurance Industries Extension Permission Sets.
-   **[Manage Picklist Values in the Status Field of the Claim Line Item Object](https://help.salesforce.com/s/articleView?id=ind.insurance_manage_picklist_values_in_the_status_field_of_claim_line_item_object.htm&language=en_US&type=5)**  
    Deactivate Status picklist values and set the default value of the Status on the Claim Line Item object.
-   **[Add Expression Set to the Rating Procedure Type Picklist for the Product Record Type](https://help.salesforce.com/s/articleView?id=ind.insurance_add_expression_set_to_the_rating_procedure_type_picklist_for_the_product_record_type.htm&language=en_US&type=5)**  
    Add Expression Set to the Rating Procedure Type picklist for the Product record type in the Product object.
-   **[Update the Claim Line Item's Record Type Status](https://help.salesforce.com/s/articleView?id=ind.insurance_update_the_claim_line_item_s_record_type_status.htm&language=en_US&type=5)**  
    For the Claim Line Item record type, add values to the Status picklist.
-   **[Install OmniScript Template DataPacks for Insurance](https://help.salesforce.com/s/articleView?id=ind.insurance_install_omniscript_template_datapacks_for_vlocity_insurance_and_vlocity_health.htm&language=en_US&type=5)**  
    OmniScript templates control the look, feel, and some of the behavior of Insurance OmniScripts.
-   **[Activate Record Pages From the Managed Package for Insurance](https://help.salesforce.com/s/articleView?id=ind.insurance_activate_record_pages_from_the_managed_package_for_vlocity_insurance.htm&language=en_US&type=5)**  
    Clone and activate the pre-configured record pages that are installed automatically in the managed package.
-   **[Enable Record Types for Insurance](https://help.salesforce.com/s/articleView?id=ind.insurance_enable_record_types_for_vlocity_insurance.htm&language=en_US&type=5)**  
    Enabling record types for profiles gives users with that profile access to the record type. Use these steps to enable the Insurance record types listed in the table below.
-   **[Create and Set the RetainProductAttribJSON Custom Setting for Insurance](https://help.salesforce.com/s/articleView?id=ind.insurance_create_and_set_the_retainproductattribjson_custom_setting_for_vlocity_insurance_and_vlocity_health.htm&language=en_US&type=5)**  
    Most insurance companies use lots of attributes as part of insurance products. Unless you're planning a special setup that will not use attributes much, or you're already using information saved by `JSONAttribute` `__c`, create a custom setting called `RetainProductAttribJSON` and set it to `false`. This keeps `JSONAttribute__c` from saving attributes and speeds up your users' experience.
-   **[Add the Create New Version Button to Calculation Matrix and Calculation Procedure Version Pages](https://help.salesforce.com/s/articleView?id=ind.insurance_add_the_create_new_version_button_to_vlocity_calculation_matrix_and_calculation_procedure_version_pages.htm&language=en_US&type=5)**  
    The buttons that let you create new versions of calculation matrices and calculation procedures exist in Insurance, but they're not included in the page layouts by default.
-   **[Set Up Custom Field Mapper for Insurance](https://help.salesforce.com/s/articleView?id=ind.insurance_set_up_custom_field_mapper_ins_task.htm&language=en_US&type=5)**  
    To get Quote Line Items to display correctly, download the CustomFieldMap file from Static Resources, then install it as a DataPack.
-   **[Set Up Custom Field Mapper for Insurance Industries Extension](https://help.salesforce.com/s/articleView?id=ind.insurance_set_up_custom_field_mapper_iie_task.htm&language=en_US&type=5)**  
    To get Insurance Policy items to display correctly, download the CustomFieldMap file from Static Resources, then install it as a DataPack.
-   **[Upgrade Product Attribute Set Value Rules for Insurance](https://help.salesforce.com/s/articleView?id=ind.insurance_upgrade_product_attribute_set_value_rules_for_vlocity_insurance_and_vlocity_health.htm&language=en_US&type=5)**  
    Fix any set value rules with incompatible or unsupported methods.
-   **[Assign Permission Sets to the Analytics Integration User](https://help.salesforce.com/s/articleView?id=ind.insurance_assign_permission_sets_to_the_analytics_integration_user.htm&language=en_US&type=5)**  
    If your org uses Tableau CRM for Insurance, assign permission sets to the Analytics Integration User.
-   **[Run Batch Jobs for Insurance](https://help.salesforce.com/s/articleView?id=ind.insurance_run_batch_jobs_for_vlocity_insurance.htm&language=en_US&type=5)**  
    Insurance provides several Apex batch jobs that correct incomplete or erroneous Insurance records in your org. Run these batch jobs to initiate them.
-   **[Set the Default Value of the Premium Frequency Field on the Insurance Policy Object](https://help.salesforce.com/s/articleView?id=ind.insurance_set_the_default_value_of_the_premium_frequency_field_on_the_insurance_policy_object.htm&language=en_US&type=5)**  
    Set the default value of the Insurance Policy object's Premium Frequency picklist to Annually.
-   **[Set Up Custom Field Mapper for Insurance Industries Extension](https://help.salesforce.com/s/articleView?id=ind.insurance_set_up_insurance_industries_extension_custom_field_mapper.htm&language=en_US&type=5)**  
    To get Insurance Policy items to display correctly, download the CustomFieldMap file from Static Resources, then install it as a DataPack.
-   **[Delete Existing Insurance Industries Extension Mappings](https://help.salesforce.com/s/articleView?id=ind.insurance_delete_existing_insurance_industries_extension_mappings.htm&language=en_US&type=5)**  
    Before you install new mappings, delete any existing Insurance Industries Extension mappings.
-   **[Download and Install the FSCCustomFieldMap File](https://help.salesforce.com/s/articleView?id=ind.insurance_download_and_install_the_fsccustomfieldmap_file.htm&language=en_US&type=5)**  
    To get all of the great mappings you need for Insurance Industries Extension objects and fields, download and install the FSCCustomFieldMap file.
-   **[Verify the CustomFieldMap for Insurance Policy](https://help.salesforce.com/s/articleView?id=ind.insurance_verify_the_customfieldmap_for_insurance_policy.htm&language=en_US&type=5)**  
    After you install the FSCCustomFieldMap file, verify the custom field mappings for the Insurance Policy object.
-   **[Verify the CustomFieldMap for Quote](https://help.salesforce.com/s/articleView?id=ind.insurance_verify_the_customfieldmap_for_quote.htm&language=en_US&type=5)**  
    After you install the FSCCustomFieldMap file, verify the custom field mappings for the Quote object.
-   **[Deep Product Cloning for Insurance](https://help.salesforce.com/s/articleView?id=ind.insurance_deep_product_cloning_ins.htm&language=en_US&type=5)**  
    You can configure Insurance to deep clone an insurance policy product. A deep clone includes the coverage specs, insured item specs, rating facts, rules, attributes, and pricebook entries of the policy product.
-   **[Add Custom Setting Values to Enable Platform Cache](https://help.salesforce.com/s/articleView?id=ind.insurance_add_custom_setting_values_to_enable_platform_cache.htm&language=en_US&type=5)**  
    To enable caching, you must first enable the platform cache in your org. Allocate a minimum of 5 MB of cache space to Organization Level Cache.
-   **[Set the ShareProductImage Custom Setting for Insurance](https://help.salesforce.com/s/articleView?id=ind.insurance_set_shareproductimage_custom_setting_for_vlocity_insurance_and_vlocity_health.htm&language=en_US&type=5)**  
    You can turn on the ShareProductImage custom setting to support product image sharing.
-   **[Enable Push Attributes in Batch Mode](https://help.salesforce.com/s/articleView?id=ind.insurance_enable_push_attribute_in_batch_mode.htm&language=en_US&type=5)**  
    If your product spec is referenced by a large number of products and you're hitting Salesforce limits in push attribute, you can enable push attributes in batch mode.

Did this article solve your issue?

Let us know so we can improve!

YesNo