---
title: "Insurance Policy Dynamic Attributes"
source: "https://help.salesforce.com/s/articleView?id=ind.insurance_admin_policies_dynamic_attributes.htm&language=en_US&type=5"
scraped: "2026-04-13"
filter: "ind.insurance_"
---# Insurance Policy Dynamic Attributes

Insurance Policy Dynamic Attributes[](https://help.salesforce.com/s?language=en_US)

You are here:

1.  [Salesforce Help](/s/?language=en_US)
2.  [Docs](/s/products?language=en_US)
3.  [Digital Insurance](https://help.salesforce.com/s/articleView?id=ind.insurance_admin_standard.htm&language=en_US&type=5)

# Insurance Policy Dynamic Attributes

Explore how dynamic attributes store values and how you query them with supported filters.

Use the virtual entities InsurancePolicyAttribute, InsPolicyCoverageAttribute, InsPolicyParticipantAttr, and InsPolicyAssetAttribute to store attribute data for insurance policies, coverages, participants, and assets. Policy creation automatically generates attribute records when you use a Digital Insurance license.

## Considerations and Limitations

Keep these considerations in mind when querying these dynamic attributes.

-   Use InsurancePolicyId, PolicyCoverageId, PolicyParticipantId, or PolicyAssetId to filter results.
-   Use the supported operators =, !=, or LIKE.
-   Avoid filtering records based on CreatedDate or LastModifiedDate, because those queries don’t return results.

## Example Queries

Example

Supported

`SELECT Id, AttributeValue FROM InsurancePolicyAttribute WHERE InsurancePolicyId = 'a1B5f00000XYZ123'`

Example

Unsupported

`SELECT Id FROM InsPolicyCoverageAttribute WHERE LastModifiedDate = TODAY`

#### See Also

-   [Insurance Policy Coverage Attribute](https://developer.salesforce.com/docs/atlas.en-us.financial_services_cloud_object_reference.meta/financial_services_cloud_object_reference/sforce_api_objects_inspolicycoverageattribute.htm)
-   [Insurance Policy Attribute](https://developer.salesforce.com/docs/atlas.en-us.financial_services_cloud_object_reference.meta/financial_services_cloud_object_reference/sforce_api_objects_insurancepolicyattribute.htm)
-   [Insurance Policy Participant Attribute](https://developer.salesforce.com/docs/atlas.en-us.financial_services_cloud_object_reference.meta/financial_services_cloud_object_reference/sforce_api_objects_inspolicyparticipantattr.htm)
-   [Insurance Policy Asset Attribute](https://developer.salesforce.com/docs/atlas.en-us.financial_services_cloud_object_reference.meta/financial_services_cloud_object_reference/sforce_api_objects_inspolicyassetattribute.htm)

Did this article solve your issue?

Let us know so we can improve!

YesNo