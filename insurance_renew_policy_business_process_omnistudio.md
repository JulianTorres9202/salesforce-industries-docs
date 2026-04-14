---
title: "Renew Policy Business Process"
source: "https://help.salesforce.com/s/articleView?id=ind.insurance_renew_policy_business_process_omnistudio.htm&language=en_US&type=5"
scraped: "2026-04-14"
filter: "ind.insurance_"
---# Renew Policy Business Process

Renew Policy Business Process[](https://help.salesforce.com/s?language=en_US)

You are here:

1.  [Salesforce Help](/s/?language=en_US)
2.  [Docs](/s/products?language=en_US)
3.  [Digital Insurance](https://help.salesforce.com/s/articleView?id=ind.insurance_admin_standard.htm&language=en_US&type=5)

# Renew Policy Business Process

When it's time to renew your policy, you get an email with a renewal link. Then all you have to do is enter some details for the renewal and it's all done. It's that simple! Carry on reading to find out details of this process.

[](https://help.salesforce.com/s?language=en_US)

## Renew Policy OmniScript

The renew policy OmniScript is available in OmniScripts under:

-   Type - insFSC/RenewPolicy
    
-   Version Name - Renew Policy FSC
    

You can launch this OmniScript from:

| 
If you’re a

 | 

Launch OmniScript from

 |
| --- | --- |
| 

Broker or Agent

 | 

Broker Portal

 |
| 

Customer who owns insurance policies

 | 

Customer Portal

 |
| 

Internal insurance agent

Vlocity admin

 | 

Vlocity Admin Lightning Experience

 |

[](https://help.salesforce.com/s?language=en_US)

## How It Works

Here's a look at the workflow to renew your policy:

1.  [](https://help.salesforce.com/s?language=en_US)The OmniScript takes a policy Id and uses the InsPolicyService:getInsuredItems and InsPolicyService:getPolicyDetails services to retrieve data about the vehicles insured by this policy and the corresponding coverages for them.
    
2.  It calls an Omnistudio Data Mapper to transform the data from the service to get it ready to display.
    
3.  It then displays the vehicle and coverage details and lets the user modify coverages. If users modify coverages, the policy is repriced accordingly and the price is updated on the user interface.
    
4.  The OmniScript uses this information to create a renewed policy.
    
5.  Next, a Data Mapper updates the old policy to show that it has been renewed.
    
6.  The OmniScript then uses a FlexCard to show information about the renewed policy.
    

[](https://help.salesforce.com/s?language=en_US)

## What's In It

| 
Component Name

 | 

Component Type

 | 

What It Does

 | 

What It Calls

 |
| --- | --- | --- | --- |
| 

SetPolicyId

 | 

Set Values

 | 

Retrieves the effective date and policy ID of the policy.

 | 

None

 |
| 

GetInsuredItems

 | 

Remote Action

 | 

Calls the service to get a list of the insured items.

 | 

[InsPolicyService:getInsuredItems](https://help.salesforce.com/s/articleView?id=ind.insurance_inspolicyservice__getinsureditems.htm&language=en_US&type=5 "Use this service to find and return insured items and insured parties from a policy (asset).")

 |
| 

GetPolicyCoverages

 | 

Remote Action

 | 

Calls the service to get a list of the applicable coverages.

 | 

[InsPolicyService:getPolicyDetails](https://help.salesforce.com/s/articleView?id=ind.insurance_inspolicyservice__getpolicydetails.htm&language=en_US&type=5 "Use this service to get the coverages, insured items, pricing, and other information for an existing insurance policy, including optional coverages that weren't selected.")

 |
| 

setDisplayValues

 | 

Omnistudio Data Mapper Extract Action

 | 

Transforms the policy data for display.

 | 

Fsc\_ReadPolicyDetails

 |
| 

SetRenewDate

 | 

Set Values

 | 

Retrieves the policy renewal date.

 | 

None

 |
| 

configure

 | 

Step

 | 

Lets users configure coverages for the renewed policy.

 | 

None

 |
| 

createUpdatePolicy

 | 

Integration Procedure Action

 | 

Calls an integration procedure that creates the renewed policy using the InsPolicyService: createPolicyVersion service.

 | 

CreateRenewedPolicyVersion

 |
| 

UpdateOldPolicy

 | 

Data Mapper Post Action

 | 

Updates the old policy record renewal information.

 | 

Ins\_PostOldPolicyVersion\_FscOS

 |
| 

confirmationScreen1

 | 

Step

 | 

Displays the details of the renewed policy.

 | 

None

 |

[](https://help.salesforce.com/s?language=en_US)

## How to Renew a Policy

There are three ways customer services reps, policyholders, and brokers can renew policies:

-   [Renew a Policy from the Policy UI](https://help.salesforce.com/s/articleView?id=ind.insurance_insurance_application_suite_renew_a_policy_from_the_policy_ui.htm&language=en_US&type=5 "A customer service rep or internal insurance agent with access to the Policy UI can renew policies from that UI.")
    
-   [Renew Policies from the Digital Experience Site](https://help.salesforce.com/s/articleView?id=ind.insurance_insurance_application_suite_renew_a_policy_from_the_digital_experience_site.htm&language=en_US&type=5 "Policyholders and brokers can renew policies right from their Experience Sites.")
    
-   [Renew a Policy Through Email](https://help.salesforce.com/s/articleView?id=ind.insurance_insurance_application_suite_renew_a_policy_through_email.htm&language=en_US&type=5 "A week before your policy expires, you receive a reminder email to renew your policy. Here's what an example email looks like:")
    

-   **[Insurance Application Suite Renew a Policy from the Policy UI](https://help.salesforce.com/s/articleView?id=ind.insurance_insurance_application_suite_renew_a_policy_from_the_policy_ui_omnistudio.htm&language=en_US&type=5)**  
    A customer service rep or internal insurance agent with access to the Policy UI can renew policies from that UI.
-   **[Insurance Application Suite Renew a Policy from the Digital Experience Site](https://help.salesforce.com/s/articleView?id=ind.insurance_insurance_application_suite_renew_a_policy_from_the_digital_experience_site_omnistudio.htm&language=en_US&type=5)**  
    Policyholders and brokers can renew policies right from their Experience Sites.
-   **[Insurance Application Suite Renew a Policy Through Email](https://help.salesforce.com/s/articleView?id=ind.insurance_insurance_application_suite_renew_a_policy_through_email_omnistudio.htm&language=en_US&type=5)**  
    A week before your policy expires, you receive a reminder email to renew your policy. Here's what an example email looks like:

Did this article solve your issue?

Let us know so we can improve!

YesNo