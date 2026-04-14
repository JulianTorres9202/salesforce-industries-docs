---
title: "Verify Identity"
source: "https://help.salesforce.com/s/articleView?id=ind.insurance_verify_identity_omnistudio.htm&language=en_US&type=5"
scraped: "2026-04-14"
filter: "ind.insurance_"
---# Verify Identity

Verify Identity[](https://help.salesforce.com/s?language=en_US)

You are here:

1.  [Salesforce Help](/s/?language=en_US)
2.  [Docs](/s/products?language=en_US)
3.  [Digital Insurance](https://help.salesforce.com/s/articleView?id=ind.insurance_admin_standard.htm&language=en_US&type=5)

# Verify Identity

How you verify the identity of a caller depends on how your admin has configured the process.

Verify a caller’s identity before processing their requests involving sensitive information, and store details about the interaction. Additionally, if a call is about someone other than the caller, you’re able to perform verification for both people.

1.  Click **Phone** from the utility bar.
    
    Your org has a mock integration with the Salesforce Computer Telephone Integration adapter that mimics a call.
    
    Note
    
    If your organization hasn’t implemented computer telephony integration (CTI), you must first create a blank Engagement Interaction record to access the identity verification flow.
    
2.  Click Login and then click the telephone icon.
3.  Click **Accept**.
    
    When you accept a call, an Engagement Interaction record page opens. Depending upon whether the initiating attendee (the caller) is calling from a registered or unregistered number, the Initiating Attendee field in the record page is auto-populated or left empty.
    
4.  Talk to the caller to understand the purpose of the call, then select a reason, and click **Next**.
5.  Select who the call is about and click **Next**.
    
    Only when the second-level verification succeeds, process the caller’s request.
    
    -   If the call is about the caller, verify the caller’s identity. If verification succeeds, process their request.
    -   If the call is about someone else, you have to first verify the identity of the caller.
    -   If verification succeeds, you have to verify the identity of the person the caller’s authorized to represent.
    
6.  Select the search type, search for the caller using keywords or available fields, and click **Next**.
    
    The search type menu enables you to specify which data is to be searched.
    
    Note
    
    If the call’s about someone else, you have to search for the caller even if the caller’s number was registered.
    
7.  Select the relevant search result and click **Next**.
8.  Ask questions to verify the required and additional information.
    
    For example, your verification process could require asking a caller's account name, birthdate, and driver's license number. The admin configures the questions.
    
    Verification succeeds only if the caller correctly answers all the questions in the required information section and the required number of questions in the additional information section. If the call is about the caller, verification ends here. Upon successful verification, process the caller’s request. If the call is about someone else, you have to now verify the identity of the person the call is about.
    
9.  Select the search type, search for the caller using keywords or available fields, and click **Next**.
    
    The search type menu enables you to specify which data is to be searched.
    
    Note
    
    If the call’s about someone else, you have to search for the caller even if the caller’s number was registered.
    
10.  Select the relevant search result and click **Next**.
11.  Ask questions to verify the required and additional information.
     
     After the user is verified, the [Client 360°](https://help.salesforce.com/s/articleView?id=ind.insurance_know_the_insurance_policy_360_console_omnistudio.htm&language=en_US&type=5 "The Insurance Policy 360° Console enables your service agents to manage interactions that streamline common tasks. For example, call service agents can use the Identity Verification feature to search accounts, verify your customers, and improve the overall customer experience.") page for the customer is displayed.
     

Did this article solve your issue?

Let us know so we can improve!

YesNo