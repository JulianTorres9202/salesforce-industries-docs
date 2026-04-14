---
title: "Get to Know the Default Configuration and Possible Customization for Bulk Enrollment OmniScript"
source: "https://help.salesforce.com/s/articleView?id=ind.insurance_get_to_know_the_default_configuration_and_possible_customization_for_bulk_enrollment_os.htm&language=en_US&type=5"
scraped: "2026-04-14"
filter: "ind.insurance_"
---# Get to Know the Default Configuration and Possible Customization for Bulk Enrollment OmniScript

Get to Know the Default Configuration and Possible Customization for Bulk Enrollment OmniScript[](https://help.salesforce.com/s?language=en_US)

You are here:

1.  [Salesforce Help](/s/?language=en_US)
2.  [Docs](/s/products?language=en_US)
3.  [Digital Insurance](https://help.salesforce.com/s/articleView?id=ind.insurance_admin_standard.htm&language=en_US&type=5)

# Get to Know the Default Configuration and Possible Customization for Bulk Enrollment OmniScript

Understand the default configuration of bulk enrollment OmniScript and customize it according to your business requirement.

## Configure an Enrollment Workflow in an OmniScript

Create an OmniScript that walks users through uploading census data for Group Benefits enrollments and that creates the related objects in the Salesforce data model.

| 
Typical Steps in an Enrollment Workflow OmniScript

 |
| --- |
| 

1

 |   | 

Data Mapper Extract Action retrieves details about the Account and Contract objects. `AccountId` is used as input for the OmniScript.

 |
| 

2

 |   | 

Data Raptor Post Action uses data collected in the previous step to create a Group Census object.

 |
| 

3

 |  | 

Set Values step sets `censusId` to a variable based on the response in the previous step.

 |
| 

4

 |  | 

Step with the insOsEnrollmentCensus Lightning web component prompts users to upload censusMembers data using a CSV file. See [Input Parameters](https://help.salesforce.com/s/articleView?id=ind.insurance_get_to_know_the_default_configuration_and_possible_customization_for_bulk_enrollment_os.htm&language=en_US&type=5#insurance_get_to_know_the_default_configuration_and_possible_customization_for_bulk_enrollment_os__section-1022).

 |
| 

5

 |  | 

Set Values step sets missing data values counts to 0.

 |
| 

6

 |   | 

Action Block that includes:

-   `updateContractCensus`: Omnistudio Data Mapper Post Action uses data collected in the previous step to update the Group Census Member Plan object.
    
-   `setMemberRatingFacts`: Remote Action calls the `InsCensusServiceStd.setMemberRatingfacts()` service to set `AttributeSelectedValues` for each of the censusMembers.
    
-   `createAccounts`: Remote Action calls the `InsCensusServiceStd.createUpdateAccounts()` service to create Person Accounts for each of the censusMembers. If Person Accounts aren't enabled in your org, use `InsCensusServiceStd.createContacts()` instead.
    

 |
| 

7

 |  | 

Set Values step prepares `parentObj` JSON that's sent to the FlexCard used in the last `EnrollmentComplete` OmniScript step. For example:

```json
"parentObj": {
  "accId": "%ContextId%",
  "timenow": "=NOW()",
  "timenowplusone": "=MOMENT(NOW()).add(2, 'minutes')",
  "userid": "%userId%"
}
```



 |
| 

8

 |  | 

Remote Action calls the `InsEnrollmentServiceStd.enrollMembers()` service to enroll each of the censusMembers in their selected plans.

 |
| 

9

 |  | 

Step uses a FlexCard with input from the `setConfirmationData` step, and confirms the process is done. Configure a FlexCard to use for this step.

 |

[](https://help.salesforce.com/s?language=en_US)

## Input Parameters

In your enrollment workflow OmniScript, specify input parameters for the insOsEnrollmentCensus Lightning web component properties.

| 
Input Property

 | 

Required

 | 

Default

 | 

Purpose

 |
| --- | --- | --- | --- |
| 

contract-id

 | 

Yes

 | 

—

 | 

Retrieve the enrollment plans/census info.

 |
| 

census-id

 | 

Yes

 | 

—

 | 

Retrieve the members.

 |
| 

items-per-page

 | 

No

 | 

10

 | 

Determines the number of employees to display on a page. The maximum number of employees per page is 15.

 |
| 

fieldset-name

 | 

No

 | 

StandardFieldset

 | 

Fieldset used when editing census member details to get the fields for uploading members.

 |
| 

plan-fieldset-name

 | 

No

 | 

—

 | 

Fieldset used for retrieving the fields from group census member plan object.

 |
| 

column-fieldset

 | 

No

 | 

GroupCensusMemberList

 | 

Fieldset used for columns in the tree grid.

 |
| 

census-template-name

 | 

No

 | 

/resource/insOsFlowCensusTemplate

 | 

URL where the census template is stored.

 |
| 

batch-size

 | 

No

 | 

1000

 | 

Count of census records in a batch.

 |
| 

parallel-batch-size

 | 

No

 | 

5

 | 

Count of parallel requests of a batch job to upload member data.

 |
| 

view-plan-coverage

 | 

No

 | 

FALSE

 | 

When set to TRUE, this property enables coverages selection in CSV file and also displays the selected coverages for each member.

 |

## Considerations for Using Bulk Enrollment OmniScript

-   The Integration Procedure in the sample OmniScript calls the `InsEnrollmentServiceStd:enrollMembersAsync` service. Add or remove remote options from the Intergration Procedure based on your requirements.
    
-   The group account may have multiple active contracts and expired contracts. The contract that's active and has been modified most recently is used for enrollment. You may choose to update the logic or provide a specific contract by modifying the OmniScript.
    
-   If there's no existing census, the census is created and saved in the **Enrollment Census** field of the Insurance Contract, This census ID is used to fetch the same census for multiple enrollment processes throughout the year for a given contract.
    
-   To avoid creating duplicate policies, the same census must be used, and do not delete the records from the Group Census Member and Group Census Member Plan entities.
    
-   In the Enrollment Census LWC, you'll see all the member records in the census, including members who are enrolled previously. You can modify the OmniScript to provide a unique census ID for each enrollment.
    
    Note Ensure not to include member details of already enrolled members in the enrollment CSV file for the current enrollment process.
    

Did this article solve your issue?

Let us know so we can improve!

YesNo