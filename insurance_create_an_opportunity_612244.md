---
title: "Create an Opportunity"
source: "https://help.salesforce.com/s/articleView?id=ind.insurance_create_an_opportunity_612244.htm&language=en_US&type=5"
scraped: "2026-04-14"
filter: "ind.insurance_"
---# Create an Opportunity

Create an Opportunity[](https://help.salesforce.com/s?language=en_US)

You are here:

1.  [Salesforce Help](/s/?language=en_US)
2.  [Docs](/s/products?language=en_US)
3.  [Digital Insurance](https://help.salesforce.com/s/articleView?id=ind.insurance_admin_standard.htm&language=en_US&type=5)

# Create an Opportunity

An opportunity represents a sale or pending deal. New business and some endorsement (mid-term adjustment) quotes are created from opportunities.

Opportunities are an integral part of the quoting process. An Opportunity must exist to create a quote. When an opportunity becomes a quote or policy, information from the opportunity moves forward to the quote or policy record.

Note

[](https://help.salesforce.com/s?language=en_US)An Opportunity is automatically generated when you create an Endorsement (Mid-Term Adjustment) quote. The new Opportunity generated has the same name as the Endorsement quote and the Opportunity type is set to Endorsement.

1.  On the Opportunities tab, click **New**.
2.  Enter the following required information:
    
    -   **Price Book**: You cannot add products to a quote if there is no Price Book selected.
        
    -   **Opportunity Name**: The name of the opportunity you're creating.
        
    -   **Close Date**: The date on which you plan to close the opportunity.
        
    -   **Stage**: The current stage of the opportunity.
        
    
    See [Opportunity Fields](https://help.salesforce.com/s/articleView?id=sf.opp_fields.htm&amp%3Btype=5&language=en_US&type=5) to learn more about the other available fields.
    
3.  Click **Save**.

[](https://help.salesforce.com/s?language=en_US)

Once you have created an Opportunity, you can create a quote associated with that Opportunity.

To learn about quoting, see:

-   [Single Root Quoting](https://help.salesforce.com/s/articleView?id=ind.insurance_single_root_quoting_612298.htm&language=en_US&type=5 "You can configure quotes directly in the Quote object, without any need to go through an OmniScript flow.")
    
-   [Multi-Root Quoting](https://help.salesforce.com/s/articleView?id=ind.insurance_multi_root_quoting_613315.htm&language=en_US&type=5 "Configure, navigate, and reprice complex quotes with multi-level insured item relationships and coverages with Vlocity Insurance multi-root quoting.")
    

Did this article solve your issue?

Let us know so we can improve!

YesNo