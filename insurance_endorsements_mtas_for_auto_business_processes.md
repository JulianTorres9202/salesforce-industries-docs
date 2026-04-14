---
title: "Endorsements/MTAs for Auto Business Processes"
source: "https://help.salesforce.com/s/articleView?id=ind.insurance_endorsements_mtas_for_auto_business_processes.htm&language=en_US&type=5"
scraped: "2026-04-14"
filter: "ind.insurance_"
---# Endorsements/MTAs for Auto Business Processes

Endorsements/MTAs for Auto Business Processes[](https://help.salesforce.com/s?language=en_US)

You are here:

1.  [Salesforce Help](/s/?language=en_US)
2.  [Docs](/s/products?language=en_US)
3.  [Digital Insurance](https://help.salesforce.com/s/articleView?id=ind.insurance_admin_standard.htm&language=en_US&type=5)

# Endorsements/MTAs for Auto Business Processes

We've created a bunch of policy endorsement/MTA business processes for you to examine, use as examples, and extend to create your own endorsement/MTA business processes for auto insurance in Vlocity.

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
        

[](https://help.salesforce.com/s?language=en_US)These OmniScripts now write to the native Financial Services Cloud Insurance Policy object instead of the Asset object. Your insurance policy data is stored on standard Insurance Policy objects using standard fields.

[](https://help.salesforce.com/s?language=en_US)

## Modify Coverages

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

[](https://help.salesforce.com/s?language=en_US)

## Add Drivers

First, the OmniScript takes the policy Id of the policy the user wants to add drivers to.

Then it calls another OmniScript: autoWC/reusableDriverInput1. This same OmniScript is used by the autoWC/Quote OmniScript.The reusable OmniScript provides a form for users to enter information about the drivers to be added.

The fields and selections on this form correspond to the attributes on the insured party spec in the product model.

After the user saves the new driver information, the OmniScript does a bunch of things behind the scenes:

[](https://help.salesforce.com/s?language=en_US)

1.  Uses the InsPolicyService:getInsuredItems service to retrieve data about all the drivers already insured by this policy.
    
2.  Uses an integration procedure to merge the new drivers with the existing drivers.
    
3.  Uses the InsPolicyService:getModifiedPolicy service to get modified policy data that includes the new driver(s).
    
4.  Uses a Data Mapper extract action to prepare the data for display.
    

The OmniScript displays all the old and new drivers using the insOsMultiInstanceGrandchildren Vlocity Lightning Web Component.

Users can open any vehicle to change attribute values on coverages for that vehicle.

On the same page, users can select or deselect optional coverages.

This page also shows the total new premium, the original premium, and other data. Each time the user makes a change to an attribute or optional coverage, the pricing here changes.

After the user clicks Add Drivers, the OmniScript does the following behind the scenes:

[](https://help.salesforce.com/s?language=en_US)

1.  A Data Mapper transform action gets the data ready to create a new version of the existing policy.
    
2.  The InsPolicyService:createNewPolicyVersion service creates a new version of the policy that includes the new driver(s).
    
3.  Payment information is updated.
    

Finally, a confirmation page appears. It includes the final pricing changes.

[](https://help.salesforce.com/s?language=en_US)

## Remove Drivers

First, the OmniScript takes the policyId and uses the InsPolicyService:getInsuredItems service to retrieve data for the drivers included in this policy.

A Vlocity Lightning Web Component (specifically extended for this purpose) displays the drivers and makes them available for users to select for removal.

A selected driver gets a half-border and a big blue dot.

The OmniScript uses the InsPolicyService:removeInsuredItem to remove the selected drivers.

A page displays the price change that will take effect when the driver is removed from the policy.

After the user clicks Remove Driver, a Data Mapper transforms the data and the InsPolicyService:createPolicyVersion service creates a new version of the existing policy, minus the removed drivers.

Finally, a confirmation page appears. It shows the key data that's changed for the policy.

[](https://help.salesforce.com/s?language=en_US)

## Add Vehicles

First, the OmniScript takes the policy Id of the policy the user wants to add vehicles to.

Then it calls another OmniScript: autoWC/reusableVehicleInput1. This same OmniScript is used by the autoWC/Quote OmniScript.

The reusable OmniScript provides a form for users to enter information about the vehicle to be added. The fields and selections on this form correspond to the attributes on the insured item spec in the product model.

After the user saves the new vehicle information, the OmniScript does a bunch of things behind the scenes:

1.  Uses the InsPolicyService:getInsuredItems service to retrieve data about all the vehicles already insured by this policy.
    
2.  Uses an integration procedure to merge the new vehicles with the existing vehicles.
    
3.  Uses the InsPolicyService:getModifiedPolicy service to get modified policy data that includes the new vehicle(s).
    
4.  Uses a Data Mapper extract action to prepare the data for display.
    

The OmniScript displays all the old and new vehicles using the insOsMultiInstanceGrandchildren Vlocity Lightning Web Component.

Users can open any vehicle to change attribute values on coverages for that vehicle.

On the same page, users can select or deselect optional coverages.

This page also shows the total new premium, the original premium, and other data. Each time the user makes a change to an attribute or optional coverage, the pricing here changes.

After the user clicks Add Vehicle, the OmniScript does the following behind the scenes:

1.  A Data Mapper transform action gets the data ready to create a new version of the existing policy.
    
2.  The InsPolicyService:createNewPolicyVersion service creates a new version of the policy that includes the new vehicle(s).
    
3.  Payment information is updated.
    

Finally, a confirmation page appears. It includes the final pricing changes.

[](https://help.salesforce.com/s?language=en_US)

## Remove Vehicles

The OmniScript takes a policy Id and uses the InsPolicyService:getInsuredItems service to retrieve data about all the vehicles insured by this policy. It calls a Data Mapper to transform the data from the service to get it ready to display. Then it displays the vehicles.

The OmniScript calls a Vlocity Lightning Web Component that lets users click any vehicle, then click Next to remove that vehicle from the policy.

When a user chooses a vehicle, it gets an outline and a big blue dot.

The OmniScript calls the InsPolicyService:removeInsuredItem service. It displays data about what will change, especially the price change to the customer.

A bunch of things happen behind the scenes after the user clicks the button. A Data Mapper transforms the data to prepare to create a new policy version.

The InsPolicyService:createPolicyVersion service creates a new version of the existing policy that doesn't include the selected vehicle(s).

An integration procedure updates the payment plan for the policy, minus the premium for the removed vehicle(s).

The user sees a confirmation page that gives the change to the premium they owe.

[](https://help.salesforce.com/s?language=en_US)

## Endorsements (MTAs) Using the Quote and Policy UIs

For all endorsements (MTAs) to policies, your users can start out on the Policies UI.

To start all of the endorsement this way, we:

[](https://help.salesforce.com/s?language=en_US)

1.  Go to the Policies list and open the policy you want to endorse.
    
2.  On the Actions panel, click the type of endorsement you want to make.
    

Did this article solve your issue?

Let us know so we can improve!

YesNo