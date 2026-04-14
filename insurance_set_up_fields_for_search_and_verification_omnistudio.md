---
title: "Set Up Fields for Search and Verification"
source: "https://help.salesforce.com/s/articleView?id=ind.insurance_set_up_fields_for_search_and_verification_omnistudio.htm&language=en_US&type=5"
scraped: "2026-04-14"
filter: "ind.insurance_"
---# Set Up Fields for Search and Verification

Set Up Fields for Search and Verification[](https://help.salesforce.com/s?language=en_US)

You are here:

1.  [Salesforce Help](/s/?language=en_US)
2.  [Docs](/s/products?language=en_US)
3.  [Digital Insurance](https://help.salesforce.com/s/articleView?id=ind.insurance_admin_standard.htm&language=en_US&type=5)

# Set Up Fields for Search and Verification

The Identity Verification Process Field object enables you to determine what an agent sees, such as which fields appear in search results or which fields must be verified. Create an Identity Verification Process Field record for each field that is part of your identity verification process.

Seven process field records are created for you.

-   Account name, birth date, and phone number are search results fields.
    
-   Account name and birth date are required verification fields.
    
-   Phone number and postal code are optional verification fields.
    

You can add other verification steps. For example, to add a check for a segment of a government ID, create an additional Identity Verification Process Field record for the field that holds that information.

The Field Type and Field Name fields in a process field record work together. Suppose you want to add Account Name as a search result field. Select Result Field as the field type and enter `AccountName` as the field name. Or, to set Birth Date as a required verification field, select Required Verifier as the field type, and enter `PersonBirthdate` as the field name.

1.  In the Identity Verification admin setup assistant, click **Set Up Fields**.
    
2.  Click **New Identity Verification Process Field**.
    
3.  Enter a label and name for the record.
    
    The Name field stores the unique name of the record used by the API and managed packages. The name must begin with a letter and use only alphanumeric characters and underscores. It can’t end with an underscore or have two consecutive underscores.
    
4.  Select the related record in the Identity Verification Process Detail field.
    
5.  Select the data source.
    
6.  Select the field type of the field you want to add for identity verification.
    
    Possible values are:
    
    **Required Verifier** - To add a required verifying question
    
    **Optional Verifier** - To add an additional verifying question
    
    **Result Field** - To display in search results. For example, when an agent searches for a caller, you’d like the search results to include the account name, phone number, and email ID.
    
    **Additional Result Field** - To fetch data as part of the search query, but the data isn’t displayed in search results. For example, you want to fetch the policy number and the age of the policy owner, but don't want the agent to see this data. Write some custom logic to process this additional data.
    
7.  Enter the name of the field for the selected field type.
    
    For example, if you select Required Verifier as the field type and you want to set Account Name as the required verifier, enter `AccountName`.
    
8.  Don't enter a Field Value Formula, as this field is reserved for future use.
    
9.  Optionally, enter a custom label to replace the standard field label in the app.
    
    For example, if you'd like `PersonBirthDate` displayed as DOB, enter DOB.
    
    If necessary, translate your custom labels using Translation Workbench so that your call center agents always see those labels in their preferred language.
    
10.  Enter a sequence number for the field.
     
     The sequence number is used in ordering how fields are displayed in the verification screen.
     
11.  Mark the record active and save it.
     

Did this article solve your issue?

Let us know so we can improve!

YesNo