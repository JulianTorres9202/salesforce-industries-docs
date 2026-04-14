---
title: "Verify an Insurance Customer and Their Representative"
source: "https://help.salesforce.com/s/articleView?id=ind.insurance_verify_insurance_customer_and_their_representative.htm&language=en_US&type=5"
scraped: "2026-04-14"
filter: "ind.insurance_"
---# Verify an Insurance Customer and Their Representative

Verify an Insurance Customer and Their Representative[](https://help.salesforce.com/s?language=en_US)

You are here:

1.  [Salesforce Help](/s/?language=en_US)
2.  [Docs](/s/products?language=en_US)
3.  [Digital Insurance](https://help.salesforce.com/s/articleView?id=ind.insurance_admin_standard.htm&language=en_US&type=5)

# Verify an Insurance Customer and Their Representative

Verify a customer's identity before processing their requests involving sensitive information, and store details about the interaction. If an engagement is about someone other than the customer, you can perform verification for both people.

When you accept a call over Open CTI or Omni-Channel, an engagement interaction record page opens. If a customer or their representative is calling or messaging from a registered phone number, the Initiating Attendee field on the record page is auto-populated. If a customer or their representative initiates an in-person engagement, you must create an Engagement Interaction record and then you can verify their identity.

1.  From the App Launcher, find and select **Engagement Interactions**.
2.  Click **New**.
3.  Enter the initiating attendee. This is the account or the contact for the customer who initiated the engagement. If the customer is new, create a lead record.
4.  Enter the start date and time for the engagement.
5.  Select the channel of communication.
6.  Click **Save**.
7.  Talk to or chat with the customer or the representative to understand the purpose of the engagement, then select a reason and click **Next**. If the engagement isn't related to confidential information, there's no need to verify the customer or the representative's identity. Process the customer's request.
8.  Select who the engagement is about and click **Next**. If the engagement is about the customer, verify their identity. If verification succeeds, process their request. If the engagement is about someone else, verify the identity of the representative. If verification succeeds, verify the identity of the customer the initiating attendee is authorized to represent. Only when the second-level verification succeeds, process the representative's request.
9.  Select the search type, search for the customer using keywords or available fields, and then click **Next**. You can use the search type menu to specify which data to search. If the engagement is about someone else, search for the person initiating the engagement even if their number was registered.
10.  Select the relevant search result and click **Next**.
11.  Ask questions to verify the required and additional information. For example, your verification process could require asking for a person's account name, birthdate, and driver's license number. Your admin configures the questions. Verification succeeds only if the person correctly answers all the questions in the required information section and the required number of questions in the additional information section. If the engagement is about the customer, verification ends here. Upon successful verification, process their request. If the engagement is about someone else, you must verify the identity of the person the engagement is about.
12.  Select the search type, search for the person using keywords or available fields, and then click **Next**.
13.  Select the relevant search result and click **Next**.
14.  Ask questions to verify the required and additional information.
     
     Verification succeeds only if the customer's representative correctly answers all the questions related to the customer in the required information section and the required number of questions in the additional information section. If verification succeeds, you're informed to process the representative's request and you're redirected to the relevant record page. In the case of the unidentified representative, depending on whether the verification was successful, the Engagement Interaction record is automatically updated. If verification fails, you're asked to stop processing the representative's request.
     

Did this article solve your issue?

Let us know so we can improve!

YesNo