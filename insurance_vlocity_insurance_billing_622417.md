---
title: "Insurance Billing"
source: "https://help.salesforce.com/s/articleView?id=ind.insurance_vlocity_insurance_billing_622417.htm&language=en_US&type=5"
scraped: "2026-04-14"
filter: "ind.insurance_"
---# Insurance Billing

Insurance Billing[](https://help.salesforce.com/s?language=en_US)

You are here:

1.  [Salesforce Help](/s/?language=en_US)
2.  [Docs](/s/products?language=en_US)
3.  [Digital Insurance](https://help.salesforce.com/s/articleView?id=ind.insurance_admin_standard.htm&language=en_US&type=5)

# Insurance Billing

Insurance Billing can help you provide your customers, brokers, and agents with a seamless billing, statements, and payments experience.

Vlocity Insurance Billing is a configurable cloud-based billing and payment solution built for the Vlocity Insurance platform. Use Vlocity Insurance Billing to accurately translate premiums, charges, and other financial transactions on a policy into statements and bills for a host of different billing scenarios. You can set up direct policy bills, consolidated account bills, or automatically scheduled payments at an account or individual policy level. With Vlocity Insurance Billing, you can seamlessly integrate billing functions (guided billing setup, statement generation, premium payments, policy modifications, renewals, and cancellations) into the policy lifecycle. Automated grace period and lapse processing help to streamline operations. Customized Vlocity Insurance portals can provide customers, brokers, or carriers a real-time view into their bills, statements, and current policy standing.

[](https://help.salesforce.com/s?language=en_US)

## Vlocity Insurance Billing Benefits

Vlocity Insurance Billing provides you with many benefits, including the ability to:

-   Seamlessly integrate billing, statements, and payments into the customer journey.
    
-   Create customer-centric Billing Accounts.
    
-   Fully integrate with Vlocity Digital Insurance Portals and the Vlocity Contact Center.
    
-   Create guided set-up and payment integrations with Vlocity OmniScript.
    
-   Manage automated grace period and lapsing rules.
    
-   Orchestrate batch processes on the Salesforce platform using code-free Vlocity Integration Procedures and Scheduled Jobs.
    
-   Automatically create the policy payment schedule when you issue a policy.
    
-   Automatically adjust the payment schedule whenever you make a change to the policy that would affect the price of the premium.
    

[](https://help.salesforce.com/s?language=en_US)

## Vlocity Insurance Billing Services

Vlocity Insurance Billing uses Apex services to help execute basic billing functions. You can use these services by adding a Remote Action element to an OmniScript or Integration Procedure. Learn more about using services [here](https://help.salesforce.com/s/articleView?id=ind.insurance_insurance_and_health_insurance_services_catalog.htm&language=en_US&type=5 "Get quote, policy, and claims systems up and running by using an extensive catalog of Digital Insurance Platform services. The services are methods of Apex classes that carry out common actions for insurance companies and health plans. They help you build end-to-end business processes faster by reducing or eliminating the need for custom programming.").

The services used by Vlocity Insurance Billing are:

-   [InsPolicyBillingService:generateBillingAccountStatements](https://help.salesforce.com/s/articleView?id=ind.insurance_inspolicybillingservice__generatebillingaccountstatements.htm&language=en_US&type=5 "Use this service to generate statements for accounts that contain policies with billing accounts that have Due Date = today.")
    
-   [InsPolicyBillingService:generateDirectBillingStatements](https://help.salesforce.com/s/articleView?id=ind.insurance_inspolicybillingservice__generatedirectbillingstatements.htm&language=en_US&type=5 "Use this service to generate statements for accounts containing policies with direct billing whose due date is equal to today's date plus ten (10) days.")
    
-   [InsPolicyService:createPaymentSchedule](https://help.salesforce.com/s/articleView?id=ind.insurance_inspolicyservice__createpaymentschedule.htm&language=en_US&type=5 "The InsPolicyService:createPaymentSchedule service creates a payment schedule (and optionally an initial payment transaction) for the target policy. This applies to Insurance Policy object only. The Policy (Asset) object is not supported.")
    
-   [InsPolicyService:createPolicyVersion](https://help.salesforce.com/s/articleView?id=ind.insurance_inspolicyservice__createpolicyversion.htm&language=en_US&type=5 "Use this service to create a new version of an existing policy, while maintaining the existing policy record as-is.")
    
-   [InsPolicyService:createUpdatePolicy](https://help.salesforce.com/s/articleView?id=ind.insurance_inspolicyservice__createupdatepolicy.htm&language=en_US&type=5 "Use this service to create a new insurance policy or to update an existing policy with new information.")
    
-   [InsPolicyService:getPaymentSchedule](https://help.salesforce.com/s/articleView?id=ind.insurance_inspolicyservice__getpaymentschedule.htm&language=en_US&type=5 "The InsPolicyService:getPaymentSchedule service returns the payment schedule of the InsurancePolicy. The Policy (Asset) object is not supported.")
    
-   [InsPolicyService:modifyPaymentSchedule](https://help.salesforce.com/s/articleView?id=ind.insurance_inspolicyservice__modifypaymentschedule.htm&language=en_US&type=5 "Use this service to modify an existing payment schedule based on a new Premium Frequency.")
    

Did this article solve your issue?

Let us know so we can improve!

YesNo