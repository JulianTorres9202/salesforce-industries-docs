---
title: "Group Benefits Flow Overview in the Salesforce Data Model"
source: "https://help.salesforce.com/s/articleView?id=ind.insurance_group_benefits_flow_overview_salesforce.htm&language=en_US&type=5"
scraped: "2026-04-14"
filter: "ind.insurance_"
---# Group Benefits Flow Overview in the Salesforce Data Model

Group Benefits Flow Overview in the Salesforce Data Model[](https://help.salesforce.com/s?language=en_US)

You are here:

1.  [Salesforce Help](/s/?language=en_US)
2.  [Docs](/s/products?language=en_US)
3.  [Digital Insurance](https://help.salesforce.com/s/articleView?id=ind.insurance_admin_standard.htm&language=en_US&type=5)

# Group Benefits Flow Overview in the Salesforce Data Model

A well-designed group benefit gives group members and their dependents cost-effective insurance coverages, and gives employers a way to attract and retain talent. You bring group benefits to life with end-to-end processes that support quoting, contracts, and enrollments. Use Digital Insurance Platform tools to design a flow that smoothly ushers administrators, brokers, group members, and policyholders through each task.

Tip

Trying to figure out which data model to use? The Salesforce data model is the digital insurance platform of choice. It uses harmonized services that integrate seamlessly into the Salesforce Customer 360 platform. If you’re an existing customer who uses the package data model, plan to harmonize your data soon. To benefit from new and enhanced features in the future, you must move to the Salesforce data model.

| 
What

 | 

Why

 | How |
| --- | --- | --- |
| 

1.

 | 

To estimate how much a policy would cost, you use a quote. The building blocks of the quote are:

-   Products offered by the provider.
    
-   Census information supplied by the customer.
    

 | 

Group Benefits solutions are fully customizable, but to get grounded in a typical setup, learn about services commonly used for quoting in the Salesforce data model.

InsProductService:

-   [getRatedProducts](https://help.salesforce.com/s/articleView?id=ind.insurance_insproductservice__getratedproducts.htm&language=en_US&type=5 "Use this service to get an array of one or more products, priced using rating procedures attached to those products. This service also includes extra features such as tax and fee calculations, filtering, and performance optimization.")
    
-   [getRatedGroupProducts](https://help.salesforce.com/s/articleView?id=ind.insurance_insproductservice__getratedgroupproducts.htm&language=en_US&type=5 "This service is used only with small group products that use a census. The service allows the products to be kept with the product service.")
    

InsCensusServiceStd:

-   [setMemberRatingFacts](https://help.salesforce.com/s/articleView?id=ind.insurance_inscensusservicestd__setmemberratingfacts.htm&language=en_US&type=5 "Use this service to set AttributeSelectedValues on the GroupCensusMember records based on the rating fact passed to the service.")
    

InsContractServiceStd:

-   [createUpdateContract](https://help.salesforce.com/s/articleView?id=ind.insurance_inscontractservicestd__createupdatecontract.htm&language=en_US&type=5 "Use this service to create or update a contract for the given quote. ​")
    

InsEnrollmentServiceStd:

-   [enrollPlans](https://help.salesforce.com/s/articleView?id=ind.insurance_insenrollmentservicestd__enrollplans.htm&language=en_US&type=5 "Use this service to create insurance policy (InsurancePolicy) records for member's selected medical, dental, vision, and other plans.")
    

InsQuoteService:

-   [createUpdateQuote](https://help.salesforce.com/s/articleView?id=ind.insurance_insquoteservice__createupdatequote.htm&language=en_US&type=5 "Use this service to create a quote for new business, update an existing quote with new information, or create an endorsement quote. For updates, the quoteId of the quote to be updated must be included in the remote options.")
    
-   [getQuoteDetail](https://help.salesforce.com/s/articleView?id=ind.insurance_insquoteservice__getquotedetail.htm&language=en_US&type=5 "Use this service to get all of the quote details as JSON.")
    

 |
| 

2\. Contract

 | 

Automating contract creation gets you contracts faster with fewer errors.

 | 

Create a customized solution to build a contract directly from a quote.

 |
| 

3.

 | 

Enroll groups of individual members in new or existing plans, and allow members to make benefit changes.

 | 

Tight integration between enrollment and census features lets you:

-   Upload a census.
    
-   Create contact records for the census members.
    
-   Enroll members into plans.
    

Learn about services commonly used for enrollment in the Salesforce data model.

InsCensusServiceStd:

-   [setMemberRatingFacts](https://help.salesforce.com/s/articleView?id=ind.insurance_inscensusservicestd__setmemberratingfacts.htm&language=en_US&type=5 "Use this service to set AttributeSelectedValues on the GroupCensusMember records based on the rating fact passed to the service.")
    
-   [createUpdateAccounts](https://help.salesforce.com/s/articleView?id=ind.insurance_inscensusservicestd__createaccounts.htm&language=en_US&type=5 "Use this service to create Person Accounts for the members in the given census. It also updates the existing person accounts using the duplicateKeys parameter.") or [createContacts](https://help.salesforce.com/s/articleView?id=ind.insurance_inscensusservicestd__createcontacts.htm&language=en_US&type=5 "Use this service to create Contacts for census members.")
    

InsEnrollmentServiceStd:

-   [enrollMembers](https://help.salesforce.com/s/articleView?id=ind.insurance_insenrollmentservicestd__enrollmembers.htm&language=en_US&type=5 "Use this service to enroll census members into their selected plans.")
    

 |

Did this article solve your issue?

Let us know so we can improve!

YesNo