---
title: "Insurance Property & Casualty Application Overview"
source: "https://help.salesforce.com/s/articleView?id=ind.insurance_propertycasualty_application_overview_509004.htm&language=en_US&type=5"
scraped: "2026-04-14"
filter: "ind.insurance_"
---# Insurance Property & Casualty Application Overview

Insurance Property & Casualty Application Overview[](https://help.salesforce.com/s?language=en_US)

You are here:

1.  [Salesforce Help](/s/?language=en_US)
2.  [Docs](/s/products?language=en_US)
3.  [Digital Insurance](https://help.salesforce.com/s/articleView?id=ind.insurance_admin_standard.htm&language=en_US&type=5)

# Insurance Property & Casualty Application Overview

The Insurance Property & Casualty Application provides examples of insurance applications for a number of lines of business that property and casualty insurers handle. It also includes the Commercial line of business.

[](https://help.salesforce.com/s?language=en_US)

This application comprises applications, business processes, and portals, that brokers, customer service reps, claims adjusters, and administrators can use to do their jobs. Realistic product models and rating procedures work with complete OmniScripts, Integration Procedures, and LWC-based UIs to create quotes, issue policies, endorse policies, create, and manage claims from filing through closing.

[](https://help.salesforce.com/s?language=en_US)

Seed data that comes with the application includes a few pre-created quotes, policies, and claims you can examine as you get started with the application suite.

[](https://help.salesforce.com/s?language=en_US)

These applications can help you learn by example how to use Vlocity Insurance to design your own property and casualty insurance experiences.

[](https://help.salesforce.com/s?language=en_US)

## Lines of Business

The Property & Casualty Application includes applications for the following lines of business:

-   Auto
    
-   Watercraft
    
-   Homeowners
    
-   Business Owners
    
-   Commercial
    

[](https://help.salesforce.com/s?language=en_US)

## Business Processes

Each line of business included in the Property & Casualty Application includes business processes.

[Business Processes Per Line of Business](https://volt.my.salesforce.com/sfc/p/#o0000000ikm8/a/3m000000mhfm/.j6atgwa2kaqjfq.yayrcck_m_4y_mskswooy6g_mgg)

We describe each of these business processes in detail in the Line of Business-specific documentation.

We've updated our business processes to let you move from the Asset object model or the Vlocity Insurance FSC extension object model to the Insurance Policy core object model. Your insurance policy data is stored on standard Insurance Policy objects using standard fields.

[](https://help.salesforce.com/s?language=en_US)

## User Personas

We've defined users in the org so you can run through examples of each business process to see how it functions. Each user has access to one or more applications where they work.

Each user persona uses either an application or a portal.

| 
Persona

 | 

Application

 | 

User

 |
| --- | --- | --- |
| 

Broker or Agent

 | 

Vlocity Broker Portal

 | 

Larry Sullivan

 |
| 

End Customer

 | 

Vlocity Customer Portal

 | 

Ernie Newton

 |
| 

Internal Service Rep, Underwriter

 | 

Vlocity Insurance Console, Vlocity Policy Administration

 | 

Kevin Under

 |
| 

Claims Adjuster

 | 

Vlocity Claims

 | 

Ed Brown

 |
| 

Vlocity Admin

 | 

All applications

 |  |

[](https://help.salesforce.com/s?language=en_US)

## Applications and Portals

The Property & Casualty Application includes the following applications:

-   Vlocity Insurance
    
    For insurance company customer service reps internal to the insurance provider, such as underwriters and reps who directly assist brokers.
    
    In this application, users can create and modify quotes and policies, both via OmniScript flows and the LWC-based Quote UI.
    
-   Vlocity Service Console
    
    For call center representatives who must access and modify customer or policyholder information while working directly with customers.
    
    In this application, the Interaction Launcher fires when a call center rep contacts a customer. The call center rep can see information about the customer and their policy information. The call center rep can have access to walk through endorsement (MTA) and claim FNOL OmniScripts.
    
-   Vlocity Adjuster Dashboard
    
    For Claims Adjusters, who use both the Salesforce features on the Dashboard and the LWC-based Vlocity Adjuster Workbench to work with claims.
    
-   Vlocity Administration
    
    For admins who need access to all the features and functionality of Vlocity Insurance.
    
    This application includes complete access to all components of the Property & Casualty Application Suite.
    

In addition, these portals are part of the Property & Casualty Application. They’re available out-of-the-box from the unmanaged insurance package and are already set up in your Property and Casualty Application org. Click the name of each portal to see what you can do with it.

[](https://help.salesforce.com/s?language=en_US)

-   [Digital Broker Self-Service Portal](https://help.salesforce.com/s/articleView?id=ind.insurance_broker_digital_experience_site_644271.htm&language=en_US&type=5 "Your network of agents and brokers who sell your insurance products need access to specific features and functions to service their accounts. The Broker Experience site on the Experience Cloud can give them that access.")
    
    Insurance brokers use the Broker portal to quote, sell, create endorsements, and sometimes take initial claims first notice of loss for insurance customers.
    
-   [Digital Policyholder Self-Service Portal](https://help.salesforce.com/s/articleView?id=ind.insurance_policyholder_digital_experience_site_645661.htm&language=en_US&type=5 "Give your policyholders access to view and change important information about their account, policies, claims, and billing options with the Policyholder Digital Experience site.")
    
    Policyholders can use this portal to access their own customer data, plus OmniScripts that let them self-serve. Some OmniScripts this portal can make available are Claim FNOL, policy renewal, and policy endorsement (MTA).
    

[](https://help.salesforce.com/s?language=en_US)

## The Most Important Objects

The Property & Casualty Application includes a broad range of Salesforce standard objects and Vlocity custom objects.

For property and casualty insurance, the most important of these objects are:

-   Product
    
    This obejct is where admins create product models to rate and sell. All the child specs, child spec attribute configurations and rules, product-level attributes, workflow rules, surcharges, and product details are configured and stored.
    
-   Quote
    
    This object has a LWC-based UI that lets Insurance and Administration users generate and administrate quotes.
    
    The Quote object connects to subobjects, such as Quote Line Item. To learn more about the Quote object, see [Insurance Quote Object Model](https://help.salesforce.com/s/articleView?id=ind.insurance_vlocity_insurance_quoteobject_model_614266.htm&language=en_US&type=5 "We've extended the Salesforce quote data model to store Insurance-specific data in quotes. When Insurance quoting uses the functionality of both Insurance and Salesforce to store all the data associated with that quote.").
    
-   Policies
    
    The Policies object is actually the Salesforce standard Asset object that we've renamed. It contains policy record data.
    
-   Claim
    
    This object has an LWC-based UI that lets Vlocity Administrator, Vlocity Insurance, and Vlocity Adjuster Dashboard work with claims.
    
    This object stores all claim data. It includes subobjects such as Claim Line Items.
    

[](https://help.salesforce.com/s?language=en_US)

## What's Next?

If you don't already have one, get a spin of the Property & Casualty Application org.

After you've got your spin, choose a line of business to dig into, then start looking at the product model, rating procedure, and business processes.

To learn more about a line of business and its contents, see:

-   [Insurance Application for Auto Guide](https://help.salesforce.com/s/articleView?id=ind.insurance_vlocity_insurance_application_for_auto_guide.htm&language=en_US&type=5 "The Insurance Application for Property & Casualty includes a fully functioning policy administration and claims system for multi-auto, multi-driver auto insurance.")
    
-   [Insurance Application for Watercraft Guide](https://help.salesforce.com/s/articleView?id=ind.insurance_vlocity_insurance_application_for_watercraft_guide_513943.htm&language=en_US&type=5 "The Insurance Application for Property & Casualty includes a fully functioning policy administration and claims system for marine insurance.")
    
-   [Property Overview](https://help.salesforce.com/s/articleView?id=ind.insurance_property_overview_516395.htm&language=en_US&type=5 "The Property line of business provides a fully functional example of Homeowners and Renters product models, rating procedures, and business processes for quoting, issuing, modifying, and canceling policies.")
    
-   [Business Owners Policy Overview](https://help.salesforce.com/s/articleView?id=ind.insurance_business_owners_policy_overview_519688.htm&language=en_US&type=5 "The Business Owners line of business gives you a fully functional example of Economy Business, and Superior Business product models, rating procedures, and business processes for quoting and issuing policies.")
    

-   **[Property & Casualty Application Naming and Numbering Conventions Reference](https://help.salesforce.com/s/articleView?id=ind.insurance_p_and_c_app_naming_and_numbering_conventionsreference_509172.htm&language=en_US&type=5)**  
    We've created product models, rating procedures, and business processes for you in this Application.
-   **[Post-Install Steps](https://help.salesforce.com/s/articleView?id=ind.insurance_post_install_steps_509765.htm&language=en_US&type=5)**  
    Before exploring the Property & Casualty Application org, you need to complete a few configuration tasks to make sure you don't run into any glitches while you're doing your thing. This section walks you through all the post-deployment steps that you must complete.
-   **[Insurance Application for Auto Guide](https://help.salesforce.com/s/articleView?id=ind.insurance_vlocity_insurance_application_for_auto_guide.htm&language=en_US&type=5)**  
    The Insurance Application for Property & Casualty includes a fully functioning policy administration and claims system for multi-auto, multi-driver auto insurance.
-   **[Insurance Application for Watercraft Guide](https://help.salesforce.com/s/articleView?id=ind.insurance_vlocity_insurance_application_for_watercraft_guide_513943.htm&language=en_US&type=5)**  
    The Insurance Application for Property & Casualty includes a fully functioning policy administration and claims system for marine insurance.
-   **[Property Overview](https://help.salesforce.com/s/articleView?id=ind.insurance_property_overview_516395.htm&language=en_US&type=5)**  
    The Property line of business provides a fully functional example of Homeowners and Renters product models, rating procedures, and business processes for quoting, issuing, modifying, and canceling policies.
-   **[Business Owners Policy Overview](https://help.salesforce.com/s/articleView?id=ind.insurance_business_owners_policy_overview_519688.htm&language=en_US&type=5)**  
    The Business Owners line of business gives you a fully functional example of Economy Business, and Superior Business product models, rating procedures, and business processes for quoting and issuing policies.
-   **[Commissions for Property and Casualty Application](https://help.salesforce.com/s/articleView?id=ind.insurance_t_commissions_for_property_and_casualty_application_521619.htm&language=en_US&type=5)**  
    You can now track commissions for agents and insurance products, and gain insight into commissions associated with each stage of the customer journey.
-   **[Support Users with the Property and Casualty Application Suite Interaction Launcher and Console](https://help.salesforce.com/s/articleView?id=ind.insurance_support_users_with_the_p_and_c_app_suite_intlauncher_and_console_521722.htm&language=en_US&type=5)**  
    Use the Interaction Launcher component with Property & Casualty so that your service agents can quickly access a 360-degree view of a customer.
-   **[Claims Dashboards](https://help.salesforce.com/s/articleView?id=ind.insurance_t_claims_dashboards_521983.htm&language=en_US&type=5)**  
    Use dashboards to focus on open tasks and claims that need your attention so you can close them quickly.

Did this article solve your issue?

Let us know so we can improve!

YesNo