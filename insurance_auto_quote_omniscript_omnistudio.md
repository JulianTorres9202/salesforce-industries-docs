---
title: "Auto Quote OmniScript"
source: "https://help.salesforce.com/s/articleView?id=ind.insurance_auto_quote_omniscript_omnistudio.htm&language=en_US&type=5"
scraped: "2026-04-13"
filter: "ind.insurance_"
---# Auto Quote OmniScript

Auto Quote OmniScript[](https://help.salesforce.com/s?language=en_US)

You are here:

1.  [Salesforce Help](/s/?language=en_US)
2.  [Docs](/s/products?language=en_US)
3.  [Digital Insurance](https://help.salesforce.com/s/articleView?id=ind.insurance_admin_standard.htm&language=en_US&type=5)

# Auto Quote OmniScript

Look under the hood of the Auto quote process with details of the quote OmniScript.

For details of the quoting flow for Commercial Auto products, see the [](https://help.salesforce.com/s?language=en_US)[Commercial Quote Business Process](https://help.salesforce.com/s/articleView?id=ind.insurance_commercial_quote_business_process_omnistudio.htm&language=en_US&type=5 "We've created a quote business process for General Liability for you to examine, use as an example, and extend to create your own business processes for insurance.").

All our screenshots are currently in Lightning style. Your spin may look different because it's using the Newport style in the Broker Portal and Customer Portal.

The name of the auto quote OmniScript is:

-   List name: **auto/Quote**
    
-   OmniScript Name: **Auto Quote**
    

You can launch this OmniScript from the following applications, where it can be accessed by the types of users described:

-   Broker Portal (Newport)
    
    For use by brokers and agents
    
-   Interaction Console (Lightning)
    
    Internal insurance agent
    
-   Vlocity Admin Lighting Experience (Newport)
    
    -   Internal insurance agent
        
    -   Vlocity admin
        

The process flow for this OmniScript looks like this:

The Auto Quote OmniScript calls two other OmniScripts. The first of these is the ReusableDriverInput OmniScript. It has its own process flow, which looks like this:

The second OmniScript called by the Auto Quote OmniScript is the ReusableVehicleInput OmniScript. Its process flow looks like this:

-   **[How Auto Quote OmniScript Works](https://help.salesforce.com/s/articleView?id=ind.insurance_how_auto_quote_omniscript_works_omnistudio.htm&language=en_US&type=5)**  
    This section describes how someone who goes through the Auto Quote OmniScript to create a quote will see and interact with it.
-   **[What's in Auto Quote OmniScript](https://help.salesforce.com/s/articleView?id=ind.insurance_whats_in_auto_quote_omniscript_omnistudio.htm&language=en_US&type=5)**  
    The Auto Quote is LWC Enabled. It's built using LWCs you can learn about in.Insurance Lightning Web Component UI Development Kit

Did this article solve your issue?

Let us know so we can improve!

YesNo