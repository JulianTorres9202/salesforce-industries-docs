---
title: "Divvy Up Work On Your Claims Team with Routing"
source: "https://help.salesforce.com/s/articleView?id=ind.insurance_divvy_up_work_on_your_claims_team_with_routing.htm&language=en_US&type=5"
scraped: "2026-04-14"
filter: "ind.insurance_"
---# Divvy Up Work On Your Claims Team with Routing

Divvy Up Work On Your Claims Team with Routing[](https://help.salesforce.com/s?language=en_US)

You are here:

1.  [Salesforce Help](/s/?language=en_US)
2.  [Docs](/s/products?language=en_US)
3.  [Digital Insurance](https://help.salesforce.com/s/articleView?id=ind.insurance_admin_standard.htm&language=en_US&type=5)

# Divvy Up Work On Your Claims Team with Routing

Configure Omni-Channel to route claims to the best-fit person on your team based on your team's availability and the priority of the work. Depending on your business needs, route work to queues or skills.

Omni-Channel supports routing for:

-   Claims.
    
-   Claim coverages.
    
-   Claim recoveries.
    
-   Claim recoveries.
    

Here are some typical queues and skills for claims routing.

Tip

Capture data such as claim type and jurisdiction in the First Notice of Loss workflow, and use product rules to enrich claim data with values such as Claim Complexity.

| 
Entity

 | 

Skill

 | 

Examples

 |
| --- | --- | --- |
| 

Claim

 | 

Claim Type

 | 

Auto, Property

 |
| 

Claim coverage

 | 

Coverage Spec

 | 

For Auto: Comprehensive, Collision, Uninsured Motorist, and Rental Car

For Health: Office Visit, Ambulance Service, Outpatient Surgery, Hospital Stay

 |
| 

Claim coverage

 | 

Complexity

 | 

Low, Medium, High

 |

| 
Entity

 | 

Queue

 | 

Examples

 |
| --- | --- | --- |
| 

Claim

 | 

Region

 | 

Asia, Europe, North America

 |
| 

Claim

 | 

Jurisdiction

 | 

Jurisdiction

 |

1.  Prepare your org for Omni-Channel.
    
    -   Make sure users have the Service Cloud license.
        
    -   In Setup, enable Omni-Channel. If you plan to route to skills, in Setup, select **Enable Skills-Based and Direct-to-Agent Routing**. If you plan to route to an agent's capacity based on status, in Setup, select **Enable Status-Based Capacity Model**.
        
    
2.  Create service channels for claims.
    
    In service channel settings, for **Salesforce Object**, enter the type of record to route claim team members: Claim, ClaimCoverage, ClaimRecovery, or PaymentRequest.
    
3.  Add the Omni-Channel utility to your Lightning Service console.
    
    The Omni-Channel utility appears in the utility bar in your Lightning Console app. From there, agents can change their presence status and triage their incoming work assignments.
    
    To give claims supervisors easy access to team assignments, create a Lightning App in App Manager.
    
    -   For **App Options**, choose Console Navigation and Service Setup.
        
    -   For **Utility Items**, add Omni-Channel.
        
    -   For **Navigation Items**, choose Claim entities.
        
    
    For information about other Lightning app settings, see [Customize Lightning Apps with the Lightning App Builder](https://help.salesforce.com/s/articleView?id=sf.dev_apps_lightning_customize.htm&language=en_US&type=5).
    
4.  Set up claim team members as agents to complete work requests.
5.  If necessary, create presence configurations and assign individual agents to them. If you reassign agents to a custom presence configuration, they're excluded from the Default Presence Configuration.
6.  Create queues.
    
    Set the priority for each queue and assign agents to it.
    
    In the Service Console, if you create a queue from Omni-Channel Setup, the queue is associated with the Case entity by default. To change the entity for a queue, from Setup, find **Queues**, then edit the queue.
    
7.  Set up routing to queues to distribute the workload among a team of agents.
    1.  Create a queue.
    2.  Create a routing configuration for the queue.
8.  Set up routing to skills to distribute work to a qualified agent with the required skills.
    1.  Create a queue.
    2.  Create skills.
    3.  Add Skills as a related list to the Service Resource object.
    4.  Create service resources that represent each claim team member and their skills.
    5.  Define skills-based routing rules.
    6.  Enable skills-based routing rules in the routing configuration used to route to skills.
9.  Test your Omni-Channel implementation to make sure it works correctly.

Did this article solve your issue?

Let us know so we can improve!

YesNo