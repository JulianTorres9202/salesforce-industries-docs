---
title: "Cancel Policy Business Process"
source: "https://help.salesforce.com/s/articleView?id=ind.insurance_cancel_policy_business_process_omnistudio.htm&language=en_US&type=5"
scraped: "2026-04-14"
filter: "ind.insurance_"
---# Cancel Policy Business Process

Cancel Policy Business Process[](https://help.salesforce.com/s?language=en_US)

You are here:

1.  [Salesforce Help](/s/?language=en_US)
2.  [Docs](/s/products?language=en_US)
3.  [Digital Insurance](https://help.salesforce.com/s/articleView?id=ind.insurance_admin_standard.htm&language=en_US&type=5)

# Cancel Policy Business Process

The policy cancelation business process lets brokers and policyholders cancel an in-force policy. The policyholder receives a refund for the unutilized premium on the policy, which is calculated based on the policy effective date and the effective date of the cancelation transaction.

[](https://help.salesforce.com/s?language=en_US)

## Cancel Policy OmniScript

You can launch this OmniScript from the following applications, where it can be accessed by the types of users described:

[](https://help.salesforce.com/s?language=en_US)

-   Broker Portal (Newport)
    
    Brokers and agents
    
-   Customer Portal (Newport)
    
    End customers who own insurance policies
    
-   Interaction Console (Lightning)
    
    Internal insurance agents and call center reps
    
-   Vlocity Admin Lighting Experience (Newport)
    -   Internal insurance agents
    -   Vlocity admins

[](https://help.salesforce.com/s?language=en_US)These OmniScripts now write to the native Financial Services Cloud Insurance Policy object instead of the Asset object.

The OmniScript takes a policy Id and uses the InsPolicyService:getPolicyDetails service to retrieve data about the policy to be canceled. The OmniSript displays information about the policy and asks for a cancellation date.

The OmniScript calls the InsPolicyService:prepareToCancelPolicy service, which calculates the refund owed to the customer upon cancellation. It displays information about the cancellation and provides a button the user can click to cancel the policy.

After the user clicks the button, the OmniScript calls the InsPolicyService:cancelPolicy service. The policy is canceled.

[](https://help.salesforce.com/s?language=en_US)

## Cancel Policy from Policies UI

To cancel any policy from the Policies UI, first go to the Policies list page and click the policy you want to cancel.

Click **Cancel Policy**.

Enter the date when you want the policy to be canceled, then click **Calculate and Display Refund**.

After you click **Approve and Proceed**, you can navigate back to the policy page, which now has the new policy end date you specified.

Did this article solve your issue?

Let us know so we can improve!

YesNo