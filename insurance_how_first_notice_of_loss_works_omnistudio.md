---
title: "How First Notice of Loss Works"
source: "https://help.salesforce.com/s/articleView?id=ind.insurance_how_first_notice_of_loss_works_omnistudio.htm&language=en_US&type=5"
scraped: "2026-04-14"
filter: "ind.insurance_"
---# How First Notice of Loss Works

How First Notice of Loss Works[](https://help.salesforce.com/s?language=en_US)

You are here:

1.  [Salesforce Help](/s/?language=en_US)
2.  [Docs](/s/products?language=en_US)
3.  [Digital Insurance](https://help.salesforce.com/s/articleView?id=ind.insurance_admin_standard.htm&language=en_US&type=5)

# How First Notice of Loss Works

Now let's step through the OmniScript the same way, as a user sees it.

This OmniScript begins for a policyholder, broker, or agent after the policy number has been entered into the system, which finds the policy and uses the data in it.

The FNOL OmniScript starts by showing the user (us) the vehicles on the policy.

After we choose the vehicle involved in the incident, we choose what happened.

Next, we enter basic information about the incident. The date of the incident is important. The system uses that date to help determine whether the policyholder is covered for the incident.

Behind the scenes, the OmniScript calls a service that creates the initial claim record.

Now we enter more information about the damaged vehicle that's covered by the policy.

We enter information about the other damaged vehicle.

We enter information about who was injured and how badly.

We enter information about the police report, and can upload it now if we have a copy.

After we finish entering information, the system provides a claim confirmation that includes the claim number.

## See Also

[Claims First Notice of Loss](https://help.salesforce.com/s/articleView?id=ind.insurance_claims_first_notice_of_loss_619107.htm&language=en_US&type=5 "When policyholders, brokers, and insurance agents first notify an insurance provider about a loss, they use a First Notice of Loss (FNOL) flow. The FNOL flow kicks off claims processing, and supports the use of photos, police reports, and any other necessary files that support a claim.")

[Configure History Timelines with Claim History LWC](https://help.salesforce.com/s/articleView?id=ind.insurance_configure_history_timelines_with_insurance_history_lwc.htm&language=en_US&type=5 "You can configure the Insurance History Lightning web component (LWC) to display a timeline of quote, claim, or policy activity in a single, chronological feed that's easy to scan and drill into. See essential activity at a glance and expand content like notes and emails to dive into more detail.")

[Configure Insurance History with Claim History LWC DataPack](https://help.salesforce.com/s/articleView?id=ind.insurance_configure_insurance_history_with_claim_history_lwc_datapack_620180.htm&language=en_US&type=5 "You can configure the Insurance History Lightning web component to create a cohesive view of all things happening with a claim. A DataPack included with your org gets you started. It has story object configuration that brings essential content into a Claim History tab out of the box.")

[Claims Harmonization Overview](https://help.salesforce.com/s/articleView?id=ind.insurance_claims_harmonization_overview_600908.htm&language=en_US&type=5 "Claims harmonization involves moving claims data from custom objects in the Vlocity managed package object model to standard objects in the Salesforce object model. The Vlocity model supports the Asset → InsuranceClaim relationship between policies and claims. The Salesforce model supports the InsurancePolicy → Claim relationship between policies and claims. Services and LWCs are updated to work with claims data in the Salesforce data model.")

[Harmonized LWCs and Services](https://help.salesforce.com/s/articleView?id=ind.insurance_harmonized_lwcs_and_services_603569.htm&language=en_US&type=5 "You don't have to do anything special to make harmonized LWCs and services work with your harmonized data. They work as well with the Salesforce object model as they do with the Vlocity managed package object model.")

[Vlocity Insurance Claim to FSC Claim Harmonized Object Model Mapping](https://help.salesforce.com/s/articleView?id=ind.insurance_vlocity_insuranceclaimc_to_fsc_claim_harmonizedobject_model_mapping_600958.htm&language=en_US&type=5 "Learn how fields in the Vlocity managed package object model correspond to fields in the Salesforce object model. Use these field mappings when you create scripts that move claims data from one model to the other.")

Did this article solve your issue?

Let us know so we can improve!

YesNo