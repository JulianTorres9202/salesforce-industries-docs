---
title: "Modify Coverages for Auto Business"
source: "https://help.salesforce.com/s/articleView?id=ind.insurance_modify_coverages_for_auto_business_omnistudio.htm&language=en_US&type=5"
scraped: "2026-04-14"
filter: "ind.insurance_"
---# Modify Coverages for Auto Business

Modify Coverages for Auto Business[](https://help.salesforce.com/s?language=en_US)

You are here:

1.  [Salesforce Help](/s/?language=en_US)
2.  [Docs](/s/products?language=en_US)
3.  [Digital Insurance](https://help.salesforce.com/s/articleView?id=ind.insurance_admin_standard.htm&language=en_US&type=5)

# Modify Coverages for Auto Business

You can modify the coverages on an existing insurance policy using an OmniScript.

First, the OmniScript takes the policy Id of the policy the user wants to make changes to.

It uses the InsPolicyService:getInsuredItems service to retrieve data about all the drivers and vehicles already insured by this policy.

Then it uses the InsPolicyService:getPolicyDetails service to get coverage data for the policy.

The OmniScript uses the insOsMultiInstanceGrandchildren Vlocity Lightning Web Component to display the vehicles, drivers, and their coverages.

This Lightning Web Component lets users make changes to attribute values.

Users can also select and deselect optional coverages.

This page also shows the total new premium, the original premium, and other data. Each time the user makes a change to an attribute or optional coverage, the pricing here changes.

After the user clicks Modify Coverages, the OmniScript does the following behind the scenes:

[](https://help.salesforce.com/s?language=en_US)

1.  An Omnistudio Data Mapper transform action gets the data ready to create a new version of the existing policy.
    
2.  The InsPolicyService:createNewPolicyVersion service creates a new version of the policy that includes the new driver(s).
    
3.  Payment information is updated.
    

Finally, a confirmation page appears. It includes the final pricing changes.

Did this article solve your issue?

Let us know so we can improve!

YesNo