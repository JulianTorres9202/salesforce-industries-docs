---
title: "InsContractService Methods"
source: "https://help.salesforce.com/s/articleView?id=ind.insurance_inscontractservice_methods.htm&language=en_US&type=5"
scraped: "2026-04-14"
filter: "ind.insurance_"
---# InsContractService Methods

InsContractService Methods[](https://help.salesforce.com/s?language=en_US)

You are here:

1.  [Salesforce Help](/s/?language=en_US)
2.  [Docs](/s/products?language=en_US)
3.  [Digital Insurance](https://help.salesforce.com/s/articleView?id=ind.insurance_admin_standard.htm&language=en_US&type=5)

# InsContractService Methods

These are the available InsContractService methods.

-   **[InsContractService:createLargeSizeRenewQuoteInBatch](https://help.salesforce.com/s/articleView?id=ind.insurance_inscontractservice__createlargesizerenewquoteinbatch.htm&language=en_US&type=5)**  
    Use this service to allow for the control of how many Apex jobs to initiate, and the number of batches to run per Apex job, for contracts with a large number of root line items.
-   **[InsContractService:createRenewQuotesInBatch](https://help.salesforce.com/s/articleView?id=ind.insurance_inscontractservice__createrenewquotesinbatch.htm&language=en_US&type=5)**  
    Use this service to allow you to control how many Apex jobs to initiate, and the number of batches to run per Apex job, for a large number of contract renewals.
-   **[InsContractService:createUpdateContract](https://help.salesforce.com/s/articleView?id=ind.insurance_inscontractservice__createupdatecontract.htm&language=en_US&type=5)**  
    Use this service to create or update a contract using the output of the `InsQuoteService:getQuoteDetail` service.
-   **[InsContractService:getContractDetail](https://help.salesforce.com/s/articleView?id=ind.insurance_inscontractservice__getcontractdetail.htm&language=en_US&type=5)**  
    Use this service to return a ProductJSON that you can use with the `InsQuoteService:createUpdateQuote` service to update the Contract JSON with, or to create a renewal quote with replacement products.
-   **[InsContractService:invokeProductRules](https://help.salesforce.com/s/articleView?id=ind.insurance_inscontractservice__invokeproductrules.htm&language=en_US&type=5)**  
    Use this service in contract flows to invoke underwriting rules you've added to a product.

Did this article solve your issue?

Let us know so we can improve!

YesNo