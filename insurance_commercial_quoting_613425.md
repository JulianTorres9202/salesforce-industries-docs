---
title: "Commercial Quoting"
source: "https://help.salesforce.com/s/articleView?id=ind.insurance_commercial_quoting_613425.htm&language=en_US&type=5"
scraped: "2026-04-14"
filter: "ind.insurance_"
---# Commercial Quoting

Commercial Quoting[](https://help.salesforce.com/s?language=en_US)

You are here:

1.  [Salesforce Help](/s/?language=en_US)
2.  [Docs](/s/products?language=en_US)
3.  [Digital Insurance](https://help.salesforce.com/s/articleView?id=ind.insurance_admin_standard.htm&language=en_US&type=5)

# Commercial Quoting

Easily configure, reprice, and navigate complex commercial quotes with multi-level insured item relationships and coverages.

Commercial quotes and policies can have complex product structures with multiple levels of insured items. Each insured item can have its own set of coverages and coverage terms. You can add coverages and ratings to parent, child, and grandchild insured items.

Ursa Major is shopping for insurance. They have two locations, one in New York and one in San Francisco. The New York location has two buildings: a warehouse and a customer contact center. Each building must have its own coverage. Additionally, the warehouse has been a target for vandalism in the past, so Ursa Major decides that they want to add the optional vandalism coverage to that building. Similarly, earthquakes are common near the San Francisco location, so they decide to add the optional earthquake coverage to the office building at that location. Now Ursa Major has exactly the coverage they need for all of their buildings, and nothing extra!

[](https://help.salesforce.com/s?language=en_US)

## Insurance Quote Commercial Lightning Web Component

The Insurance Quote Commercial Lightning web component is specially designed to help you build complex quotes. It features a side panel for editing line items. Buttons for common actions display prominently so your users can issue policies, create quote versions, compare quote version histories and add additional products with ease.

[](https://help.salesforce.com/s?language=en_US)Note

Starting in Spring ’25, you can configure and reprice quotes by using the Insurance Commercial Quote LWC in the customer community portal. To use the component, enable the `RemoveEncryptionForCustCmnyUsr` custom setting in Insurance Configuration Setup.

[](https://help.salesforce.com/s?language=en_US)Tip

To make the Issue Policy button available to your users, select the **Show Issue Policy Button** on the Insurance Quote Commercial LWC in the Lightning App Builder. Read [Create and Configure Lightning Experience Record Pages](https://help.salesforce.com/s/articleView?id=platform.lightning_app_builder_customize_lex_pages.htm&language=en_US&type=5) to learn how.

[](https://help.salesforce.com/s?language=en_US)This component supports multi-root quotes. Multi-root quotes consist of a quote that has multiple root products. Users can view root products and associated coverages on the same UI. In products used for commercial quoting, define the **Instance Key Formula** in a way that creates unique instance keys. For example, for a Vehicle product, use a formula that incorporates unique license or part numbers:

`vehicle.vehicleType + " " + vehicle.vehicleLicNum + " " + vehicle.vehicleChassisNum`

A well-formed **Instance Key Formula** ensures that products in a multi-root quote have unique instance key values, and that the attribute rules used for commercial quoting work consistently. Find the **Instance Key Formula** field on the product Details page.

When you compare versions of a quote, the side-by-side view shows details for multiple levels of insured items in single- and multi-root quotes.

For example, compare two versions of a Commercial Product quote with multiple levels of insured items and coverages.

Or compare two versions of a multi-root quote.

Note Multi-root version comparison is not supported for policies.

[](https://help.salesforce.com/s?language=en_US)

## Commercial Quoting Workflow

After you've created and configured a quote, there are several other things you may want to do and be aware of:

Note

To make the Insurance Quote Commercial LWC available for your users, you must add it to the Quote page. Read [Lightning App Builder](https://help.salesforce.com/s/articleView?id=platform.lightning_app_builder_overview.htm&language=en_US&type=5) to learn about adding custom components to your lightning pages.

1.  [Create a New Commercial Quote](https://help.salesforce.com/s/articleView?id=ind.insurance_create_a_new_commercial_quote_613496.htm&language=en_US&type=5 "To estimate how much a commercial policy would cost, you use a quote.")
    
    To estimate how much a commercial policy would cost, you use a quote.
    
2.  [Configure a Commercial Quote](https://help.salesforce.com/s/articleView?id=ind.insurance_configure_a_commercial_quote_613553.htm&language=en_US&type=5 "Once you have created a Commercial quote, you can configure it to provide your customer with exactly the coverage they need.")
    
    Once you have created a commercial quote, you can configure it to provide the coverages needed.
    

-   [Quote Rating](https://help.salesforce.com/s/articleView?id=ind.insurance_quote_rating_612853.htm&language=en_US&type=5 "You can rate quotes as many times as you need to during the quoting process. When you rate a quote, optional coverage validation rules and optional coverage relationship rules run, and a price is created and displayed for the coverage.")
    
    You can rate quotes as many times as you want to during the quoting process.
    
-   [Quote Versioning](https://help.salesforce.com/s/articleView?id=ind.insurance_quote_versioning_612894.htm&language=en_US&type=5 "You can create and compare quote versions from a Quote record.")
    
    You can create and compare quote versions from a Quote record.
    
-   [Quote Record Types](https://help.salesforce.com/s/articleView?id=ind.insurance_quote_record_types_612976.htm&language=en_US&type=5 "The Type field on the Quote Details tab helps you to differentiate between quotes created for new business and endorsement (mid-term adjustment) quotes.")
    
    The Type field on the Quote Details tab helps you to differentiate between quotes created for new business and endorsement (mid-term adjustment) quotes.
    
-   [Issue a Policy from a Commercial Quote](https://help.salesforce.com/s/articleView?id=ind.insurance_issue_a_policy_from_a_commercial_quote__613774.htm&language=en_US&type=5 "You can issue a commercial policy directly from a quote using the Issue Policy button.")
    
    You can issue a policy directly from a commercial quote using the Issue Policy button.
    
-   [Optional Coverage Rules for Quoting](https://help.salesforce.com/s/articleView?id=ind.insurance_optional_coverage_rules_for_quoting_613045.htm&language=en_US&type=5 "When you make changes to insured items, insured parties, and coverages on the Quote UI, optional coverage rules run. Which rules run and what the system does depends on what you've done to the quote.")
    
    When you make changes to insured items, insured parties, and coverages on the Commercial Quote UI, optional coverage rules run. Which rules run depends on what you've done to the quote.
    
-   [Commissions for Quoting](https://help.salesforce.com/s/articleView?id=ind.insurance_commissions_for_quoting_613215.htm&language=en_US&type=5 "You can use a variety of commission calculations that apply to individual agents and products in different time periods. You get to choose which events trigger a calculation, including quotes. As agents do business, services calculate and save commission data to quote objects so you can view and report on them.")
    
    You can use a variety of commission calculations that apply to individual agents and products in different time periods. You get to choose which events trigger a calculation, including quotes. As agents do business, services calculate and save commission data to quote objects so you can view and report on them.
    

[](https://help.salesforce.com/s?language=en_US)

## See Also

-   [Build Insurance Product Models](https://help.salesforce.com/s/articleView?id=ind.insurance_insurance_and_health_product_models_603786.htm&language=en_US&type=5 "An insurance product model is a structured definition of a product that a company sells, then services. A product model acts as a blueprint for an insurance product.")
    
-   [Learn About Rating Procedures](https://help.salesforce.com/s/articleView?id=ind.insurance_rating_procedures.htm&language=en_US&type=5 "Rating procedures are the backbone of insurance pricing. Learn how services, product models, and rating procedures work together to price insurance products.")
    
-   [Insurance Rules](https://help.salesforce.com/s/articleView?id=ind.insurance_insurance_and_health_rules_606729.htm&language=en_US&type=5 "Rules define the way Insurance products behave when those products are quoted, sold, and serviced.")
    

-   **[Create a New Commercial Quote](https://help.salesforce.com/s/articleView?id=ind.insurance_create_a_new_commercial_quote_613496.htm&language=en_US&type=5)**  
    To estimate how much a commercial policy would cost, you use a quote.
-   **[Configure a Commercial Quote](https://help.salesforce.com/s/articleView?id=ind.insurance_configure_a_commercial_quote_613553.htm&language=en_US&type=5)**  
    Once you have created a Commercial quote, you can configure it to provide your customer with exactly the coverage they need.
-   **[Pricing Discount for Multiroot Quotes](https://help.salesforce.com/s/articleView?id=ind.insurance_pricing_discount.htm&language=en_US&type=5)**  
    To calculate discounts and reprice premiums during the issuance and endorsement of multiroot quotes, use the Pricing Discount out-of-the-box solution. Enable the PricingDiscountIntegProcName custom setting to use this solution in the Insurance Commercial Quote Lightning web component.
-   **[Issue a Policy from a Commercial Quote](https://help.salesforce.com/s/articleView?id=ind.insurance_issue_a_policy_from_a_commercial_quote__613774.htm&language=en_US&type=5)**  
    You can issue a commercial policy directly from a quote using the Issue Policy button.

Did this article solve your issue?

Let us know so we can improve!

YesNo