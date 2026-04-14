---
title: "Upload Group Census Data"
source: "https://help.salesforce.com/s/articleView?id=ind.insurance_group_benefits_core_upload_group_census_data.htm&language=en_US&type=5"
scraped: "2026-04-14"
filter: "ind.insurance_"
---# Upload Group Census Data

Upload Group Census Data[](https://help.salesforce.com/s?language=en_US)

You are here:

1.  [Salesforce Help](/s/?language=en_US)
2.  [Docs](/s/products?language=en_US)
3.  [Digital Insurance](https://help.salesforce.com/s/articleView?id=ind.insurance_admin_standard.htm&language=en_US&type=5)

# Upload Group Census Data

Use a csv file to upload census information such as group members and dependents into a group census.

### Required Editions

<table class="slds-table slds-table_bordered slds-m-bottom_small edition" lwc-3eigj2skqo3=""><colgroup lwc-3eigj2skqo3=""><col style="width:100%" lwc-3eigj2skqo3=""></colgroup><tbody lwc-3eigj2skqo3=""><tr class="" lwc-3eigj2skqo3=""><td style="vertical-align:top;" class="slds-cell-wrap" lwc-3eigj2skqo3="">Available in: Lightning Experience</td></tr><tr class="" lwc-3eigj2skqo3=""><td style="vertical-align:top;" class="slds-cell-wrap" lwc-3eigj2skqo3="">Available in: <strong class="uicontrol" lwc-3eigj2skqo3="">Professional</strong>, <strong class="uicontrol" lwc-3eigj2skqo3="">Enterprise</strong>, and<strong class="uicontrol" lwc-3eigj2skqo3=""> Unlimited</strong> Editions of Digital Insurance with Digital Insurance Product Admin Add On, Digital Insurance Group Benefits AddOn, Digital Insurance Group Enrollment AddOn,Digital Insurance Group Benefits Customer Community AddOn, and Digital Insurance Group Benefits Partner Community AddOn licenses</td></tr></tbody></table>

| User Permissions Needed |
| --- |
| To upload group census data | Digital Insurance Group Census Quote Contract Management, Digital Insurance Group Enrollment, Digital Insurance Group Census Quote Contract Management Partner Community, and Digital Insurance Group Enrollment Partner Community |

Keep these guidelines in mind.

-   Don’t include an extra empty line at the end of the CSV file.
-   Remove trailing spaces before commas in column headers to improve upload performance.
-   Define Association with Primary Member values such as Self, Spouse, Child, Parent, Parent-in-law, or Other.
-   Ensure that the primary member (Self) is followed by all their dependents in the file.
-   The census upload uses First Name, Last Name, and Association with Primary Member from the CSV file to identify members when updating personal information or adding new members.
-   Define your own duplicate detection criteria by setting the Duplicate Detection Fields property when you add the Insurance Group Census Lightning web component. Provide unique values in these fields to avoid matching multiple records to the same member.
-   The [group class](https://help.salesforce.com/s/articleView?id=ind.insurance_group_benefits_core_create_group_class.htm&language=en_US&type=5 "Group classes are groups of members who all receive similar benefits. Examples of group classes include Executives, Managers, and Directors.") that you assign to the primary member is automatically applied to their dependents even if dependents have a different value in the Group Class field.
-   Either assign a group class to all members in the census or leave the field blank for all members.
-   You can’t update the group class for an existing member. To change it, delete the member and add them again with the correct value.

1.  From the App Launcher, find and select **Group Census**.
2.  On the group census details page, click the **Census Members** tab.
    
    Depending on your organization’s customization, this tab may have a different label.
    
3.  Click **Add Member** to manually add an individual census member.
4.  Click **Upload Census** to upload census data from a CSV file. You can upload a new census or reuse an existing one.
5.  If you’re uploading a new census, map fields in the source file to fields in Group Census Member records.
    
    -   The number of fields to map matches the number of columns in the source file.
    -   Field labels are the same as the column headings in the file.
    -   Field values in dropdowns are populated from the Group Census Member object.
        
        Note If you select Census Type as Enrollment, use the Contract Group Plan field for each plan column to map the plans from the CSV file.
        
    
6.  Save your changes. Uploaded census members appear in a hierarchical tree view.
7.  (Optional) If errors occur, download the error file from the Notes & Attachments section to review and correct issues.
8.  Review the group census group class summary record under the Related tab to view statistics about the group class members for the associated group census.

Did this article solve your issue?

Let us know so we can improve!

YesNo