---
title: "Auto Claims First Notice of Loss"
source: "https://help.salesforce.com/s/articleView?id=ind.insurance_auto_claims_first_notice_of_loss_513238.htm&language=en_US&type=5"
scraped: "2026-04-13"
filter: "ind.insurance_"
---# Auto Claims First Notice of Loss

Auto Claims First Notice of Loss[](https://help.salesforce.com/s?language=en_US)

You are here:

1.  [Salesforce Help](/s/?language=en_US)
2.  [Docs](/s/products?language=en_US)
3.  [Digital Insurance](https://help.salesforce.com/s/articleView?id=ind.insurance_admin_standard.htm&language=en_US&type=5)

# Auto Claims First Notice of Loss

Car accidents happen. When they do, policyholders need to submit First Notice of Loss (FNOL) information to their insurers to start the claims process rolling. This application includes an auto FNOL OmniScript that does just this.

[](https://help.salesforce.com/s?language=en_US)

To show how to gather info about accidents, the auto FNOL OmniScript does these things:

[](https://help.salesforce.com/s?language=en_US)

-   Gathers initial loss information
    
-   Creates a claim record
    
-   Runs rules
    
-   Puts the claim into an adjuster's workflow
    

[](https://help.salesforce.com/s?language=en_US)

The Multi Auto Claim First Notice of Loss (FNOL) OmniScript name is:

[](https://help.salesforce.com/s?language=en_US)

-   Type: **lwcauto**
    
-   Subtype: **FNOL**
    
-   Version name: **MultiAutoClaimFNOL**
    

[](https://help.salesforce.com/s?language=en_US)

The claims FNOL business process flow looks like this:

[](https://help.salesforce.com/s?language=en_US)

## How It Works

Now let's step through the OmniScript the same way, as a user sees it.

This OmniScript begins for a policyholder, broker, or agent after the policy number has been entered into the system, which finds the policy and uses the data in it.

The FNOL OmniScript starts by showing the user (us) the vehicles on the policy.

After we choose the vehicle involved in the incident, we choose what happened.

Next, we enter basic information about the incident. The date of the incident is important. The system uses that date to help determine whether the policyholder is covered for the incident.

Behind the scenes, the OmniScript calls a service that creates the initial claim record.

Then, we enter more information about the damaged vehicle that's covered by the policy.

We enter information about the other damaged vehicle.

We enter information about who was injured and how badly.

We enter information about the police report, and can upload it now if we have a copy.

After we finish entering information, the system provides a claim confirmation that includes the claim number.

Did this article solve your issue?

Let us know so we can improve!

YesNo