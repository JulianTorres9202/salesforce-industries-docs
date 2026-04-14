---
title: "Add the Insurance Group Census Lightning Web Component"
source: "https://help.salesforce.com/s/articleView?id=ind.insurance_group_benefits_core_group_census_lwc.htm&language=en_US&type=5"
scraped: "2026-04-14"
filter: "ind.insurance_"
---# Add the Insurance Group Census Lightning Web Component

Add the Insurance Group Census Lightning Web Component[](https://help.salesforce.com/s?language=en_US)

You are here:

1.  [Salesforce Help](/s/?language=en_US)
2.  [Docs](/s/products?language=en_US)
3.  [Digital Insurance](https://help.salesforce.com/s/articleView?id=ind.insurance_admin_standard.htm&language=en_US&type=5)

# Add the Insurance Group Census Lightning Web Component

The Insurance Group Census Lightning web component gives users a straightforward way to incorporate census data into group census. After a Salesforce admin configures the component and incorporates it into workflows, insurance carrier administrators and brokers upload census data and fix data exceptions.

### Required Editions

<table class="slds-table slds-table_bordered slds-m-bottom_small edition" lwc-3eigj2skqo3=""><colgroup lwc-3eigj2skqo3=""><col style="width:100%" lwc-3eigj2skqo3=""></colgroup><tbody lwc-3eigj2skqo3=""><tr class="" lwc-3eigj2skqo3=""><td style="vertical-align:top;" class="slds-cell-wrap" lwc-3eigj2skqo3="">Available in: Lightning Experience</td></tr><tr class="" lwc-3eigj2skqo3=""><td style="vertical-align:top;" class="slds-cell-wrap" lwc-3eigj2skqo3="">Available in: <strong class="uicontrol" lwc-3eigj2skqo3="">Professional</strong>, <strong class="uicontrol" lwc-3eigj2skqo3="">Enterprise</strong>, and<strong class="uicontrol" lwc-3eigj2skqo3=""> Unlimited</strong> Editions of Digital Insurance with Digital Insurance Product Admin Add On, Digital Insurance Group Benefits AddOn, Digital Insurance Group Enrollment AddOn,Digital Insurance Group Benefits Customer Community AddOn, and Digital Insurance Group Benefits Partner Community AddOn licenses</td></tr></tbody></table>

| User Permissions Needed |
| --- |
| To add a lightning web component | Digital Insurance Group Census Quote Contract Management, Digital Insurance Group Enrollment, Digital Insurance Group Census Management Customer Community, Digita lInsurance Group Enrollment Customer Community, Digital Insurance Group Census Quote Contract Management Partner Community, and Digital Insurance Group Enrollment Partner Community |

1.  From the Group Census record details page, go to Setup and select **Edit Page**.
2.  In the Lightning App Builder, add a new custom tab and give it a descriptive label. For example, Census Data.
3.  Drag the Insurance Group Census component onto the new tab in the page layout.
4.  Specify input parameters for the Insurance Group Census Lightning web component properties.
    
    | Input property | purpose | default value |
    | --- | --- | --- |
    | Census Members List Columns | Specifies the list of group census member standard or custom fields to show in the grid used for censusType Quote. | Name, FirstName, Lastname, Birth Date, Gender , Status |
    | Census Members List Columns for Enrollment Census | Specifies the list of group census member standard or custom fields to show in the grid. censusType Enrollment | 
    Name, FirstName, Lastname, Group Class, Enrollment, Status
    
    Enrollment (shows the select root plans)
    
     |
    | Matching Keys for Duplicate Detection | Specifies the list of group census member fields to be used for duplicate detection along with First Name, Last Name and Association With Primary Member. | FirstName, Lastname, GroupCensusId, AssociationWithPrimaryMbr |
    | Census Members List Details for Side Panel | Specifies the list of group census member fields on the side panel. | Shows all the fields by default and if selections are made only selected fields will show |
    | Batch Job Name | The batch job definition name that's used to execute a custom process flow for census with Quoting census type. | NA |
    | Batch Job Name for Enrollment Census | The batch job definition name that's used to execute a custom process flow for census with Enrollment census type. | NA |
    | Batch Size for Upload Census Data without Plans | Maximum members without plan information to process for each batch from the CSV file. | 2000 |
    | Chunk Size for Upload Census Data With Plans | Maximum members with plan information to process for each batch from the CSV file. | 25 |
    | Execute Configuration Rules | Runs configuration rules when this option is checked. | False |
    
5.  Save your changes.

Administrators and brokers can now use the component to upload census files and review results.

Did this article solve your issue?

Let us know so we can improve!

YesNo