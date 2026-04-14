---
title: "Set Up Search for Identity Verification"
source: "https://help.salesforce.com/s/articleView?id=ind.insurance_set_up_search_for_identity_verification_omnistudio.htm&language=en_US&type=5"
scraped: "2026-04-14"
filter: "ind.insurance_"
---# Set Up Search for Identity Verification

Set Up Search for Identity Verification[](https://help.salesforce.com/s?language=en_US)

You are here:

1.  [Salesforce Help](/s/?language=en_US)
2.  [Docs](/s/products?language=en_US)
3.  [Digital Insurance](https://help.salesforce.com/s/articleView?id=ind.insurance_admin_standard.htm&language=en_US&type=5)

# Set Up Search for Identity Verification

When an agent receives a call, the first thing they do is search for the caller. To set up how the search works, such as whether the search is text-based or object-based, the data source to query, and more, create an Identity Verification Process Detail record. You can also specify the minimum number of additional verifying questions to ask a caller.

The default Identity Verification Process Detail record enables text-based search of account records in Salesforce and uses Id as the unique identifier for search records. To configure a different object for identity verification, or to require that more than one additional verifier is checked, or to not require additional verifiers, create a process detail record.

To verify both a caller and the person they represent, you must create at least two Identity Verification Process Detail records:

-   One to search and verify the caller
    
-   The other to search and verify the person the call is about
    

Then, link the two records using the Linked Identity Verification Process Detail field in the process detail record for the caller. The data required to perform the secondary verification using the linked subflow, Verify Linked Caller Identity, is defined in the linked process detail record. For example, suppose the data to verify authorized representatives resides in Contact records and the data to verify their customers resides in Account records. You would create two process detail records, one for the Contact object and the other for the Account object. Specify the process detail record for the Account object in the Linked Identity Verification Process Detail field of the process detail record for Contact.

Note

If your org is Person Account-enabled and you use the Account object for identity verification, person account records are queried. Otherwise, business account records are queried.

1.  In the Identity Verification admin setup assistant, click **Set Up Search**.
    
2.  Click **New Identity Verification Process Detail**.
    
3.  Enter a label and name for the record.
    
    The Name field stores the unique name of the record used by the API and managed packages. The name must begin with a letter and use only alphanumeric characters and underscores. It can’t end with an underscore or have two consecutive underscores.
    
4.  Select the relevant record name in the Identity Verification Process Definition field.
    
5.  Enter a search sequence number.
    
    The search sequence number determines the order in which the Search Type picklist values are displayed to your users in the identity verification flow.
    
6.  Select the data source.
    
    Possible values are External and Salesforce. If the caller records and verification data reside in Salesforce, select **Salesforce**. If they are in some other electronic health records system, select **External**.
    
7.  Select the search type.
    
    Text-based search enables the agent to enter search keywords in the search field. In object-based search, a CCA uses available fields to search for data in Salesforce.
    
    If your data resides in an external data source and you’re using the Verify Customer Identity flow template, then use the text-based search type.
    
8.  Enter the object used for the verification process.
    
9.  Enter the field that uniquely identifies a record.
    
    For example, ID, policy number, and account number uniquely identify records.
    
10.  Enter conditions used to filter the search results.
     
     For example, if you want to search only Person Account records, enter `isPersonAccount=true`.
     
     Use the AND operator to enter multiple conditions. The OR operator isn’t currently supported.
     
11.  Enter the values used to sort and order the search results.
     
     For example, if you want to sort the results by policy date and arrange them in a descending order, enter `PolicyDate__c` Desc.
     
12.  Enter the minimum number of additional verifying questions that must be answered by the caller.
     
     For example, if you want callers to answer at least one of the configured additional questions, enter 1.
     
13.  If you want to use an external data source to search for caller records and to get verification data, select the custom Apex class.
     
14.  Mark the record active.
     
15.  If your process requires two levels of verification, select the linked Identity Verification Process Detail record.
     
16.  Save your changes.
     

Did this article solve your issue?

Let us know so we can improve!

YesNo