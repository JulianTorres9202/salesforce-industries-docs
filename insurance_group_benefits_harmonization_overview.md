---
title: "Group Benefits Harmonization Overview"
source: "https://help.salesforce.com/s/articleView?id=ind.insurance_group_benefits_harmonization_overview.htm&language=en_US&type=5"
scraped: "2026-04-14"
filter: "ind.insurance_"
---# Group Benefits Harmonization Overview

Group Benefits Harmonization Overview[](https://help.salesforce.com/s?language=en_US)

You are here:

1.  [Salesforce Help](/s/?language=en_US)
2.  [Docs](/s/products?language=en_US)
3.  [Digital Insurance](https://help.salesforce.com/s/articleView?id=ind.insurance_admin_standard.htm&language=en_US&type=5)

# Group Benefits Harmonization Overview

Group Benefits harmonization involves moving Group Benefits data from custom objects in the Vlocity managed package object model to standard objects in the Salesforce object model.

Note

Existing customers can continue to use Group Benefits custom objects in the Vlocity object model, but no further enhancements will be provided in the Vlocity Health and Vlocity Insurance Managed Package. Not sure whether or when to harmonize your org? See [When to Harmonize](https://help.salesforce.com/s/articleView?id=ind.insurance_when_to_harmonize.htm&language=en_US&type=5 "It's your choice to harmonize or not to harmonize, and when to do it. We have different recommendations based on whether you're a new or existing customer.").

[](https://help.salesforce.com/s?language=en_US)For details on the harmonized objects and the field mappings for each object, see [Vlocity Object to Group Benefits Standard Object Model Mapping](https://help.salesforce.com/s/articleView?id=ind.insurance_vlocity_object_to_group_benefits_standard_object_model_mapping.htm&language=en_US&type=5 "Learn how fields in the Vlocity Group Benefits object model correspond to fields in the Salesforce object model. Use these field mappings when you create scripts that move Group Benefits data from one model to the other.").

## Group Insurance Data Model in a Harmonized Org

Group Census holds the summary information derived from the Group Census Member records. This child object of Employee or Group Account can have multiple Group Census Members records associated with it.

The Group Class object defines the employee classes such as Executives and Managers. Define the employee and employer contribution percentages on the premium in the Group Class Contribution object. Each account can have multiple Group Classes and Group Class Contributions.

The Quote and Quote Line Items are existing objects in the quoting process. After you finalize the quote, an insurance contract is created, which holds the insurance-specific contract information.

When a carrier signs a contract, it becomes a part of the Contract Group Plan. Each Census Member can then enroll in the insurance plan. Group Census Member Plan is a junction object that connects Group Census Member and Contract Group Plan.

For a high-level look at the harmonized data model, look at the following diagram. The objects shown in blue are new standard Salesforce objects that correspond to the existing objects in the Vlocity Health and Insurance Package.

| 
Object in Standard Group Benefits Data Model

 | 

Description

 |
| --- | --- |
| 

[Group Census](https://developer.salesforce.com/docs/atlas.en-us.financial_services_cloud_object_reference.meta/financial_services_cloud_object_reference/sforce_api_objects_groupcensus.htm)

 | 

Represents a snapshot of statistics about eligible members (employees or members) of a group (employer or association) and their legal dependents. Use this entity in quoting, rating, and the subsequent enrollment process. Child object of employer or group Account.

 |
| 

[Group Census Member](https://developer.salesforce.com/docs/atlas.en-us.financial_services_cloud_object_reference.meta/financial_services_cloud_object_reference/sforce_api_objects_groupcensusmember.htm)

 | 

Represents personal information about a member, for example employee or association member, or their dependents. GroupCensusMember is used to estimate the insurance plan cost for the group. GroupCensusMember is also used in the enrollment process to retrieve the member and dependent details. Child object of GroupCensus.

 |
| 

[Group Class](https://developer.salesforce.com/docs/atlas.en-us.financial_services_cloud_object_reference.meta/financial_services_cloud_object_reference/sforce_api_objects_groupclass.htm)

 | 

Represents the classification of group members that receive similar benefits. Example classes include executives, union, and office workers. Child object of employer or group Account.

 |
| 

[Group Class Contribution](https://developer.salesforce.com/docs/atlas.en-us.financial_services_cloud_object_reference.meta/financial_services_cloud_object_reference/sforce_api_objects_groupclasscontribution.htm)

 | 

Represents employer or group contributions for GroupClass members and their dependents on a per product category such as medical, dental, or vision. Child object of GroupClass.

 |
| 

[Insurance Contract](https://developer.salesforce.com/docs/atlas.en-us.financial_services_cloud_object_reference.meta/financial_services_cloud_object_reference/sforce_api_objects_insurancecontract.htm)

 | 

Represents insurance-specific contract information. Extension of Contract.

 |
| 

[Contract Group Plan](https://developer.salesforce.com/docs/atlas.en-us.financial_services_cloud_object_reference.meta/financial_services_cloud_object_reference/sforce_api_objects_contractgroupplan.htm)

 | 

Represents a set of plans as part of the contract between the insurance carrier and the group. This set of plans corresponds to the plans included in the quote (as Quote Line Items). Child object of Contract.

 |
| 

[Group Census Member Plan](https://developer.salesforce.com/docs/atlas.en-us.financial_services_cloud_object_reference.meta/financial_services_cloud_object_reference/sforce_api_objects_groupcensusmemberplan.htm)

 | 

Represents the association of GroupCensusMember and ContractGroupPlan. Use this entity when census data includes previous member enrollment plan details and new member plan details. You can populate GroupCensusMemberPlan by reading the enrollment census in the enrollment services before creating insurance policies.

 |
| 

[Quote Line Item Group Class](https://developer.salesforce.com/docs/atlas.en-us.financial_services_cloud_object_reference.meta/financial_services_cloud_object_reference/sforce_api_objects_quotelineitemgroupclass.htm)

 | 

Represents the association of a Quote Line Item to GroupClass. Use this entity for large group quoting process when multiple group classes are attributed on a single quote line item. Child object of Quote.

 |

[](https://help.salesforce.com/s?language=en_US)

## Customer Experience Based on Licensing

To use group benefits in the Salesforce data model, check your add-on licenses and permission set license assignments. Financial Services Cloud and Health Cloud have different requirements. See [Give Users Access to Group Benefits in the Salesforce Data Model](https://help.salesforce.com/s/articleView?id=ind.insurance_give_users_access_to_group_benefits.htm&language=en_US&type=5 "To use group benefits in the Salesforce data model, check your add-on licenses and permission set license assignments.").

Did this article solve your issue?

Let us know so we can improve!

YesNo