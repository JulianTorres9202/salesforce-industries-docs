---
title: "Terminate a Policy for a Single Member"
source: "https://help.salesforce.com/s/articleView?id=ind.insurance_terminate_single_member.htm&language=en_US&type=5"
scraped: "2026-04-14"
filter: "ind.insurance_"
---# Terminate a Policy for a Single Member

Terminate a Policy for a Single Member[](https://help.salesforce.com/s?language=en_US)

You are here:

1.  [Salesforce Help](/s/?language=en_US)
2.  [Docs](/s/products?language=en_US)
3.  [Digital Insurance](https://help.salesforce.com/s/articleView?id=ind.insurance_admin_standard.htm&language=en_US&type=5)

# Terminate a Policy for a Single Member

Terminate policies of primary members and associated dependents individually in the middle of a contract. Get notified when the termination is completed and receive a list of errors if termination couldn't be completed.

1.  From the Mid-Term Adjustments tab on the Account page, click **Terminate Member**.
2.  Search for the member policy you want to terminate, and then click **Enter**.
    
    The member details and all the associated active policies appear. If there are no active policies associated with that member, a message appears stating that there are no active policies that exist for that member.
    
3.  Enter a **Termination Date**, and then click **Terminate**.
4.  Click **Confirm & Terminate**.
    
    In the background, the `InsPolicyService:cancelPolicy` service cancels all the policies associated with the member. To learn about other tasks the service performs, see [InsPolicyService:cancelPolicy](https://help.salesforce.com/s/articleView?id=ind.insurance_inspolicyservice__cancelpolicy.htm&language=en_US&type=5 "Use this service to cancel an existing insurance policy.").
    
    When you initiate the termination process for another member, both of the tasks run asynchronously.
    

Did this article solve your issue?

Let us know so we can improve!

YesNo