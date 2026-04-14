---
title: "Insurance Direct to Customer Quoting"
source: "https://help.salesforce.com/s/articleView?id=ind.insurance_vlocity_insurance_direct_to_customer_quoting_613241.htm&language=en_US&type=5"
scraped: "2026-04-14"
filter: "ind.insurance_"
---# Insurance Direct to Customer Quoting

Insurance Direct to Customer Quoting[](https://help.salesforce.com/s?language=en_US)

You are here:

1.  [Salesforce Help](/s/?language=en_US)
2.  [Docs](/s/products?language=en_US)
3.  [Digital Insurance](https://help.salesforce.com/s/articleView?id=ind.insurance_admin_standard.htm&language=en_US&type=5)

# Insurance Direct to Customer Quoting

Empower guest users and customers to create their own quotes whenever they want with Direct to Customer Quoting. Give your independent customers (and potential customers) the freedom to explore options on their own, and free up your agents and CSRs to help even more customers.

[](https://help.salesforce.com/s?language=en_US)

Simply put, Direct to Customer Quoting cuts out the middle man. Guest users and authenticated customers can create and update their own quotes on your Digital Experience Site, and explore options at their own pace from the comfort of their own homes.

[](https://help.salesforce.com/s?language=en_US)Note

This feature is only available for users that have the Customer Community or Customer Community Plus licenses. Learn more about user licenses [here](https://help.salesforce.com/s/articleView?id=platform.users_understanding_license_types.htm&language=en_US&type=5).

[](https://help.salesforce.com/s?language=en_US)

There are two types of Direct to Customer Quoting: Guest User Quoting and Customer Quoting.

[](https://help.salesforce.com/s?language=en_US)

Let's dig a little deeper into both types.

[](https://help.salesforce.com/s?language=en_US)

## Guest User Quoting

A guest user is an unauthenticated user of your Experience Site. You haven’t granted them login credentials and they don’t have an affiliation with your organization (yet). Guest users can create and update their own quotes, and even issue policies based on those quotes. However, we encrypt the `quoteId` and `opportunityId` for guest users, and they can’t see these Ids.

Here's an example of Guest User Quoting:

_Riley wants to see if switching auto insurance providers could save her money. Riley creates a quote and compares the coverage and price offered in the quote to her current policy._

[](https://help.salesforce.com/s?language=en_US)

## Customer Quoting

A customer is someone (like a policyholder) that you've granted credentials to. You authenticated these users as customers for your Experience Site. After they're logged in, customers can:

-   Create quotes for new products or coverages
-   Revise existing quotes
-   Create endorsement quotes for existing policies

Here's an example of Customer Quoting:

_Beth and Jerry want to know how much it would cost to add their daughter as a driver on their policy. They log into their Experience Site and create a quote to see how this change would affect the price of their policy._

You can assign the Insurance Self Quoting permission set to a customer to grant them access to self quoting capabilities.

[](https://help.salesforce.com/s?language=en_US)

## Insurance Self Quoting Permission Set

The Insurance Self Quoting permission set is a blank permission set. `InsQuote` services check to see if the user has the Insurance Self Quoting permission set. If the user has the Insurance Self Quoting permission set, the service runs. If the Insurance Self Quoting permission set isn’t tied to the user and the user tries to run an OmniScript, Integration Procedure, or UI function that uses this service, the service doesn't run and the guest user sees an error message.

Important The InsuranceSelfQuoting permission set is not accessible within a Permission Set Group.

[](https://help.salesforce.com/s?language=en_US)

## Services

Quoting requires access to the Quote and Opportunity objects, but by default Customer Experience Site users don't have access to these objects. You can provide users with limited access to the Quote and Opportunity objects through services. These services use encrypted IDs for customers and guest users for added security.

We enhanced these services to support Direct to Customer quoting:

-   [InsQuoteService:createUpdateQuote](https://help.salesforce.com/s/articleView?id=ind.insurance_insquoteservice__createupdatequote.htm&language=en_US&type=5 "Use this service to create a quote for new business, update an existing quote with new information, or create an endorsement quote. For updates, the quoteId of the quote to be updated must be included in the remote options.")
-   [InsQuoteService:getAccountQuotes](https://help.salesforce.com/s/articleView?id=ind.insurance_insquoteservice__getaccountquotes.htm&language=en_US&type=5 "Use this service to retrieve quote records associated with an accountId.")
-   [InsQuoteService:getQuoteDetail](https://help.salesforce.com/s/articleView?id=ind.insurance_insquoteservice__getquotedetail.htm&language=en_US&type=5 "Use this service to get all of the quote details as JSON.")
-   [InsQuoteService:invokeProductRules](https://help.salesforce.com/s/articleView?id=ind.insurance_insquoteservice__invokeproductrules.htm&language=en_US&type=5 "Use this service in quote flows to invoke underwriting rules you've added to a product.")
-   [InsQuoteService:invokeRules](https://help.salesforce.com/s/articleView?id=ind.insurance_insquoteservice__invokerules.htm&language=en_US&type=5 "Use this service to Invoke state transition rules associated with a target state transition on a target quote.")

Note If you want services to calculate taxes and fees, you must add read permission for the PriceListEntry\_\_c object to the Customer Community user permission set.

[](https://help.salesforce.com/s?language=en_US)

## Additional Access

You can provide additional access to the customer quoting capabilities with these permission sets:

-   Insurance Create/Update Census Data Permission Set
    
-   Insurance View Census Data Permission Set
    

Did this article solve your issue?

Let us know so we can improve!

YesNo