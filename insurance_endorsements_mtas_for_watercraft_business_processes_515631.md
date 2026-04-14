---
title: "Endorsements/MTAs for Watercraft Business Processes"
source: "https://help.salesforce.com/s/articleView?id=ind.insurance_endorsements_mtas_for_watercraft_business_processes_515631.htm&language=en_US&type=5"
scraped: "2026-04-14"
filter: "ind.insurance_"
---# Endorsements/MTAs for Watercraft Business Processes

Endorsements/MTAs for Watercraft Business Processes[](https://help.salesforce.com/s?language=en_US)

You are here:

1.  [Salesforce Help](/s/?language=en_US)
2.  [Docs](/s/products?language=en_US)
3.  [Digital Insurance](https://help.salesforce.com/s/articleView?id=ind.insurance_admin_standard.htm&language=en_US&type=5)

# Endorsements/MTAs for Watercraft Business Processes

We've created a bunch of policy endorsement/MTA business processes for you to examine, use as examples, and extend to create your own endorsement/MTA business processes for watercraft insurance in Vlocity.

[](https://help.salesforce.com/s?language=en_US)

All our screenshots are currently in Lightning style. Your spin may look different because it's using the Newport style in the Broker Portal and Policyholder Self-Service Portal.

[](https://help.salesforce.com/s?language=en_US)

## OmniScript Policy Endorsement Flows

You can launch all of the following OmniScripts from the following applications, where it can be accessed by the types of users described:

[](https://help.salesforce.com/s?language=en_US)

-   Broker Portal (Newport)
    
    Brokers and agents
    
-   Policyholder Self-Service Portal (Newport)
    
    End customers who own insurance policies
    
-   Interaction Console (Lightning)
    
    Internal insurance agents and call center reps
    
-   Vlocity Admin Lighting Experience (Newport)
    
    -   Internal insurance agents
        
    -   Vlocity admins
        

[](https://help.salesforce.com/s?language=en_US)

## Modify Coverages

The modify coverages process uses the Marine - Modify Coverages OmniScript. First, the OmniScript takes the policy Id of the policy that the user wants to make changes to.

It uses the [InsPolicyService:getInsuredItems](https://help.salesforce.com/s/articleView?id=ind.insurance_inspolicyservice__getinsureditems.htm&language=en_US&type=5 "Use this service to find and return insured items and insured parties from a policy (asset).") service to retrieve data about the operator and the vessels already insured by this policy.

Then it uses the [InsPolicyService:getPolicyDetails](https://help.salesforce.com/s/articleView?id=ind.insurance_inspolicyservice__getpolicydetails.htm&language=en_US&type=5 "Use this service to get the coverages, insured items, pricing, and other information for an existing insurance policy, including optional coverages that weren't selected.") service to get coverage data for the policy.

The OmniScript uses the insOsMultiInstanceGrandchildren Vlocity Lightning Web Component to display the vessels and coverages.

This Lightning Web Component lets users make changes to attribute values. Users can change policy-level coverages as well as the coverages for each vessel.

To start all of the endorsements this way:

[](https://help.salesforce.com/s?language=en_US)

1.  Go to the Policies list.
2.  Open the policy you want to endorse.
3.  On the Actions panel, click the type of endorsement you want to make. To modify coverages, click **Modify Coverages**.
4.  Update the policy-level and item-level coverages, as required.
5.  You can also select and deselect optional coverages.
6.  This page also shows the total new premium, the original premium, and other data. Each time the user makes a change to an attribute or optional coverage, the pricing here changes.

After the user clicks Modify Coverages, the OmniScript does the following behind the scenes:

[](https://help.salesforce.com/s?language=en_US)

1.  An Omnistudio Data Mapper transform action gets the data ready to create a new version of the existing policy.
    
2.  The [InsPolicyService:createPolicyVersion](https://help.salesforce.com/s/articleView?id=ind.insurance_inspolicyservice__createpolicyversion.htm&language=en_US&type=5 "Use this service to create a new version of an existing policy, while maintaining the existing policy record as-is.") service creates a new version of the policy that includes the new data.
    
3.  Payment information is updated.
    

Finally, a confirmation page appears. It includes the final pricing changes.

[](https://help.salesforce.com/s?language=en_US)

## Endorsements (MTAs) Using the Quote and Policy UIs

For all endorsements (MTAs) to policies, your users can start out on the Policies UI.

Did this article solve your issue?

Let us know so we can improve!

YesNo