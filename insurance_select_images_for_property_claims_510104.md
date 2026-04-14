---
title: "Select Images for Property Claims"
source: "https://help.salesforce.com/s/articleView?id=ind.insurance_select_images_for_property_claims_510104.htm&language=en_US&type=5"
scraped: "2026-04-14"
filter: "ind.insurance_"
---# Select Images for Property Claims

Select Images for Property Claims[](https://help.salesforce.com/s?language=en_US)

You are here:

1.  [Salesforce Help](/s/?language=en_US)
2.  [Docs](/s/products?language=en_US)
3.  [Digital Insurance](https://help.salesforce.com/s/articleView?id=ind.insurance_admin_standard.htm&language=en_US&type=5)

# Select Images for Property Claims

If images for the Property claims FNOL process aren't displaying correctly, configure them in the OmniScript.

1.  Use the App Launcher to navigate to OmniScripts.
2.  Find the OmniScript:
    
    -   Type/Subtype - Insproperty/claimsFSC
        
    -   OmniScript Name - propertyClaimFNOLFsc
        
    
3.  Deactivate the OmniScript.
4.  Navigate to the element **enterDetailsofAccident**.
5.  Select the element titled **peril**.
6.  Scroll down to Options, and select these images for the options.
    
    Mostly, when you select the first image, that is the umbrella, the other images get selected automatically as originally configured.
    
    | 
    Value
    
     | 
    
    Image Name
    
     |
    | --- | --- |
    | 
    
    Water
    
     | 
    
    Umbrella
    
     |
    | 
    
    Fire
    
     | 
    
    Fire
    
     |
    | 
    
    Vandalism
    
     | 
    
    Vandalism
    
     |
    | 
    
    EarthQuake
    
     | 
    
    EarthQuake
    
     |
    | 
    
    Flooding
    
     | 
    
    Flooding
    
     |
    | 
    
    Burglary
    
     | 
    
    Burglary
    
     |
    | 
    
    Personal Liability
    
     | 
    
    liability
    
     |
    | 
    
    Guest Injury
    
     | 
    
    GuestInjuryPNG
    
     |
    | 
    
    Windstorm
    
     | 
    
    Windstorm
    
     |
    
7.  Navigate to the next step, called **description**, in the same block.
8.  If you don't see the image next to **Description**, edit the text to add the image DetailDocument from the **Image List**.
9.  Navigate to the element **propertyDamagedDetails**.
10.  Scroll down to Options and select these images:
     
     | 
     Value
     
      | 
     
     Image Name
     
      |
     | --- | --- |
     | 
     
     Exterior of the House
     
      | 
     
     ExteriorOfHouse
     
      |
     | 
     
     Interior of the House
     
      | 
     
     interionHousy
     
      |
     | 
     
     Contents within the house
     
      | 
     
     ContentsWithin
     
      |
     | 
     
     Other structures in property
     
      | 
     
     otherStructures
     
      |
     
11.  Click **Save**.
12.  Activate the OmniScript.

Did this article solve your issue?

Let us know so we can improve!

YesNo