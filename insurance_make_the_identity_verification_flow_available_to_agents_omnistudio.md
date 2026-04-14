---
title: "Make the Identity Verification Flow Available to Agents"
source: "https://help.salesforce.com/s/articleView?id=ind.insurance_make_the_identity_verification_flow_available_to_agents_omnistudio.htm&language=en_US&type=5"
scraped: "2026-04-14"
filter: "ind.insurance_"
---# Make the Identity Verification Flow Available to Agents

Make the Identity Verification Flow Available to Agents[](https://help.salesforce.com/s?language=en_US)

You are here:

1.  [Salesforce Help](/s/?language=en_US)
2.  [Docs](/s/products?language=en_US)
3.  [Digital Insurance](https://help.salesforce.com/s/articleView?id=ind.insurance_admin_standard.htm&language=en_US&type=5)

# Make the Identity Verification Flow Available to Agents

To enable your call center agents to perform identity verification, make the flow available to them. Create an Engagement Interaction Lightning record page and then add the flow to the Engagement Interaction Lightning record page.

1.  From Setup Home, in the Quick Find box, enter `Lightning App Builder`, and then select **Lightning App Builder**.
    
2.  Click **New**.
    
3.  In Create a New Lightning Page, select **Record Page** and click **Next**.
    
4.  Enter a label and select the **Engagement Interaction** object for the new Lightning record page.
    
5.  Click **Save**.
    
6.  Select a page template and click **Finish**.
    
    The No Data for this Object window appears, which says that the selected object has no records. That’s fine. Engagement Interaction records are auto-created at runtime.
    
7.  Read the message and then close the window.
    
8.  Drop the Flow component on the page.
    
9.  Select the relevant flow in the Flow field.
    
10.  In the attributes panel, select **Pass record ID into this variable**.
     
11.  Save and activate your changes.
     
12.  Close Flow Builder.
     

Did this article solve your issue?

Let us know so we can improve!

YesNo