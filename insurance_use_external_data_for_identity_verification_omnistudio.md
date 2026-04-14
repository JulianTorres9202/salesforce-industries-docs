---
title: "Use External Data for Identity Verification"
source: "https://help.salesforce.com/s/articleView?id=ind.insurance_use_external_data_for_identity_verification_omnistudio.htm&language=en_US&type=5"
scraped: "2026-04-14"
filter: "ind.insurance_"
---# Use External Data for Identity Verification

Use External Data for Identity Verification[](https://help.salesforce.com/s?language=en_US)

You are here:

1.  [Salesforce Help](/s/?language=en_US)
2.  [Docs](/s/products?language=en_US)
3.  [Digital Insurance](https://help.salesforce.com/s/articleView?id=ind.insurance_admin_standard.htm&language=en_US&type=5)

# Use External Data for Identity Verification

If the data required to verify a caller resides outside of Salesforce, configure the identity verification process to use data from an external source.

When displaying information from external data sources on the identity verification screen, make sure that you don’t show any sensitive or confidential information. Your Apex class must either mask sensitive information or only partially display the information. For example, you may want to show only the last four digits of social security numbers (SSN) or account numbers and mask the rest.

Note

To disconnect from an external data source, remove all authentication information, data source connection details and mappings, as well as any other dependent configuration.

1.  Create an Apex class.
    
    The Apex class implements the identity verification process methods for building verification context, searching for caller records, and getting verification data.
    
2.  Create an Identity Verification Process Definition record.
    
    As you already know, a process definition record links an identity verification process configuration to the identity verification flow.
    
3.  Create an Identity Verification Process Detail record that looks up to the process definition record.
    
    In the process detail record, set the values of the required fields and specify the Apex class that you’ve created. Select External as the data source.
    
    The Apex class overrides any other detail that you specify.
    
    Note
    
    If you’re using the Verify Customer Identity flow template, you can’t use object-based search with an external data source.
    
4.  Create an identity verification flow.
    
5.  Make the flow available to your users.
    

Did this article solve your issue?

Let us know so we can improve!

YesNo