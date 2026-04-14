---
title: "Configure the Quote Page and a Quote Workflow for Census Management"
source: "https://help.salesforce.com/s/articleView?id=ind.insurance_configure_the_quote_page_and_a_quote_workflow_for_census_management.htm&language=en_US&type=5"
scraped: "2026-04-14"
filter: "ind.insurance_"
---# Configure the Quote Page and a Quote Workflow for Census Management

Configure the Quote Page and a Quote Workflow for Census Management[](https://help.salesforce.com/s?language=en_US)

You are here:

1.  [Salesforce Help](/s/?language=en_US)
2.  [Docs](/s/products?language=en_US)
3.  [Digital Insurance](https://help.salesforce.com/s/articleView?id=ind.insurance_admin_standard.htm&language=en_US&type=5)

# Configure the Quote Page and a Quote Workflow for Census Management

Give users a straightforward way to incorporate census data directly into a quote or configure a quote workflow by incorporating the Quote Census Lightning web component into an OmniScript.

Important

These configurations apply to the Group Census and Group Census Member objects in the Salesforce data model.

## Add the Quote Census LWC to the Quote Page

In Lightning App Builder, add a custom tab, and then drop the **Insurance Census** component into it.

## Configure a Quote Workflow in an OmniScript

Create an OmniScript that walks users through uploading census data for Group Benefits quotes and that creates the related objects in the Salesforce data model.

| 
Typical Steps in a Quote Workflow OmniScript

 |
| --- |
| 

1

 |  | 

Data Mapper Extract action retrieves details about the user running the OmniScript.

 |
| 

2

 |  | 

Data Mapper Extract action retrieves record type metadata for Account, Contact, and Group Census objects.

 |
| 

3

 |  | 

Form prompts the user for information about the Account (group) and Contact. In this example, the form requires unique data for Account Name, Contact Name, and Email.

 |
| 

4

 |  | 

Form prompts the user for qualifying information about the group.

 |
| 

5

 |  | 

Data Mapper Post Action uses data collected in previous steps to create Account, Contact, Opportunity, and Group Census objects.

 |
| 

6

 |  | 

Set Values step sets censusId and accountId to a variable based on the response in the previous step.

 |
| 

7

 |  | 

Step with the insOsGroupCensus Lightning web component prompts users to upload censusMembers data using a CSV file. See [Input Parameters](https://help.salesforce.com/s/articleView?id=ind.insurance_configure_the_quote_page_and_a_quote_workflow_for_census_management.htm&language=en_US&type=5#insurance_configure_the_quote_page_and_a_quote_workflow_for_census_management__section-378).

 |
| 

8

 |  | 

Data Mapper Extract action retrieves ratingfactId from ratingfactcode.

 |
| 

9

 |  | 

Remote Action calls the `InsCensusServiceStd.setMemberRatingfacts()` service to set AttributeSelectedValues for each of the censusMembers.

 |
| 

10

 |  | 

Data Mapper Extract Action retrieves the Rating Type, age-based or composite-based.

 |
| 

11

 |  | 

Form prompts the user for categories of plans to select, such as Medical, Dental, and Vision. The form accepts one or more selections.

 |
| 

12

 |  | 

Integration Procedure Action retrieves `userInputs` to use for rating the selected products in the next steps. The `userInputs` is retrieved from AttributeSelectedValues for each of the censusMembers.

 |
| 

13

 |  | 

Set Values and Steps prompt users to select plans.

 |
| 

14

 |  | 

Form shows the names and prices of the products the user added to the cart.

 |
| 

15

 |  | 

Omnistudio Data Mapper Transform Action transforms data into inputs for the next step.

 |
| 

16

 |  | 

Remote Action calls the `InsQuoteService.createUpdateQuote()` service to create Quote and QuoteLineItem objects.

 |
| 

17

 |  | 

Step confirms the process is done.

 |
| 

18

 |  | 

Seed Data JSON property values on the Setup tab pre-fill OmniScript fields with data.

 |

[](https://help.salesforce.com/s?language=en_US)

## Input Parameters

In your enrollment workflow OmniScript, specify input parameters for the insOsGroupCensus Lightning web component properties.

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

census-id

 | 

Yes

 | 

—

 | 

Retrieve census members.

 |
| 

items-per-page

 | 

No

 | 

10

 | 

Rows displayed per page.

 |
| 

census-mem-field-set

 | 

No

 | 

StandardFieldset

 | 

Fieldset used when editing census member details to get the fields for uploading the members.

 |
| 

census-summary-field-set

 | 

No

 | 

StandardFieldset

 | 

Fieldset for census summary fields details.

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

duplicate-keys

 | 

No

 | 

FirstName, Lastname, Email, GroupCensusId

 | 

Determine members that already exist in the table, and execute an update instead of an insert.

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

parallel-batch-requests

 | 

No

 | 

5

 | 

Count of parallel requests of a batch job to upload member data.

 |

Did this article solve your issue?

Let us know so we can improve!

YesNo