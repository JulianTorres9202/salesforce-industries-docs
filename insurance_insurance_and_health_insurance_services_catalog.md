---
title: "Insurance Services Catalog"
source: "https://help.salesforce.com/s/articleView?id=ind.insurance_insurance_and_health_insurance_services_catalog.htm&language=en_US&type=5"
scraped: "2026-04-14"
filter: "ind.insurance_"
---# Insurance Services Catalog

. Insurance Services Catalog[](https://help.salesforce.com/s?language=en_US)

You are here:

1.  [Salesforce Help](/s/?language=en_US)
2.  [Docs](/s/products?language=en_US)
3.  [Digital Insurance](https://help.salesforce.com/s/articleView?id=ind.insurance_admin_standard.htm&language=en_US&type=5)

# Insurance Services Catalog

Get quote, policy, and claims systems up and running by using an extensive catalog of Digital Insurance Platform services. The services are methods of Apex classes that carry out common actions for insurance companies and health plans. They help you build end-to-end business processes faster by reducing or eliminating the need for custom programming.

[](https://help.salesforce.com/s?language=en_US)

## Service Model Basics

Services support the Vlocity Open Interface protocol with the same call signature. Service detail topics each include a section for Remote Options, Input JSON, and Output JSON. To learn more about a specific service, click its method name.

Central to an understanding of services is an understanding of the product definition. Product administrators set up products with coverages, insured items, and rating facts, and map rating procedures in the product definition.

Insurance has a defined JSON product object model that is the JSON description of a product as it is set up in Salesforce. JSON product objects are used by many services and templates to pass runtime product data between them.

See [Product JSON Structure Model](https://help.salesforce.com/s/articleView?id=ind.insurance_product_json_structure_model_609451.htm&language=en_US&type=5 "The product JSON object provides a portable product data object for runtime use between services and templates.") for more information.

[](https://help.salesforce.com/s?language=en_US)

## Explore a Service

To try a service on your own, add a Remote Action element to an OmniScript or Integration Procedure. Then add any of the services in this catalog to the Remote Action and preview your OmniScript to see how it works.

## Service Listings by Class

Review service listings by class.

-   [Quote, Policy, Claims, and Group Benefits Service Listing by Class](https://help.salesforce.com/s/articleView?id=ind.insurance_insurance_and_health_insurance_services_catalog.htm&language=en_US&type=5#insurance_insurance_and_health_insurance_services_catalog__t_service_listing_by_class_625012)
    
    These services apply to quote, policy, claims administration. This listing also includes group benefits services in the Vlocity Health and Vlocity Insurance managed package.
    
-   [Group Benefits Standard Service Listing by Class](https://help.salesforce.com/s/articleView?id=ind.insurance_insurance_and_health_insurance_services_catalog.htm&language=en_US&type=5#insurance_insurance_and_health_insurance_services_catalog__section-gbstandardservicelistingbyclass)
    
    These services apply to group benefits in the Salesforce data model.
    

[](https://help.salesforce.com/s?language=en_US)

## Quote, Policy, Claims, and Group Benefits Service Listing by Class

These services apply to quote, policy, claims administration. This listing also includes Group Benefits services in the Vlocity Health and Vlocity Insurance managed package.

| 
Classes/Methods

 | 

Description

 |
| --- | --- |
| 

**ActionListService**

 |
| 

[processOnCreateActions](https://help.salesforce.com/s/articleView?id=ind.insurance_actionlistservice__processoncreateactions.htm&language=en_US&type=5 "This service executes the Vlocity Action set on the State Model version of the object.")

 | 

Executes the `OnCreate` Vlocity Action set at the State Model version of the object.

 |
| 

**HealthFeeScheduleDataService**

[](https://help.salesforce.com/s?language=en_US)Important

These services are retired from Vlocity Health  and Vlocity Insurance Spring '22 release and onwards.







 |
| 

[getBaseFees](https://help.salesforce.com/s/articleView?id=ind.insurance_healthfeescheduledataservice__getbasefees.htm&language=en_US&type=5 "Use this service to retrieve the currently active base fee schedule data—Description, Facility Price, and Non-Facility Price, and so forth—based on the date specified.")

 | 

This service retrieves the currently active base fee schedule data—Description, Facility Price, and Non-Facility Price, and so forth—based on the date specified.

 |
| 

[getProviderFees](https://help.salesforce.com/s/articleView?id=ind.insurance_healthfeescheduledataservice__getproviderfees.htm&language=en_US&type=5 "Use this service to retrieve data from the given provider fee schedule and use the supplied date to determine the appropriate base fee schedule version.")

 | 

This service retrieves data for the currently active provider fee schedule based on the specified date.

 |
| **InsAsyncBulkService** |
| [getRequestStatusById](https://help.salesforce.com/s/articleView?id=ind.insurance_insasyncbulkservice_getrequeststatusbyid.htm&language=en_US&type=5 "Use this service to get the status of the async bulk request and its details associated with the request.") | Use this service to get the status of the async bulk request and its details associated with the request. |
| [getRequestStatusByUser](https://help.salesforce.com/s/articleView?id=ind.insurance_insasyncbulkservice_getrequeststatusbyuser.htm&language=en_US&type=5 "Use this service to get the status of async bulk requests and information about the associated async request items.") | Use this service to get the status of async bulk requests and information about the associated async request items. |
| 

**InsCensusService**

 |
| 

[addMembers](https://help.salesforce.com/s/articleView?id=ind.insurance_inscensusservice__addmembers.htm&language=en_US&type=5 "Use this service to add members to a census via an input JSON. Guest user access is enabled for this service.")

 | 

Use this service to add members to a census via JSON.

 |
| 

[addPlanSelections](https://help.salesforce.com/s/articleView?id=ind.insurance_inscensusservice__addplanselections.htm&language=en_US&type=5 "Use this service to insert pre-enrolled plans for each member specified in the input.")

 | 

Use this service to insert pre-enrolled plans for each member specified in the input.

 |
| 

[cloneCensus](https://help.salesforce.com/s/articleView?id=ind.insurance_inscensusservice__clonecensus.htm&language=en_US&type=5 "Use this service to clone a census and all the census members.")

 | 

Use this service to clone a census and all the census members.

 |
| 

[ConvertLeadAnd CreateCensus](https://help.salesforce.com/s/articleView?id=ind.insurance_inscensusservice__convertleadandcreatecensus.htm&language=en_US&type=5 "Use this service to extend the Lead Conversion Salesforce feature, allowing users to include Lead census information and map this data to the Vlocity Group Account Census objects while converting the Lead.")

 | 

Use this service to extend the Lead Conversion Salesforce feature, allowing users to include Lead census information and map this data to the Vlocity Group Account Census objects while converting the Lead.

 |
| 

[createAccounts](https://help.salesforce.com/s/articleView?id=ind.insurance_inscensusservice__createaccounts.htm&language=en_US&type=5 "Use this service to create Person Accounts for the members in the given census.")

 | 

Create Person Accounts for members in the given census.

 |
| 

[createContacts](https://help.salesforce.com/s/articleView?id=ind.insurance_inscensusservice__createcontacts.htm&language=en_US&type=5 "Use this service to create Contacts for census members and community (portal) users.")

 | 

Creates Contacts for census members, and also creates community (portal) users.

 |
| 

[deleteMembers](https://help.salesforce.com/s/articleView?id=ind.insurance_inscensusservice__deletemembers.htm&language=en_US&type=5 "Use this service to delete the members from a census.")

 | 

Use this service to delete the members from a census.

 |
| 

[getFields](https://help.salesforce.com/s/articleView?id=ind.insurance_inscensusservice__getfields.htm&language=en_US&type=5 "Use this service to retrieve field definitions and field API names for group census members and group census plans. Guest user access is enabled for this service.")

 | 

Retrieves field definitions and field API names for group census members and group census plans.

 |
| 

[getMemberRatingFacts](https://help.salesforce.com/s/articleView?id=ind.insurance_inscensusservice__getmemberratingfacts.htm&language=en_US&type=5 "Use this service to retrieve rating fact data for census members, for use as user Inputs for the InsProductService:getRatedProducts service.")

 | 

This service retrieves rating fact data for census members, for use as user Inputs for the [getRatedGroupProducts](https://help.salesforce.com/s/articleView?id=ind.insurance_insproductservice__getratedgroupproducts.htm&language=en_US&type=5 "This service is used only with small group products that use a census. The service allows the products to be kept with the product service.") service.

 |
| 

[getMembers](https://help.salesforce.com/s/articleView?id=ind.insurance_inscensusservice__getmembers.htm&language=en_US&type=5 "Use this service to retrieve the members of a census. It also retrieves the fields. Guest user access is enabled for this service.")

 | 

Use this service to retrieve the first 2,000 census members of the given census.

 |
| 

[getMembersWithPlans](https://help.salesforce.com/s/articleView?id=ind.insurance_inscensusservice__getmemberswithplans.htm&language=en_US&type=5 "Use this service to retrieve members of a census and their pre-enrolled plans. This service also retrieves field definitions for the GroupCensusMember__c and GroupCensusMemberPlan__c fields.")

 | 

Use this service to retrieve members of a census and their pre-enrolled plans as well as field definitions for the `GroupCensusMember__c` and `GroupCensusMemberPlan__c` fields.

 |
| 

[getQualifiedCensusMembers](https://help.salesforce.com/s/articleView?id=ind.insurance_inscensusservice__getqualifiedcensusmembers.htm&language=en_US&type=5 "Use this service to retrieve members that qualify for rating per family. Filters out dependents based on age, region, number of dependents.")

 | 

Use this service to retrieve members that qualify for rating per family. Filters out dependents based on age, region, number of dependents.

 |
| 

[sendMassEmail](https://help.salesforce.com/s/articleView?id=ind.insurance_inscensusservice__sendmassemail.htm&language=en_US&type=5 "Use this service to send emails to all members of a census. For example, you can use this service to send an invitation to enroll in a health insurance plan to all members of a customer's census.")

 | 

Sends all employees in a census an email, kicking off an enrollment process.

 |
| 

[setCensusRatingFacts](https://help.salesforce.com/s/articleView?id=ind.insurance_inscensusservice__setcensusratingfacts.htm&language=en_US&type=5 "Use this service to associate a Rating Fact spec to a census, and automatically extract information from the census fields to populate the Attribute Selected Values for the census, based on the Rating Fact.")

 | 

Associates a Rating Fact spec to a census.

 |
| 

[setMemberRatingFacts](https://help.salesforce.com/s/articleView?id=ind.insurance_inscensusservice__setmemberratingfacts.htm&language=en_US&type=5 "Use this service to associate a Rating Facts Spec to a census member, and automatically extract information from the census member fields to populate the Attribute Selected Values for the member, based on the Rating Fact.")

 | 

Associates a Rating Fact spec to a census member.

 |
| 

[updateMembers](https://help.salesforce.com/s/articleView?id=ind.insurance_inscensusservice__updatemembers.htm&language=en_US&type=5 "Use this service to update members in a census to the values in the input JSON. Guest user access is enabled for this service.")

 | 

Use this service to update all the members listed to the values in the JSON.

 |
| 

[updateMembersWithPlans](https://help.salesforce.com/s/articleView?id=ind.insurance_inscensusservice__updatememberswithplans.htm&language=en_US&type=5 "Use this service to populate a census with primary members, their dependents, and their pre-enrolled plan.")

 | 

Use this service to populate a census with primary members, their dependents, and their pre-enrolled plan.

 |
| 

**InsClaimCoverageService**

 |
| 

[createUpdateCoverage](https://help.salesforce.com/s/articleView?id=ind.insurance_insclaimcoverageservice_createupdatecoverage.htm&language=en_US&type=5 "Use this service to create a claim coverage or update an existing claim coverage.")

 | 

Creates a new claim coverage or updates an existing claim coverage.

 |
| 

[invokeProductRules](https://help.salesforce.com/s/articleView?id=ind.insurance_insclaimcoverageservice__invokeproductrules.htm&language=en_US&type=5 "Use this service when creating claim coverages to invoke product rules for state transitions.")

 | 

Runs rules for the claim coverage.

 |
| 

**InsClaimItemService**

 |
| 

[add](https://help.salesforce.com/s/articleView?id=ind.insurance_insclaimitemservice__add.htm&language=en_US&type=5 "Use this service to add a claim line item to a specified claim item object.")

 | 

Adds a claim line item to a specified claim item object.

 |
| 

[](https://help.salesforce.com/s?language=en_US)[calculateCoverages](https://help.salesforce.com/s/articleView?id=ind.insurance_insclaimitemservice__calculatecoverages.htm&language=en_US&type=5 "Use this service to calculate the coverage amount and adjusted amount for a claim line item. These amounts are used as payment amount when the claims adjuster pays the claim line item.")

 | 

Calculates the payment amount for a claim line item.

 |
| 

[cancelPayments](https://help.salesforce.com/s/articleView?id=ind.insurance_insclaimitemservice__cancelpayments.htm&language=en_US&type=5 "Use this service to cancel claim loss and expense payments.")

 | 

Cancels claim loss and expense payments.

 |
| 

[claimCoverageValuation](https://help.salesforce.com/s/articleView?id=ind.insurance_insclaimitemservice_claimcoveragevaluation.htm&language=en_US&type=5 "Use this service to verify that users have the authority to pay or approve amounts in different types of financial activities.")

 | 

Verifies that users have the authority to pay or approve amounts in different types of financial activities.

 |
| 

[createPayments](https://help.salesforce.com/s/articleView?id=ind.insurance_insclaimitemservice__createpayments.htm&language=en_US&type=5 "Use this service to create and save claim payment records based on the line item IDs and the groupPayments option.")

 | 

Creates and saves claim payment records based on the line item IDs and the `groupPayments` option.

 |
| 

[delete](https://help.salesforce.com/s/articleView?id=ind.insurance_insclaimitemservice__delete.htm&language=en_US&type=5 "Use this service to delete a claim line item from a claim object.")

 | 

Deletes a claim line item from a claim object.

 |
| 

[getClaimItems](https://help.salesforce.com/s/articleView?id=ind.insurance_insclaimitemservice__getclaimitems.htm&language=en_US&type=5 "Use this service to retrieve the list of Claimants and their corresponding open ClaimCoverages with the respective line items (loss or expense).")

 | 

Retrieves claim line items from a specified claim.

 |
| 

[getClaimLineItemFields](https://help.salesforce.com/s/articleView?id=ind.insurance_insclaimitemservice__getclaimlineitemfields.htm&language=en_US&type=5 "Use this service to retrieve the list of fields of a field set (and optionally the field's values). This field set is specific for a particular CoverageSpec.")

 | 

Gets a list of fields and values for claim line items in a specified claim.

 |
| 

[getCoverages](https://help.salesforce.com/s/articleView?id=ind.insurance_insclaimitemservice__getcoverages.htm&language=en_US&type=5 "Use this service to get coverages that apply to a specific claim.")

 | 

Gets coverages that apply to a specific claim.

 |
| 

[getInsuranceCodes](https://help.salesforce.com/s/articleView?id=ind.insurance_insclaimitemservice__getinsurancecodes.htm&language=en_US&type=5 "Use this service to get a list of insurance codes that correspond to the coverages associated with claims.")

 | 

Gets a list of insurance codes that correspond to the coverages associated with claims.

 |
| 

[getInvolvedItems](https://help.salesforce.com/s/articleView?id=ind.insurance_insclaimitemservice__getinvolveditems.htm&language=en_US&type=5 "Use this service to get a list of involved items (property) and/or involved people (parties) for a specific claim.")

 | 

Returns a list of involved items (property) and/or involved people (parties) for a specific claim.

 |
| 

[invokeInitiatePaymentIP](https://help.salesforce.com/s/articleView?id=ind.insurance_insclaimitemservice__invokeinitiatepaymentip.htm&language=en_US&type=5 "Use this service to initiate loss or expense payments.")

 | 

Initiates loss or expense payments.

 |
| 

[saveInvolvedItem](https://help.salesforce.com/s/articleView?id=ind.insurance_insclaimitemservice__saveinvolveditem.htm&language=en_US&type=5 "Use this service to update the total reserve amount of an involved property or involved injury record.")

 | 

Updates the total reserve amount of an involved property or involved injury record.

 |
| 

[update](https://help.salesforce.com/s/articleView?id=ind.insurance_insclaimitemservice__update.htm&language=en_US&type=5 "Use this service to update a claim line item to a specified claim item object.")

 | 

Updates a claim line item to a specified claim item object.

 |
| 

**InsClaimRecoveryService**

 |
| 

[getRecoveries](https://help.salesforce.com/s/articleView?id=ind.insurance_insclaimrecoveryservice__getrecoveries.htm&language=en_US&type=5 "Use this service to get a list of claim recoveries (InsuranceClaimRecovery__c) based on a specified claim Id or claim number.")

 | 

Gets a list of claim recoveries (**InsuranceClaimRecovery\_\_c**) based on a specified claim Id or claim number.

 |
| 

[save](https://help.salesforce.com/s/articleView?id=ind.insurance_insclaimrecoveryservice__save.htm&language=en_US&type=5 "Use this service to accept an input of a list of information, which is transformed to create and update records for the InsuranceClaimRecovery__c, an object that represents the recovery of funds for a claim.")

 | 

Accepts an input of a list of information, which is transformed to create and update records for the InsuranceClaimRecovery\_\_c, an object that represents the recovery of funds for a claim.

 |
| 

**InsClaimService**

 |
| 

createUpdateClaim

 | 

Creates or updates a claim.

 |
| 

[createUpdateClaimRecoveries](https://help.salesforce.com/s/articleView?id=ind.insurance_insclaimrecoveryservice__createupdateclaimrecoveries.htm&language=en_US&type=5 "Use this service to create or update records that represent a recovery of funds on an insurance claim.")

 | 

Use this service to create or update records that represent a recovery of funds on an insurance claim.

 |
| 

[getClaimRecoveries](https://help.salesforce.com/s/articleView?id=ind.insurance_insclaimrecoveryservice__getclaimrecoveries.htm&language=en_US&type=5 "Use this service to get a list of claim recoveries for a claim.")

 | 

Use this service to get a list of claim recoveries for a claim.

 |
| 

[getRuleLogs](https://help.salesforce.com/s/articleView?id=ind.insurance_insclaimservice__getrulelogs.htm&language=en_US&type=5 "Use this service to retrieve rule logs for a claim, sorted by execution date in ascending order.")

 | 

Retrieves rule logs for a target quote, sorted by execution date in ascending order.

 |
| 

[invokeProductRules](https://help.salesforce.com/s/articleView?id=ind.insurance_insclaimservice__invokeproductrules.htm&language=en_US&type=5 "Use this service in claim flows to invoke underwriting rules you've added to a product.")

 | 

Invokes a set of underwriting rules for a product.

 |
| 

[invokeRules](https://help.salesforce.com/s/articleView?id=ind.insurance_insclaimservice__invokerules.htm&language=en_US&type=5 "Use this service to invoke state transition rules associated with a target state transition on a target claim. If the rules satisfy the transition criteria, this service executes actions associated with the transition, optionally logs the results of the rule executions, and transitions the target claim to the new state.")

 | 

Invokes state transition rules associated with a target state transition on a target claim.

 |
| 

[verifyCoverage](https://help.salesforce.com/s/articleView?id=ind.insurance_insclaimservice__verifycoverage.htm&language=en_US&type=5 "Use this service to verify valid insurance coverage for a policyholder who is filing a claim.")

 | 

Verifies valid insurance coverage for a policyholder who is filing a claim.

 |
| 

**InsCommissionService**

 |
| 

[adjust](https://help.salesforce.com/s/articleView?id=ind.insurance_inscommissionservice__adjust.htm&language=en_US&type=5 "Use this service to adjust a Producer Commission amount.")

 | 

Adjusts a commission based on user inputs.

 |
| 

[calculate](https://help.salesforce.com/s/articleView?id=ind.insurance_inscommissionservice__calculate.htm&language=en_US&type=5 "Use this service to calculate the commission for a producer.")

 | 

Calculates the commission for a producer.

 |
| 

**InsContractService**

 |
| 

[createLargeSizeRenewQuoteInBatch](https://help.salesforce.com/s/articleView?id=ind.insurance_inscontractservice__createlargesizerenewquoteinbatch.htm&language=en_US&type=5 "Use this service to allow for the control of how many Apex jobs to initiate, and the number of batches to run per Apex job, for contracts with a large number of root line items.")

 | 

This service allows for the control of how many Apex jobs to initiate, and the number of batches to run per Apex job, for contracts with a large number of root line items.

 |
| 

[createRenewQuotesInBatch](https://help.salesforce.com/s/articleView?id=ind.insurance_inscontractservice__createrenewquotesinbatch.htm&language=en_US&type=5 "Use this service to allow you to control how many Apex jobs to initiate, and the number of batches to run per Apex job, for a large number of contract renewals.")

 | 

This service allows you to control how many Apex jobs to initiate, and the number of batches to run per Apex job, for a large number of contract renewals.

 |
| 

[createUpdateContract](https://help.salesforce.com/s/articleView?id=ind.insurance_inscontractservice__createupdatecontract.htm&language=en_US&type=5 "Use this service to create or update a contract using the output of the InsQuoteService:getQuoteDetail service.")

 | 

Creates a contract or updates an existing contract.

 |
| 

[getContractDetail](https://help.salesforce.com/s/articleView?id=ind.insurance_inscontractservice__getcontractdetail.htm&language=en_US&type=5 "Use this service to return a ProductJSON that you can use with the InsQuoteService:createUpdateQuote service to update the Contract JSON with, or to create a renewal quote with replacement products.")

 | 

Calls a contract record.

 |
| 

[invokeProductRules](https://help.salesforce.com/s/articleView?id=ind.insurance_inscontractservice__invokeproductrules.htm&language=en_US&type=5 "Use this service in contract flows to invoke underwriting rules you've added to a product.")

 | 

Invokes a set of underwriting rules for a product.

 |
| 

**InsEnrollmentService**

 |
| 

[enrollMembers](https://help.salesforce.com/s/articleView?id=ind.insurance_insenrollmentservice__enrollmembers.htm&language=en_US&type=5 "Use this service to enroll census members into their selected plans.")

 | 

This service enrolls census members into their selected plans.

 |
| 

[enrollPlans](https://help.salesforce.com/s/articleView?id=ind.insurance_insenrollmentservice__enrollplans.htm&language=en_US&type=5 "Use this service to create policy (Asset or Insurance Policy) records for enrollee selected medical, dental, vision, and other plans.")

 | 

Creates all policies for enrollment.

 |
| 

[findEnrollees](https://help.salesforce.com/s/articleView?id=ind.insurance_insenrollmentservice__findenrollees.htm&language=en_US&type=5 "Use this service to allow a user to search for a list of enrolled clients.")

 | 

Allows a user to search for a list of enrolled clients.

 |
| 

[getEligibleMemberProducts](https://help.salesforce.com/s/articleView?id=ind.insurance_insenrollmentservice__geteligiblememberproducts.htm&language=en_US&type=5 "Use this service to return eligible products for members of a census and groups them by type.")

 | 

This service returns eligible products for members of a census and groups them by type.

 |
| 

[getEnrolleePolicies](https://help.salesforce.com/s/articleView?id=ind.insurance_insenrollmentservice__getenrolleepolicies.htm&language=en_US&type=5 "Use this service to allow a user to search for the policies of a given set of enrolled clients.")

 | 

This service allows a user to search for the policies of given enrolled clients.

 |
| 

\>getMemberEnrollments

 | 

This service retrieves current enrollments for a member so they can make benefit changes. It also takes one or more census member Ids and returns enrolled plans for the member and its dependents.

 |
| 

[getRatedProducts](https://help.salesforce.com/s/articleView?id=ind.insurance_insenrollmentservice__getratedproducts.htm&language=en_US&type=5 "Use the service to return a list of eligible products for a given enrollee and their dependents. The rate band prices for each product are displayed when the plan's rate type is Composite.")

 | 

Pulls contract-based eligible policies with prices for the active user.

 |
| 

[modifyEnrollment](https://help.salesforce.com/s/articleView?id=ind.insurance_insenrollmentservice__modifyenrollment.htm&language=en_US&type=5 "Use this service to modify the enrollments, dependents, and coverages of each enrollment for input members. You can use this service to add new or remove existing plans or add or remove dependents.")

 | 

This service is used to modify the enrollments, dependents, and coverages of each enrollment for input members.

 |
| 

**InsFormularyService**

 |
| 

[getListOfCoveredDrugs](https://help.salesforce.com/s/articleView?id=ind.insurance_insformularyservice__getlistofcovereddrugs.htm&language=en_US&type=5 "Use this service to get a list of brand name or generic drugs in a formulary that are part of a health plan.")

 | 

Use this service to get a list of brand name or generic drugs in a formulary that are part of a health plan.

 |
| 

[getListOfDrugs](https://help.salesforce.com/s/articleView?id=ind.insurance_insformularyservice__getlistofdrugs.htm&language=en_US&type=5 "Use this service to get a list of drugs within their effective marketing dates.")

 | 

Use this service to get a list of drugs within their effective marketing dates.

 |
| 

[getListOfPlanMedicationPrices](https://help.salesforce.com/s/articleView?id=ind.insurance_insformularyservice__getlistofplanmedicationprices.htm&language=en_US&type=5 "Use this service to get a list of prices for covered drugs within a provider network, including copay calculation.")

 | 

Use this service to get a list of prices for covered drugs within a provider network, including copay calculation.

 |
| 

[getProducts](https://help.salesforce.com/s/articleView?id=ind.insurance_insformularyservice__getproducts.htm&language=en_US&type=5 "One of the eligibility rules to retrieve health plans is to ensure that the plan covers the medications that the customer is taking. Use this service to facilitate the process to retrieve eligible products linked to Formularies, which contains medications (drugs) where the customer (accountId) medications are included.")

 | 

Use this service to facilitate the process of retrieving eligible products linked to Formularies, which contains medications (`drugs`) where the customer (`accountId`) medications are included.

 |
| **InsGroupClassService** |
| [getGroupClassByAccount](https://help.salesforce.com/s/articleView?id=ind.insurance_insgroupclassservicegetgroupclassesbyaccount.htm&language=en_US&type=5 "Fetch the GroupClasses associated with the given AccountId.") | Fetches the Group Classes associated with the given `AccountId`. |
| [getGroupClassesByContract](https://help.salesforce.com/s/articleView?id=ind.insurance_insgroupclassservice_getgroupclassesbycontract.htm&language=en_US&type=5 "​Use this service to get a list of eligible plans with the contractId that’s provided as input, and a list of eligible plans for the GroupclassId that’s provided as input.​") | Use this service to get a list of eligible plans with the `contractId` that's provided as input, and a list of eligible plans for the GroupclassId that's provided as input. |
| 

**InsPolicyBillingService**

 |
| 

[generateBillingAccountStatements](https://help.salesforce.com/s/articleView?id=ind.insurance_inspolicybillingservice__generatebillingaccountstatements.htm&language=en_US&type=5 "Use this service to generate statements for accounts that contain policies with billing accounts that have Due Date = today.")

 | 

Generates billing statements for accounts.

 |
| 

[generateDirectBillingStatements](https://help.salesforce.com/s/articleView?id=ind.insurance_inspolicybillingservice__generatedirectbillingstatements.htm&language=en_US&type=5 "Use this service to generate statements for accounts containing policies with direct billing whose due date is equal to today's date plus ten (10) days.")

 | 

Generates statements for direct billing.

 |
| 

**InsPolicyRevenueScheduleService**

 |
| 

[cancelRevenueSchedule](https://help.salesforce.com/s/articleView?id=ind.insurance_inspolicyrevenuescheduleservice__cancelrevenueschedule.htm&language=en_US&type=5 "When a policy is canceled, this service adjusts the revenue schedule to calculate revenue until the cancellation date.")

 | 

Adjusts the last revenue schedule line item, calculating revenue based on the cancellation date of the canceled policy.

 |
| 

[createRevenueSchedule](https://help.salesforce.com/s/articleView?id=ind.insurance_inspolicyrevenuescheduleservice__createrevenueschedule.htm&language=en_US&type=5 "This service creates a monthly revenue schedule for a policy, starting on the effective date of the policy and ending on the expiration date of the policy term.")

 | 

Creates a monthly revenue schedule for a policy, starting on the effective date of the policy and ending on the expiration date.

 |
| 

[modifyRevenueSchedule](https://help.salesforce.com/s/articleView?id=ind.insurance_inspolicyrevenuescheduleservice__modifyrevenueschedule.htm&language=en_US&type=5 "This service takes in the modifications done to the policy. Based on the changes to total policy premium and the modification date, it recalculates the revenue schedule to adjust the unpaid monthly premiums (unearned revenue).")

 | 

Takes in the modifications done to the policy. Based on the changes to total policy premium and the modification date, it recalculates the revenue schedule to adjust the monthly premiums (earned and unearned revenue).

 |
| 

**InsPolicyTermsService**

 |
| 

getCurrentStanding

 | 

Gets a list of amounts that represent the current standing of the policy terms associated with a policy or a claim.

 |
| 

**InsPolicyService**

 |
| 

[calculateTaxesAndFees](https://help.salesforce.com/s/articleView?id=ind.insurance_inspolicyservice__calculatetaxesandfees.htm&language=en_US&type=5 "Use this service to calculate and save taxes and fees on a target asset (policy).")

 | 

Use this service to calculate and save taxes and fees on a target asset (policy).

 |
| 

[cancelPolicy](https://help.salesforce.com/s/articleView?id=ind.insurance_inspolicyservice__cancelpolicy.htm&language=en_US&type=5 "Use this service to cancel an existing insurance policy.")

 | 

Cancels a policy.

 |
| 

[createMultiRootPolicy](https://help.salesforce.com/s/articleView?id=ind.insurance_inspolicyservice_createmultirootpolicy.htm&language=en_US&type=5 "Use this service to issue a multi-root policy from a quote.")

 | 

Issues a multi-root policy from a quote.

 |
| 

[createMultiRootPolicyVersion](https://help.salesforce.com/s/articleView?id=ind.insurance_inspolicyservice_createmultirootpolicyversion.htm&language=en_US&type=5 "Use this service to endorse a multi-root policy from an endorsed quote.")

 | 

Endorses a multi-root policy from an endorsed quote.

 |
| [createOutOfSequencePolicyVersion](https://help.salesforce.com/s/articleView?id=ind.insurance_inspolicyservice__createoutofsequencepolicyversion.htm&language=en_US&type=5 "Use this service to initiate an out-of-sequence endorsement for a given policy.") | Initiates an out-of-sequence endorsement for a given policy. |
| 

[createPolicyVersion](https://help.salesforce.com/s/articleView?id=ind.insurance_inspolicyservice__createpolicyversion.htm&language=en_US&type=5 "Use this service to create a new version of an existing policy, while maintaining the existing policy record as-is.")

 | 

Creates a new version of an existing policy, while leaving the original policy record as is.

 |
| 

[createPaymentSchedule](https://help.salesforce.com/s/articleView?id=ind.insurance_inspolicyservice__createpaymentschedule.htm&language=en_US&type=5 "The InsPolicyService:createPaymentSchedule service creates a payment schedule (and optionally an initial payment transaction) for the target policy. This applies to Insurance Policy object only. The Policy (Asset) object is not supported.")

 | 

Creates a payment schedule for the policy.

 |
| 

[createReinstatementPolicy](https://help.salesforce.com/s/articleView?id=ind.insurance_inspolicyservice_createreinstatementpolicy.htm&language=en_US&type=5 "Use this service to reinstate a canceled policy.")

 | 

Reinstates a canceled policy.

 |
| 

[createRenewalPolicy](https://help.salesforce.com/s/articleView?id=ind.insurance_inspolicyservice__createrenewalpolicy.htm&language=en_US&type=5 "Use this service to create a renewal policy from an existing policy.")

 | 

Creates a renewal policy from an existing policy.

 |
| 

[createRenewalQuote](https://help.salesforce.com/s/articleView?id=ind.insurance_inspolicyservice__createrenewalquote.htm&language=en_US&type=5 "Use this service to create a renewal quote for an existing policy.")

 | 

Creates a renewal quote for an existing policy.

 |
| 

[createTransaction](https://help.salesforce.com/s/articleView?id=ind.insurance_inspolicyservice__createtransaction.htm&language=en_US&type=5 "Use this service to create a transaction on a target policy.")

 | 

Creates a new transaction for a policy.

 |
| 

[createUpdatePolicy](https://help.salesforce.com/s/articleView?id=ind.insurance_inspolicyservice__createupdatepolicy.htm&language=en_US&type=5 "Use this service to create a new insurance policy or to update an existing policy with new information.")

 | 

Creates or updates a policy and its insured items.

 |
| 

[createPolicyTerms](https://help.salesforce.com/s/articleView?id=ind.insurance_inspolicyservice__createpolicyterms.htm&language=en_US&type=5 "Create policy terms in the AssetTerm__c or InsurancePolicyTerm__c (for Salesforce FSC) object for all the power attributes at the Policy and PolicyCoverage level. A power attribute is an attribute that has an attribute class, attribute scope, applicable item, and applicable actions.")

 | 

Creates policy terms in the **AssetTerm\_\_c** object for all the power attributes at the Asset and AssetCoverage level.

 |
| 

[getInsuredItems](https://help.salesforce.com/s/articleView?id=ind.insurance_inspolicyservice__getinsureditems.htm&language=en_US&type=5 "Use this service to find and return insured items and insured parties from a policy (asset).")

 | 

Gets insured items from a policy.

 |
| 

[getModifiedPolicy](https://help.salesforce.com/s/articleView?id=ind.insurance_inspolicyservice__getmodifiedpolicy.htm&language=en_US&type=5 "Use this service when a user makes changes to the insured items or insured parties in an existing policy. The service takes the changes the user makes and returns modified policy data, including the recalculated price.")

 | 

Gets the policy as it has been modified by user inputs.

 |
| [getOutOfSequenceEndorsementStatus](https://help.salesforce.com/s/articleView?id=ind.insurance_inspolicyservice_getoutofsequenceendorsementstatus.htm&language=en_US&type=5 "Use this service to retrieve the current status of the OutOfSequenceEndorsement async job. The service accepts jobId, policyId, or referencePolicyNumber as an input to fetch the out-of-sequence endorsement operation status.") | Retrieves the current status of the OutOfSequenceEndorsement async job. |
| 

[getPaymentSchedule](https://help.salesforce.com/s/articleView?id=ind.insurance_inspolicyservice__getpaymentschedule.htm&language=en_US&type=5 "The InsPolicyService:getPaymentSchedule service returns the payment schedule of the InsurancePolicy. The Policy (Asset) object is not supported.")

 | 

Retrieves the payment schedule.

 |
| 

[getPolicyAsyncJobStatus](https://help.salesforce.com/s/articleView?id=ind.insurance_inspolicyservice_getpolicyasyncjobstatus.htm&language=en_US&type=5 "Use this service to fetch the status of the asynchronous batch job.")

 | 

Fetches the status of the asynchronous batch job.

.

 |
| 

[getPolicyDetails](https://help.salesforce.com/s/articleView?id=ind.insurance_inspolicyservice__getpolicydetails.htm&language=en_US&type=5 "Use this service to get the coverages, insured items, pricing, and other information for an existing insurance policy, including optional coverages that weren't selected.")

 | 

Gets the policy (asset) object.

 |
| 

[getPolicyVersions](https://help.salesforce.com/s/articleView?id=ind.insurance_inspolicyservice__getpolicyversions.htm&language=en_US&type=5 "Use this service to retrieve the different versions of a policy. The service returns a list of policies with high level fields determined by the Policy field set PolicyCompareHeader.")

 | 

Retrieves the different versions of a policy.

 |
| 

[getRuleLogs](https://help.salesforce.com/s/articleView?id=ind.insurance_inspolicyservice__getrulelogs.htm&language=en_US&type=5 "This service retrieves rule logs for a target policy, sorted by execution date in ascending order.")

 | 

Retrieves rule logs for a target policy, sorted by execution date in ascending order.

 |
| 

[initiateLapseGracePeriod](https://help.salesforce.com/s/articleView?id=ind.insurance_inspolicyservice__initiatelapsegraceperiod.htm&language=en_US&type=5 "This service initiates a grace period on a policy, lapses a policy, or does nothing to a policy, depending on factors of the policy.")

 | 

Initiates a grace period after a policy lapses, but before it gets canceled.

 |
| 

[invokeProductRules](https://help.salesforce.com/s/articleView?id=ind.insurance_inspolicyservice__invokeproductrules.htm&language=en_US&type=5 "Use this service with a policy to invoke underwriting rules you've added to a product.")

 | 

Invokes a set of underwriting rules for a product.

 |
| 

[modifyPaymentSchedule](https://help.salesforce.com/s/articleView?id=ind.insurance_inspolicyservice__modifypaymentschedule.htm&language=en_US&type=5 "Use this service to modify an existing payment schedule based on a new Premium Frequency.")

 | 

Modifies the payment schedule of this policy.

 |
| 

[prepareToCancelPolicy](https://help.salesforce.com/s/articleView?id=ind.insurance_inspolicyservice__preparetocancelpolicy.htm&language=en_US&type=5 "Use this service to calculate the premium price difference before canceling a policy. The service prorates the premium, fee, and tax amounts, and calculates the premium, fee, and tax refund.")

 | 

Calculates the difference between the original premium and the premium up to the cancellation date.

 |
| 

[prepareToRenewPolicy](https://help.salesforce.com/s/articleView?id=ind.insurance_inspolicyservice__preparetorenewpolicy.htm&language=en_US&type=5 "Use this service to calculate the amount required for renewing an existing policy. This service returns renewal premium, taxes, and fees, or the renewal policy JSON without creating a policy.")

 | 

Calculates the amount required for renewing an existing policy. This service returns renewal premium, taxes, and fees, or the renewal policy JSON without creating a policy.

 |
| 

[removeInsuredItem](https://help.salesforce.com/s/articleView?id=ind.insurance_inspolicyservice__removeinsureditem.htm&language=en_US&type=5 "Use this service to remove an insured item from an existing policy.")

 | 

Removes an insured item from a policy record.

 |
| 

[renewPoliciesInBatch](https://help.salesforce.com/s/articleView?id=ind.insurance_inspolicyservice__renewpoliciesinbatch.htm&language=en_US&type=5 "Use this service to control the number of Apex jobs to initiate, and the number of batches to run per Apex job, for a large number of policy renewals.")

 | 

Controls the number of Apex jobs to initiate, and the number of batches to run per Apex job, for a large number of policy renewals.

 |
| 

[verifyCoverage](https://help.salesforce.com/s/articleView?id=ind.insurance_inspolicyservice__verifycoverage.htm&language=en_US&type=5 "Use this service to verify valid insurance coverage for a policyholder who is filing a claim.")

 | 

Verifies that an insurance policy includes coverage on the date the claim is filed for properties and injuries claimed.

 |
| **InsProductAsyncService** |
| [fetchProductsPrice](https://help.salesforce.com/s/articleView?id=ind.insurance_insproductasyncratingservicefetchproductsprice.htm&language=en_US&type=5 "Use this service to fetch asynchronous rating results.") | Fetches asynchronous rating results. |
| [fetchRepriceProductPrice](https://help.salesforce.com/s/articleView?id=ind.insurance_insproductasyncratingservicefetchrepriceproductprice.htm&language=en_US&type=5 "Use this service to fetch asynchronous rating results for a reprice product request.") | Fetches asynchronous rating results for a reprice product request. |
| [repriceProduct](https://help.salesforce.com/s/articleView?id=ind.insurance_insproductasyncratingservicerepriceproduct.htm&language=en_US&type=5 "Asynchronously recalculate the price of a product based on selectedProduct JSON and userInput.") | Asynchronously recalculates the price of a product based on `selectedProduct` JSON and `userInput`. |
| [startAsyncRating](https://help.salesforce.com/s/articleView?id=ind.insurance_insproductasyncratingservicestartasyncrating.htm&language=en_US&type=5 "Asynchronously calculate product prices based on a list of product IDs.") | Asynchronously calculates product prices based on a list of product IDs. |
| 

**InsProductJSONService**

 |
| 

[getAttributes](https://help.salesforce.com/s/articleView?id=ind.insurance_insproductjsonservice__getattributes.htm&language=en_US&type=5 "Use this service to get the attributes nodes of the ProductJSON.")

 | 

Gets the attributes from a specified product JSON.

 |
| 

[getCoverageChanges](https://help.salesforce.com/s/articleView?id=ind.insurance_insproductjsonservice__getcoveragechanges.htm&language=en_US&type=5 "Use this service for renewals, to get the coverage changes between two product JSONs. You can use the resulting difference map for display in the UI, or in a generated document.")

 | 

Use this service for renewals, to get the coverage changes between two product JSONs.

 |
| 

[getCoverages](https://help.salesforce.com/s/articleView?id=ind.insurance_insproductjsonservice__getcoverages.htm&language=en_US&type=5 "Use this service to get one or more coverages from a Product JSON using product codes.")

 | 

Gets the coverages from a specified product JSON.

 |
| 

[trimOffAttributeCategory](https://help.salesforce.com/s/articleView?id=ind.insurance_insproductjsonservice__trimoffattributecategory.htm&language=en_US&type=5 "Use this service to get a product JSON that does not include attribute categories, but does include attribute selected values, attribute rules, and attribute value rules.")

 | 

Makes the product JSON smaller by removing the attribute categories. Leaves attribute values in place.

 |
| 

[updateUserValues](https://help.salesforce.com/s/articleView?id=ind.insurance_insproductjsonservice__updateuservalues.htm&language=en_US&type=5 "Use this service to update the userValues of specified attributes in a product JSON, based on changes a user has made. You can also use this service to update where the JSON node is in the hierarchy.")

 | 

Use this service to update the `userValues` of specified attributes in a product JSON, based on changes a user has made.

 |
| 

**InsProductReportService**

 |
| 

[getReportData](https://help.salesforce.com/s/articleView?id=ind.insurance_insproductreportservice__getreportdata.htm&language=en_US&type=5 "Use this service to retrieve all product fields and attributes for a given set of IDs and field sets, including all child products and their attributes.")

 | 

Retrieves all product fields and attributes for a given set of Ids and field sets.

 |
| 

**InsProductService**

 |
| 

[cloneProduct](https://help.salesforce.com/s/articleView?id=ind.insurance_insproductservice__cloneproduct.htm&language=en_US&type=5 "Use this service to clone a product.")

 | 

Clones a product.

 |
| 

[getEligibleProducts](https://help.salesforce.com/s/articleView?id=ind.insurance_insproductservice__geteligibleproducts.htm&language=en_US&type=5 "Use this service to find and return a list of products that match the criteria you specify.")

 | 

Use this service to find and return a list of products that match the criteria you specify.

 |
| 

[getCoverages](https://help.salesforce.com/s/articleView?id=ind.insurance_insproductservice__getcoverages.htm&language=en_US&type=5 "Use this service to get all the coverages for a product spec.")

 | 

Use this service to get all the coverages for a product spec.

 |
| 

[getRatedGroupProducts](https://help.salesforce.com/s/articleView?id=ind.insurance_insproductservice__getratedgroupproducts.htm&language=en_US&type=5 "This service is used only with small group products that use a census. The service allows the products to be kept with the product service.")

 | 

Used only with group products that use census, which allows the products to be kept with the product service.

 |
| 

[getRatedProducts](https://help.salesforce.com/s/articleView?id=ind.insurance_insproductservice__getratedproducts.htm&language=en_US&type=5 "Use this service to get an array of one or more products, priced using rating procedures attached to those products. This service also includes extra features such as tax and fee calculations, filtering, and performance optimization.")

 | 

Queries for eligibility products, runs through the calculation procedure, and returns a price and coverages.

 |
| 

[repriceProduct](https://help.salesforce.com/s/articleView?id=ind.insurance_insproductservice__repriceproduct.htm&language=en_US&type=5 "Use this service to price one product using the rating procedure attached to that product. This service is usually called when a user selects a product and customizes its coverage.")

 | 

Updates pricing based on changes in user values.

 |
| 

[runRules](https://help.salesforce.com/s/articleView?id=ind.insurance_insproductservice__runrules.htm&language=en_US&type=5 "Use this service to run rules on a product without repricing that product.")

 | 

Runs rules on a product without repricing that product.

 |
| 

**InsProviderNetworkService**

Important

These services are retired from Vlocity Health and Vlocity Insurance Winter '22 release:







 |
| 

[cloneNetwork](https://help.salesforce.com/s/articleView?id=ind.insurance_insprovidernetworkservice__clonenetwork.htm&language=en_US&type=5 "Use this service in an OmniScript to clone a Provider Network.")

 | 

Use this service in an OmniScript to clone a Provider Network.

 |
| 

[getProviders](https://help.salesforce.com/s/articleView?id=ind.insurance_insprovidernetworkservice__getproviders.htm&language=en_US&type=5 "Use this service to get a list of Providers and Provider Networks, based on the contact name, postal code, or profile attributes.")

 | 

Use this service to get a list of Providers and Provider Networks, based on contact name, postal code, or profile attributes.

 |
| 

[getProvidersByArea](https://help.salesforce.com/s/articleView?id=ind.insurance_insprovidernetworkservice__getprovidersbyarea.htm&language=en_US&type=5 "Use this service to get all providers and their networks for a given geographical location. This service returns both individual and organizational providers along with the networks they are a member of, by using state and postalCode as inputs.")

 | 

Use this service to retrieve all providers and their networks for a given geographical location. Both individual and organizational providers are returned along with the networks they are a member of, by using `state` and `postalCode` as inputs.

 |
| 

[getProvidersByNameOrNPI](https://help.salesforce.com/s/articleView?id=ind.insurance_insprovidernetworkservice__getprovidersbynameornpi.htm&language=en_US&type=5 "Use this service to allow users to search for Providers using a search key.")

 | 

This service allows users to search for providers using a search key.

 |
| 

[getProvidersDetail](https://help.salesforce.com/s/articleView?id=ind.insurance_insprovidernetworkservice__getprovidersdetail.htm&language=en_US&type=5 "This service allows you to retrieve Provider information, including group affiliations and locations.")

 | 

This service allows user to retrieve provider information including its group affiliations and locations.

 |
| 

**InsQuoteService**

 |
| 

[addInsuredItem](https://help.salesforce.com/s/articleView?id=ind.insurance_insquoteservice__addinsureditem.htm&language=en_US&type=5 "Use this service to add insured items to quotes.")

 | 

Use this service to add insured items to quotes.

 |
| 

[calculateTaxesAndFees](https://help.salesforce.com/s/articleView?id=ind.insurance_insquoteservice__calculatetaxesandfees.htm&language=en_US&type=5 "Use this service to calculate and save taxes and fees on a target quote.")

 | 

Use this service to calculate and save taxes and fees on a target quote.

 |
| 

[cloneQuote](https://help.salesforce.com/s/articleView?id=ind.insurance_insquoteservice__clonequote.htm&language=en_US&type=5 "Use this service to clone a quote.")

 | 

Use this service to clone a quote.

 |
| 

[createEndorsementQuote](https://help.salesforce.com/s/articleView?id=ind.insurance_insquoteservice_createendorsementquote.htm&language=en_US&type=5 "Use this service to create an endorsement quote with quote line items for single-root and multi-root policies.")

 | 

Creates an endorsement quote with quote line items for single-root and multi-root policies.

 |
| 

[createUpdateQuote](https://help.salesforce.com/s/articleView?id=ind.insurance_insquoteservice__createupdatequote.htm&language=en_US&type=5 "Use this service to create a quote for new business, update an existing quote with new information, or create an endorsement quote. For updates, the quoteId of the quote to be updated must be included in the remote options.")

 | 

Use this service to create a quote for an insurance policy, or update an existing quote with new information.

 |
| 

[createUpdateQuoteFromExternal](https://help.salesforce.com/s/articleView?id=ind.insurance_insquoteservice__createupdatequotefromexternal.htm&language=en_US&type=5 "Creates a quote or updates an existing quote with new information through an inbound API call from an external system.")

 | 

Use this service to create a quote or update an existing quote with new information through an inbound API call from an external system.

 |
| 

[getAccountQuotes](https://help.salesforce.com/s/articleView?id=ind.insurance_insquoteservice__getaccountquotes.htm&language=en_US&type=5 "Use this service to retrieve quote records associated with an accountId.")

 | 

Use this service to retrieve quote records associated with an `accountId`.

 |
| 

[getPlanSpecs](https://help.salesforce.com/s/articleView?id=ind.insurance_insquoteservice__getplanspecs.htm&language=en_US&type=5 "Use this service to get all the quote line items (that is to say, the plan specs) associated with a specific product.")

 | 

Use this service to get all the quote line items (that is to say, the plan specs) associated with a specific product.

 |
| 

[getProductSpecs](https://help.salesforce.com/s/articleView?id=ind.insurance_insquoteservice__getproductspecs.htm&language=en_US&type=5 "Use this service in an OmniScript to get a list of specific product specs used in a quote, at the Quote Line Item level, and which includes product information.")

 | 

Use this service in an OmniScript to get a list of specific product specs used in a quote, at the QuoteLineItem level, and which includes product information.

 |
| 

[getRuleLogs](https://help.salesforce.com/s/articleView?id=ind.insurance_insquoteservice_getrulelogs.htm&language=en_US&type=5 "This service retrieves rule logs for a target quote, sorted by execution date in ascending order.")

 | 

Use this service to retrieve rule logs for a target quote, sorted by execution date in ascending order.

 |
| 

[getQuoteDetail](https://help.salesforce.com/s/articleView?id=ind.insurance_insquoteservice__getquotedetail.htm&language=en_US&type=5 "Use this service to get all of the quote details as JSON.")

 | 

Use this service to get all the quote details in a JSON.

 |
| 

[getQuoteVersions](https://help.salesforce.com/s/articleView?id=ind.insurance_insquoteservice__getquoteversions.htm&language=en_US&type=5 "Use this service to retrieve different versions of a quote based on its Opportunity Id, and then return a list of quotes based on the Quote field set QuoteCompareHeader.")

 | 

Use this service to retrieve different versions of a quote based on its Opportunity Id, and then returns a list of quotes based on the Quote field set **QuoteCompareHeader**.

 |
| 

[invokeProductRules](https://help.salesforce.com/s/articleView?id=ind.insurance_insquoteservice__invokeproductrules.htm&language=en_US&type=5 "Use this service in quote flows to invoke underwriting rules you've added to a product.")

 | 

Use this service in quote flows to invoke underwriting rules you've added to a product.

 |
| 

[invokeRules](https://help.salesforce.com/s/articleView?id=ind.insurance_insquoteservice__invokerules.htm&language=en_US&type=5 "Use this service to Invoke state transition rules associated with a target state transition on a target quote.")

 | 

Use this service to invoke state transition rules associated with a target state transition on a target quote.

 |
| [priceLargeGroupRootItems](https://help.salesforce.com/s/articleView?id=ind.insurance_insquoteservicepricelargegrouprootitems.htm&language=en_US&type=5 "This service calculates the price, and optionally taxes and fees, for a specific root item or all root items for a large group quote.") | Calculates the price, and optionally taxes and fees, for a specific root item or all root items for a large group quote. |
| 

[priceRootItem](https://help.salesforce.com/s/articleView?id=ind.insurance_insquoteservice__pricerootitem.htm&language=en_US&type=5 "Use this service to calculate the price (and optionally, taxes and fees) for a target root item and its children under a Quote.")

 | 

Calculates the price for a target root item and its children in a quote.

 |
| 

[recalculateRollupFormulas](https://help.salesforce.com/s/articleView?id=ind.insurance_insquoteservice__recalculaterollupformulas.htm&language=en_US&type=5 "Use this service to sum the price at the child or grandchild quote line item level and recalculates it to the parent quote line item level.")

 | 

This service sums the price at the child or grandchild quote line item level and recalculates it to the parent quote line item level.

 |
| 

[removeCoverage](https://help.salesforce.com/s/articleView?id=ind.insurance_insquoteservice__removecoverage.htm&language=en_US&type=5 "Use this service in an OmniScript to remove a specified coverage, as per the product code, from the quote. You can use this service on multiple plans.")

 | 

Use this service in an OmniScript to remove a specified coverage, as per the product code, from the quote. Can be used on multiple plans.

 |
| 

[updateQuoteLine](https://help.salesforce.com/s/articleView?id=ind.insurance_insquoteservice__updatequoteline.htm&language=en_US&type=5 "Use this service to update items on the quote.")

 | 

Use this service to update items on the quote.

 |
| 

[updateQuotePlans](https://help.salesforce.com/s/articleView?id=ind.insurance_insquoteservice__updatequoteplans.htm&language=en_US&type=5 "Use this service in an OmniScript to add, update, or upsert (add and update) either coverages or attributes for one or more Group Benefit plans across a quote. This service is designed to process only coverages under root products.")

 | 

Use this service in an OmniScript to add, update, or upsert (add and update) either coverages or attributes for one or more plans across a quote.

 |
| 

**InsScheduledAutomatedTransitionService**

 |
| 

[scheduleAutomatedTransition](https://help.salesforce.com/s/articleView?id=ind.insurance_insscheduledautomatedtransitionservice__scheduleautomatedtransition.htm&language=en_US&type=5 "Use this service to automate the state transition by scheduling an object state transition, from an origin state to a target state (Vlocity States), using hourly, daily, or weekly patterns.")

 | 

Use this service to automate the transition by scheduling an object state transition, from an origin state to a target state (Vlocity States), using hourly, daily, or weekly patterns.

 |
| 

**StateRuleService**

 |
| 

[invokeRules](https://help.salesforce.com/s/articleView?id=ind.insurance_stateruleservice__invokerules.htm&language=en_US&type=5 "Use this service to invoke state transition rules associated with a target state transition on a target object. If the rules satisfy the transition criteria, this service executes actions associated with the transition, optionally logs the results of the rule executions, and transitions the target object to the new state.")

 | 

Invokes state transition rules associated with a target state transition on a target object.

 |
| 

[getRuleLogs](https://help.salesforce.com/s/articleView?id=ind.insurance_stateruleservice__getrulelogs.htm&language=en_US&type=5 "Use this service to retrieve rule logs for a target object, sorted by execution date in ascending order.")

 | 

Retrieves rule logs for a target object, sorted by execution date in ascending order.

 |
| 

[getTransitionStates](https://help.salesforce.com/s/articleView?id=ind.insurance_stateruleservice__gettransitionstates.htm&language=en_US&type=5 "Use this service to get default transition states, the To state of each from state transition, the current state, and the last default state for the target object.")

 | 

Gets default transition states, the **To** state of each from state transition, the current state, and the last default state for the target object.

 |
| 

**InsTrailingDocumentService**

 |
| 

[uploadContentDocuments](https://help.salesforce.com/s/articleView?id=ind.insurance_instrailingdocumentservice__uploadcontentdocuments.htm&language=en_US&type=5 "Add this service as remote properties within File and Image inputs to upload documents that satisfy requirements set up as placeholders for specific objects.")

 | 

Add this service as remote properties within File and Image inputs to upload documents that satisfy requirements set up as placeholders for specific objects.

 |
| 

**InsurancePolicyTransactionService**

 |
| 

[reverseTransaction](https://help.salesforce.com/s/articleView?id=ind.insurance_insurancepolicytransactionservice_reversetransaction.htm&language=en_US&type=5 "Use this service to reverse an insurance policy transaction.")

 | 

Reverses an insurance policy transaction

 |
| 

**InsVlocityActionService**

 |
| 

[assignRecordToQueue](https://help.salesforce.com/s/articleView?id=ind.insurance_insvlocityactionservice_assignrecordtoqueue.htm&language=en_US&type=5 "Use this service to assign a record to a specified Salesforce queue.")

 | 

Use this service to assign a record to the specified Salesforce queue.

 |
| 

[notifyApplicant](https://help.salesforce.com/s/articleView?id=ind.insurance_insvlocityactionservice_notifyapplicant.htm&language=en_US&type=5 "Use this service to send an email notification to applicants.")

 | 

Use this service to send an email notification to applicants. This service is used in Vlocity State Model workflows when the Vlocity Actions are configured.

 |

[](https://help.salesforce.com/s?language=en_US)

## Group Benefits Standard Service Listing by Class

These services apply to group benefits in the Salesforce data model.

| 
Classes/Methods

 | 

Description

 |
| --- | --- |
| 

**InsCensusServiceStd**

 |
| 

[addMembers](https://help.salesforce.com/s/articleView?id=ind.insurance_inscensusservicestd__addmembers.htm&language=en_US&type=5 "Use this service to add group census members to a group census using an input JSON.")

 | 

Use this service to add group census members to a group census using an input JSON.

 |
| 

[addPlanSelections](https://help.salesforce.com/s/articleView?id=ind.insurance_inscensusservicestd__addplanselections.htm&language=en_US&type=5 "Use this service to create GroupCensusMemberPlan records for existing GroupCensusMember records. It uses the ContractGroupPlans specified in the input JSON for adding plans to each GroupCensusMember. The service also accepts optional coverages per member such that primary members and dependents can be enrolled into different coverages under the same plan.")

 | 

Use this service to create `GroupCensusMemberPlan` records for existing `GroupCensusMember` records.

 |
| 

[createContacts](https://help.salesforce.com/s/articleView?id=ind.insurance_inscensusservicestd__createcontacts.htm&language=en_US&type=5 "Use this service to create Contacts for census members.")

 | 

Use this service to create Contacts for census members.

 |
| 

[createUpdateAccounts](https://help.salesforce.com/s/articleView?id=ind.insurance_inscensusservicestd__createaccounts.htm&language=en_US&type=5 "Use this service to create Person Accounts for the members in the given census. It also updates the existing person accounts using the duplicateKeys parameter.")

 | 

Use this service to create Person Accounts for the members in the given census. It also updates the existing person accounts using the `duplicateKeys` parameter.

 |
| [deleteAllMembers](https://help.salesforce.com/s/articleView?id=ind.insurance_inscensusservicestddeleteallmembers.htm&language=en_US&type=5 "Use this service to delete all group census members of the group census passed as input into the service. This service supports small and medium groups with a maximum of 1,000 members (including primary members and dependents). The maximum number of records an org can have in the Group Census Member entity is 150,000.") | Deletes all group census members of the group census passed as input into the service. |
| 

[deleteMembers](https://help.salesforce.com/s/articleView?id=ind.insurance_inscensusservicestd__deletemembers.htm&language=en_US&type=5 "Use this service to delete the group census members.")

 | 

Use this service to delete the group census members.

 |
| 

[deleteMembersWithPlans](https://help.salesforce.com/s/articleView?id=ind.insurance_inscensusservicestd__deletememberswithplans.htm&language=en_US&type=5 "Use this service to delete the group census members and the associated plans.")

 | 

Use this service to delete the group census members and the associated plans.

 |
| [findAccounts](https://help.salesforce.com/s/articleView?id=ind.insurance_inscensusservicestdfindaccounts.htm&language=en_US&type=5 "Search for existing person accounts by first name, last name, and email, or by a search key and group account.") | Searches for existing person accounts by first name, last name, and email, or by a search key and group account. |
| [findContacts](https://help.salesforce.com/s/articleView?id=ind.insurance_inscensusservicestdfindcontacts.htm&language=en_US&type=5 "Search for existing contacts by first name, last name, and email, or by a search key and group account.") | Searches for existing contacts by first name, last name, and email, or by a search key and group account. |
| 

[getFields](https://help.salesforce.com/s/articleView?id=ind.insurance_inscensusservicestd__getfields.htm&language=en_US&type=5 "Use this service to retrieve field definitions and field API names for group census members and group census member plans.")

 | 

Use this service to retrieve field definitions and field API names for group census members and group census member plans.

 |
| 

[getMembers](https://help.salesforce.com/s/articleView?id=ind.insurance_inscensusservicestd__getmembers.htm&language=en_US&type=5 "Use this service to retrieve the members of a census from the GroupCensusMember. It also retrieves the headers based on the fieldsetName.")

 | 

Use this service to retrieve the members of a census from the `GroupCensusMember`. It also retrieves the headers based on the `fieldsetName`.

 |
| 

[getMembersWithPlans](https://help.salesforce.com/s/articleView?id=ind.insurance_inscensusservicestd__getmemberswithplans.htm&language=en_US&type=5 "Use this service to retrieve the list of census members for a given censusId. Corresponding to these census members, the service retrieves the ContractGroupPlanIds from GroupCensusMemberPlan. The service also retrieves headers based on the fieldsetName and planFieldsetName.")

 | 

Use this service to retrieve the list of census members for a given `censusId`.

 |
| 

[setCensusRatingFacts](https://help.salesforce.com/s/articleView?id=ind.insurance_inscensusservicestd__setcensusratingfacts.htm&language=en_US&type=5 "Use this service to set AttributeSelectedValues on the GroupCensus record based on the rating fact passed to the service.")

 | 

Use this service to set `AttributeSelectedValues` on the `GroupCensus` record based on the rating fact passed to the service.

 |
| 

[setMemberRatingFacts](https://help.salesforce.com/s/articleView?id=ind.insurance_inscensusservicestd__setmemberratingfacts.htm&language=en_US&type=5 "Use this service to set AttributeSelectedValues on the GroupCensusMember records based on the rating fact passed to the service.")

 | 

Use this service to set `AttributeSelectedValues` on the `GroupCensusMember` records based on the rating fact passed to the service.

 |
| 

[updateMembers](https://help.salesforce.com/s/articleView?id=ind.insurance_inscensusservicestd__updatemembers.htm&language=en_US&type=5 "Use this service to update the values of existing members in a census.")

 | 

Use this service to update the values of existing members in a census.

 |
| 

[updateMembersWithPlans](https://help.salesforce.com/s/articleView?id=ind.insurance_inscensusservicestd__updatememberswithplans.htm&language=en_US&type=5 "Use this service to populate a group census with primary members, their dependents, and their pre-enrolled plan. This service updates existing GroupCensusMember by memberKey and creates GroupCensusMemberPlan records for existing GroupCensusMember records. It uses the ContractGroupPlans specified in the input JSON to update plans for each GroupCensusMember.")

 | 

Use this service to populate a group census with primary members, their dependents, and their pre-enrolled plan.

 |
| 

**InsContractServiceStd**

 |
| 

[createUpdateContract](https://help.salesforce.com/s/articleView?id=ind.insurance_inscontractservicestd__createupdatecontract.htm&language=en_US&type=5 "Use this service to create or update a contract for the given quote. ​")

 | 

Use this service to create or update a contract for the given quote. ​

 |
| 

**InsEnrollmentServiceStd**

 |
| [enrollFamily](https://help.salesforce.com/s/articleView?id=ind.insurance_insenrollmentservicestd_enrollfamily.htm&language=en_US&type=5 "​Use this service to enroll one family within one root plan that includes a primary member and associated dependents with coverages.") | Use this service to enroll one family within one root plan that includes a primary member and associated dependents with coverages. |
| 

[enrollMembers](https://help.salesforce.com/s/articleView?id=ind.insurance_insenrollmentservicestd__enrollmembers.htm&language=en_US&type=5 "Use this service to enroll census members into their selected plans.")

 | 

Use this service to enroll census members into their selected plans.

 |
| [enrollMembersAsync](https://help.salesforce.com/s/articleView?id=ind.insurance_insenrollmentservicestdenrollmembersasync.htm&language=en_US&type=5 "Use this service to enroll large groups of members.") | Enrolls large groups of members. |
| [enrollNewHires](https://help.salesforce.com/s/articleView?id=ind.insurance_insenrollmentservicestdenrollnewhires.htm&language=en_US&type=5 "Enroll new census members into their selected plans in the middle of a contract term.") | Enrolls new census members into their selected plans in the middle of a contract term. |
| 

[enrollPlans](https://help.salesforce.com/s/articleView?id=ind.insurance_insenrollmentservicestd__enrollplans.htm&language=en_US&type=5 "Use this service to create insurance policy (InsurancePolicy) records for member's selected medical, dental, vision, and other plans.")

 | 

Use this service to create insurance policy (`InsurancePolicy`) records for member's selected medical, dental, vision, and other plans.

 |
| 

[getMemberEnrollments](https://help.salesforce.com/s/articleView?id=ind.insurance_insenrollmentservicegetmemberenrollmentsstd_632876.htm&language=en_US&type=5 "Use this service to retrieve current enrollments for a member. This service takes one or more census member Ids and returns enrolled plans for the member and associated dependents.")

 | 

Use this service to retrieve current enrollments for a member. This service takes one or more census member Ids and returns enrolled plans for the member and associated dependents.

 |
| [getPolicyDetails](https://help.salesforce.com/s/articleView?id=ind.insurance_insenrollmentservicestdgetpolicydetails.htm&language=en_US&type=5 "Retrieve Insurance Policy records for Primary Group Census Members.") | Retrieves Insurance Policy records for Primary Group Census Members. |
| [getRatedGroupProducts](https://help.salesforce.com/s/articleView?id=ind.insurance_insenrollmentservicestd_getratedgroupproducts.htm&language=en_US&type=5 "Use this service to calculate price to opt for a root plan with coverages for a family. The service also provides employee and employer contributions for a policy before enrollment, and supports proration for new hires.") | Use this service to calculate price to opt for a root plan with coverages for a family. The service also provides employee and employer contributions for a policy before enrollment, and supports proration for new hires. |

-   **[ActionListService Methods](https://help.salesforce.com/s/articleView?id=ind.insurance_actionlistservice_methods.htm&language=en_US&type=5)**  
    This is the available ActionListService method.
-   **[HealthFeeScheduleDataService Methods](https://help.salesforce.com/s/articleView?id=ind.insurance_healthfeescheduledataservice_methods.htm&language=en_US&type=5)**  
    These are the available HealthFeeScheduleDataService methods.
-   **[InsAsyncBulkService Methods](https://help.salesforce.com/s/articleView?id=ind.insurance_insasyncbulkservice_methods.htm&language=en_US&type=5)**  
    These are the available InsAsyncBulkService methods.
-   **[InsCensusService Methods](https://help.salesforce.com/s/articleView?id=ind.insurance_inscensusservice_methods.htm&language=en_US&type=5)**  
    These are the available InsCensusService methods.
-   **[InsCensusServiceStd Methods](https://help.salesforce.com/s/articleView?id=ind.insurance_inscensusservicestd_methods.htm&language=en_US&type=5)**  
    These are the available InsCensusServiceStd methods.
-   **[InsClaimCoverageService Methods](https://help.salesforce.com/s/articleView?id=ind.insurance_insclaimcoverageservice_methods.htm&language=en_US&type=5)**  
    Create coverages, update coverages, and run state transition rules when creating coverages with the help of the claim coverage service methods.
-   **[InsClaimItemService Methods](https://help.salesforce.com/s/articleView?id=ind.insurance_insclaimitemservice_methods.htm&language=en_US&type=5)**  
    Manage claim line items, calculate coverages, process and cancel payments, and gather information about parties on a claim with the help of the claim item service methods. If you use a payment authorization workflow, use a service method to verify a team member's authority to pay or approve a financial amount.
-   **[InsClaimRecoveryService Methods](https://help.salesforce.com/s/articleView?id=ind.insurance_insclaimrecoveryservice_methods.htm&language=en_US&type=5)**  
    Get a list of claim recoveries and update the records that represent the recovery of funds for a claim with the help of the claim recovery service methods.
-   **[InsClaimService Methods](https://help.salesforce.com/s/articleView?id=ind.insurance_insclaimservice_methods.htm&language=en_US&type=5)**  
    Create and update claims, verify coverages, recover funds on claims, and run underwriting and state transition rules with the help of the claim service methods.
-   **[InsCommissionService Methods](https://help.salesforce.com/s/articleView?id=ind.insurance_inscommissionservice_methods.htm&language=en_US&type=5)**  
    These are the available InsCommissionService methods.
-   **[InsContractService Methods](https://help.salesforce.com/s/articleView?id=ind.insurance_inscontractservice_methods.htm&language=en_US&type=5)**  
    These are the available InsContractService methods.
-   **[InsContractServiceStd Methods](https://help.salesforce.com/s/articleView?id=ind.insurance_inscontractservicestd_methods.htm&language=en_US&type=5)**  
    These are the available InsContractServiceStd methods.
-   **[InsEnrollmentService Methods](https://help.salesforce.com/s/articleView?id=ind.insurance_insenrollmentservice_methods.htm&language=en_US&type=5)**  
    These are the available InsEnrollmentService methods.
-   **[InsEnrollmentServiceStd Methods](https://help.salesforce.com/s/articleView?id=ind.insurance_insenrollmentservicestd_methods.htm&language=en_US&type=5)**  
    These are the available InsEnrollmentServiceStd methods.
-   **[InsFormularyService Methods](https://help.salesforce.com/s/articleView?id=ind.insurance_insformularyservice_methods.htm&language=en_US&type=5)**  
    These are the available InsFormularyService methods.
-   **[InsGroupClassService Methods](https://help.salesforce.com/s/articleView?id=ind.insurance_insgroupclassservice_methods.htm&language=en_US&type=5)**  
    These the available InsGroupClassService methods.
-   **[InsPolicyBillingService Methods](https://help.salesforce.com/s/articleView?id=ind.insurance_inspolicybillingservice_methods.htm&language=en_US&type=5)**  
    These are the available InsPolicyBillingService methods.
-   **[InsPolicyRevenueScheduleService Methods](https://help.salesforce.com/s/articleView?id=ind.insurance_inspolicyrevenuescheduleservice_methods.htm&language=en_US&type=5)**  
    These are the available InsPolicyRevenueScheduleService methods.
-   **[InsPolicyService Methods](https://help.salesforce.com/s/articleView?id=ind.insurance_inspolicyservice_methods.htm&language=en_US&type=5)**  
    These are the available InsPolicyService methods.
-   **[InsPolicyTermsService Methods](https://help.salesforce.com/s/articleView?id=ind.insurance_inspolicytermsservice_methods.htm&language=en_US&type=5)**  
    Track the financial status of policy terms for claims with the help of the policy term service methods.
-   **[InsProductAsyncRatingService Methods](https://help.salesforce.com/s/articleView?id=ind.insurance_insproductasyncratingservice_methods.htm&language=en_US&type=5)**  
    These are the available InsProductAsyncRatingService methods.
-   **[InsProductJSONService Methods](https://help.salesforce.com/s/articleView?id=ind.insurance_insproductjsonservice_methods.htm&language=en_US&type=5)**  
    These are the available InsProductJSONService methods.
-   **[InsProductReportService Methods](https://help.salesforce.com/s/articleView?id=ind.insurance_insproductreportservice_methods.htm&language=en_US&type=5)**  
    These are the available InsProductReportService methods.
-   **[InsProductService Methods](https://help.salesforce.com/s/articleView?id=ind.insurance_insproductservice_methods.htm&language=en_US&type=5)**  
    These are the InsProductService methods.
-   **[InsProviderNetworkService Methods](https://help.salesforce.com/s/articleView?id=ind.insurance_insprovidernetworkservice_methods.htm&language=en_US&type=5)**  
    These are the available InsProviderNetworkService methods.
-   **[InsQuoteService Methods](https://help.salesforce.com/s/articleView?id=ind.insurance_insquoteservice_methods.htm&language=en_US&type=5)**  
    These are the available InsQuoteService methods.
-   **[InsScheduledAutomatedTransitionService Methods](https://help.salesforce.com/s/articleView?id=ind.insurance_insscheduledautomatedtransitionservice_methods.htm&language=en_US&type=5)**  
    These are the available InsScheduledAutomatedTransitionService methods.
-   **[StateRuleService Methods](https://help.salesforce.com/s/articleView?id=ind.insurance_stateruleservice_methods.htm&language=en_US&type=5)**  
    These are the available StateRuleService methods.
-   **[InsTrailingDocumentService:uploadContentDocuments](https://help.salesforce.com/s/articleView?id=ind.insurance_instrailingdocumentservice__uploadcontentdocuments.htm&language=en_US&type=5)**  
    Add this service as remote properties within File and Image inputs to upload documents that satisfy requirements set up as placeholders for specific objects.
-   **[InsurancePolicyTransactionService Methods](https://help.salesforce.com/s/articleView?id=ind.insurance_insurancepolicytransactionservice_methods.htm&language=en_US&type=5)**  
    These are the available InsurancePolicyTransactionService methods.
-   **[InsVlocityActionService](https://help.salesforce.com/s/articleView?id=ind.insurance_insvlocityactionservice.htm&language=en_US&type=5)**  
    These are the available InsVlocityActionService methods.

.

Did this article solve your issue?

Let us know so we can improve!

YesNo