---
title: "Activate and Deploy LWC OmniScripts"
source: "https://help.salesforce.com/s/articleView?id=ind.insurance_activate_and_deploy_an_lwc_omniscript_omniscripts.htm&language=en_US&type=5"
scraped: "2026-04-13"
filter: "ind.insurance_"
---# Activate and Deploy LWC OmniScripts

Activate and Deploy LWC OmniScripts[](https://help.salesforce.com/s?language=en_US)

You are here:

1.  [Salesforce Help](/s/?language=en_US)
2.  [Docs](/s/products?language=en_US)
3.  [Digital Insurance](https://help.salesforce.com/s/articleView?id=ind.insurance_admin_standard.htm&language=en_US&type=5)

# Activate and Deploy LWC OmniScripts

Make OmniScripts available to Experience Sites, Lightning Pages, custom LWCs, and Lightning tabs by activating and deploying the OmniScript. If an error occurs during deployment the OmniScript will deactivate.

If you're upgrading, complete this task to deploy each of your Active LWC OmniScripts.

1.  From OmniScript, click **Activate** to activate the OmniScript and deploy the OmniScript automatically.
2.  (Optional) Click **Deactivate**, and then **Activate** to redeploy the OmniScript and apply updates.
3.  (Optional) Click **Deactivate**, and then **Activate** to redeploy the OmniScript and apply updates or resolve a deployment issue.
4.  (Optional) Exclusive to the Classic Designer, if there is an issue with the deployment, redeploy the OmniScript by clicking the **Deploy LWC** button in the Script Configuration properties.
    
    Note Ensure the OmniScript is active, then click the Deploy LWC button to redeploy the OmniScript.
    
5.  After deploying your OmniScript, launch your OmniScript from one of these experiences:
    
    | Experience | Description |
    | --- | --- |
    | 
    Lightning pages
    
     | 
    
    Launch an OmniScript from a Lightning page using the standard OmniScript component, the OmniScript's generated LWC, or the Vlocity LWC OmniScript Wrapper component.
    
     |
    | 
    
    Experience pages
    
     | 
    
    Launch an OmniScript from an Experience page using the standard OmniScript component, OmniScript's generated LWC, or the Vlocity LWC OmniScript Wrapper component.
    
     |
    | 
    
    Embedded inside of a custom component
    
     | 
    
    Launch an OmniScript from a custom Lightning web component by embedding the OmniScript's LWC.
    
     |
    | 
    
    Off-Platform
    
     | 
    
    Run OmniScripts off-platform using OmniOut. Available beginning with Vlocity Insurance and Health and Vlocity CME Summer '20.
    
     |
    
6.  (Optional) If an error occurs on the initial load of an OmniScript, in the OmniScript, click **Deactivate**, then click **Activate**. This redeploys the OmniScript.
7.  (Optional) Map deployment errors using the Error Handling Framework.
    
    Error Mapping Example:
    
    Original error
    
    Error Message Mapping a Path and Value to a new message
    
    New error message
    
8.  (Optional) Click the dropdown arrow, and click **Download LWC** to view the metadata for the OmniScript.

Did this article solve your issue?

Let us know so we can improve!

YesNo