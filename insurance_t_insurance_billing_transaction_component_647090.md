---
title: "Insurance Billing Transaction Component"
source: "https://help.salesforce.com/s/articleView?id=ind.insurance_t_insurance_billing_transaction_component_647090.htm&language=en_US&type=5"
scraped: "2026-04-14"
filter: "ind.insurance_"
---# Insurance Billing Transaction Component

Insurance Billing Transaction Component[](https://help.salesforce.com/s?language=en_US)

You are here:

1.  [Salesforce Help](/s/?language=en_US)
2.  [Docs](/s/products?language=en_US)
3.  [Digital Insurance](https://help.salesforce.com/s/articleView?id=ind.insurance_admin_standard.htm&language=en_US&type=5)

# Insurance Billing Transaction Component

Your Policyholder site users can view a summary of previous transactions on their account on the Insurance Billing Transactions component.

[](https://help.salesforce.com/s?language=en_US)

This component is composed of a FlexCard and the LWC compiled from the FlexCard:

-   FlexCard: insPolicyBillingTransactions\_nds
    
-   LWC: cfInsPolicyBillingTransactions\_nds
    
-   Label: **Insurance Policy Billing Transactions Newport**
    

[](https://help.salesforce.com/s?language=en_US)

This component is designed for desktop and mobile.

[](https://help.salesforce.com/s?language=en_US)

This component is styled with the Newport Design System.

Here's what the Insurance Billing Transactions component looks like when it's rendered in the Policyholder portal:

[](https://help.salesforce.com/s?language=en_US)

The parts of this component are:

1.  Text label:
    
    **Past Transactions**
    
2.  Child Custom Lightning web component (LWC): **insPolicyTransactions**
    
    The Custom LWC displays information about transactions, including:
    
    -   The transaction post date
        
    -   The transaction description
        
    -   The transaction type
        
    -   The amount of the transaction
        

[](https://help.salesforce.com/s?language=en_US)

## FlexCard Structure

1.  Custom LWC: **insPolicyTransactions**
    

Note

The `listSize` is set to 5 by default, however, you can change this on the Properties tab of the custom LWC.

[](https://help.salesforce.com/s?language=en_US)

## Data Source Called by this Component

The Insurance Billing Transactions component uses the **InsGetPolicyTransactionDetails** Omnistudio Data Mapper to fetch the transaction details and pass them into the custom LWC.

[](https://help.salesforce.com/s?language=en_US)

## Customize this Component

To learn about how to customize this kind of component, see the Digital Experience Site Component Customization Overview

Did this article solve your issue?

Let us know so we can improve!

YesNo