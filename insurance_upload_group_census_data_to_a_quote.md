---
title: "Upload Group Census Data to a Quote"
source: "https://help.salesforce.com/s/articleView?id=ind.insurance_upload_group_census_data_to_a_quote.htm&language=en_US&type=5"
scraped: "2026-04-14"
filter: "ind.insurance_"
---# Upload Group Census Data to a Quote

Upload Group Census Data to a Quote[](https://help.salesforce.com/s?language=en_US)

You are here:

1.  [Salesforce Help](/s/?language=en_US)
2.  [Docs](/s/products?language=en_US)
3.  [Digital Insurance](https://help.salesforce.com/s/articleView?id=ind.insurance_admin_standard.htm&language=en_US&type=5)

# Upload Group Census Data to a Quote

To incorporate census information into a Group Benefits quote, upload it. The group member and dependent data in the census is used to create accurate quotes.

1.  On a quote, select one or more insurance products, such as a Dental Premium plan.
2.  Click Upload Census to upload a new or existing CSV file with census data. The system uses the census data to calculate a rating for the selected products.
    
    You can choose an existing census that's already been uploaded or you can upload a new census.
    
3.  If you're uploading a new census, map fields in source data to fields in Group Census Member records.
    
    -   The number of fields to map is the same as the number of columns in the source file.
        
    -   The field labels are the same as the column headings in the source file.
        
    -   The field values displayed in the dropdown lists are populated from the Group Census Member object.
        
    
4.  Review and correct any data errors. If you skip this step, records with errors are not saved as group census members.
    
    Uploaded group census members appear in a hierarchical tree view.
    

Did this article solve your issue?

Let us know so we can improve!

YesNo