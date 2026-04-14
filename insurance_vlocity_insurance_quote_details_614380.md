---
title: "Insurance Quote Details"
source: "https://help.salesforce.com/s/articleView?id=ind.insurance_vlocity_insurance_quote_details_614380.htm&language=en_US&type=5"
scraped: "2026-04-14"
filter: "ind.insurance_"
---# Insurance Quote Details

Insurance Quote Details[](https://help.salesforce.com/s?language=en_US)

You are here:

1.  [Salesforce Help](/s/?language=en_US)
2.  [Docs](/s/products?language=en_US)
3.  [Digital Insurance](https://help.salesforce.com/s/articleView?id=ind.insurance_admin_standard.htm&language=en_US&type=5)

# Insurance Quote Details

The header information for a quote is populated by the InsQuoteService:createUpdateQuote service. You can see it in the Quote object's Details tab.

[](https://help.salesforce.com/s?language=en_US)The Quote Details field set is used by the Vlocity Insurance services that pull data, such as [InsQuoteService:getQuoteDetails](https://help.salesforce.com/s/articleView?id=ind.insurance_insquoteservice__getquotedetail.htm&language=en_US&type=5 "Use this service to get all of the quote details as JSON."). You can extend this field set with custom fields, and the services pull them along with the standard field set data. You don't have to modify the services.

[](https://help.salesforce.com/s?language=en_US)These are the fields that Vlocity does important stuff with:

[](https://help.salesforce.com/s?language=en_US)

-   Quote Name
    
-   Quote Number
    
-   Term
    
    The length of the policy.
    
-   Standard Premium
    
    The premium as rated by the Vlocity rating engine. This might not be for the same term that this quote is written for.
    
-   Total Premium for Term
    
    The total premium for the term the quote is written for.
    
-   Monthly Premium
    
    The total premium for the quote's term divided into monthly increments.
    
-   Effective Date
    
    The date the quoted policy would go into effect. Used to calculate premiums.
    
-   End Date
    
    The date the quoted policy ends. Set this for custom terms only.
    
-   Total Tax Amount
    
-   Total Fee Amount
    
-   Total Amount
    
    Total Price + Total Taxes + Total Fees
    
-   Total Adjustment Amount
    
    The amount adjusted by an underwriter, if applicable.
    
-   Total Price
    
    The total price of the policy, including total term premium and total (underwriting) adjustments.
    
    Total Amount + Total Adjustment Amount
    
-   Total Sum Insured
    
    The total amount of insurance this quote provides for the insurance customer.
    
    Sums the total sum insured of all quote line items to get this value.
    
-   Calculated Price Data
    
    JSON output of the rating for single-root, single instance products.
    
    We populate calculated price data in each root line item for multi-root use case. Multi-root products and multi-product (like multi-auto) populate these JSONs on the quote line items.
    
-   Census
    
    CensusId used by this quote. Set this for any group insurance quote.
    
-   Rate Type
    
    Age or Composite are the most common values used by Vlocity Health, and are honored by Vlocity. This value gets used downstream when a contract gets created for a group health plan. You can extend this field to use other values if needed.
    
-   Primary Root Item
    
    Used to designate a primary root item in multi-root quotes.
    
-   Primary Quoted Product
    
    A formula field that's calculated and populated based on the data in the Primary Root Item field.
    
    For single root cases, we populate this field with the PrimaryRootItemId value.
    

Did this article solve your issue?

Let us know so we can improve!

YesNo