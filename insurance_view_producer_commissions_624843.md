---
title: "View Producer Commissions"
source: "https://help.salesforce.com/s/articleView?id=ind.insurance_view_producer_commissions_624843.htm&language=en_US&type=5"
scraped: "2026-04-14"
filter: "ind.insurance_"
---# View Producer Commissions

View Producer Commissions[](https://help.salesforce.com/s?language=en_US)

You are here:

1.  [Salesforce Help](/s/?language=en_US)
2.  [Docs](/s/products?language=en_US)
3.  [Digital Insurance](https://help.salesforce.com/s/articleView?id=ind.insurance_admin_standard.htm&language=en_US&type=5)

# View Producer Commissions

As commissionable events occur, services calculate commissions and generate Producer Commission records. These show agents how much they’re earning as they issue quotes and close deals, and give insight into the commissions associated with each stage of the customer journey.

On Producer records, click the **Commissions** tab to see Producer Commission records associated with that record. On Quote and Insurance Policy records, click the **Related** tab.

You can also view Producer Commission records directly.

1.  From the App Launcher, find and select **Producer Commissions**.
2.  Click a producer commission **Name** to view it.
    
    You can click **New** to create a producer commission manually, but you typically don't need to since services create them automatically as commissionable events occur.
    
3.  Review these values.
    
    | 
    Name
    
     | 
    
    Unique identifier
    
     |
    | --- | --- |
    | 
    
    Parent Producer Commission
    
     | 
    
    Parent name of producer hierarchy, if applicable
    
     |
    | 
    
    Commission Schedule
    
     | 
    
    The commission schedule used to calculate the commission
    
     |
    | 
    
    Payee Producer
    
     | 
    
    The producer who gets paid the commission
    
     |
    | 
    
    Type
    
     | 
    
    Category of the commission (for example, Commission, Chargeback, or Bonus)
    
     |
    | 
    
    Status
    
     | 
    
    Status of the commission payment (for example, Pending, Paid, or Waived)
    
     |
    | 
    
    Source System
    
     | 
    
    For commissions coming from an external system, the name of the system
    
     |
    | 
    
    Source System Identifier
    
     | 
    
    For commissions coming from an external system, a unique ID from that system
    
     |
    | 
    
    Payment Date
    
     | 
    
    Date commission is paid
    
     |
    | 
    
    Max Commission Amount
    
     | 
    
    Maximum commission amount
    
     |
    | 
    
    Min Commission Amount
    
     | 
    
    Minimum commission amount
    
     |
    | 
    
    Commission Amount
    
     | 
    
    Calculated commission amount
    
     |
    | 
    
    Commissionable Amount
    
     | 
    
    Amount on which commission calculation is based
    
     |
    | 
    
    Insurance Policy
    
     | 
    
    The insurance policy associated with this commission
    
     |
    | 
    
    Insurance Policy Asset
    
     | 
    
    The insured item associated with this commission
    
     |
    | 
    
    Insurance Policy Coverage
    
     | 
    
    The insurance policy coverage associated with this commission
    
     |
    | 
    
    Insurance Policy Transaction
    
     | 
    
    The insurance policy transaction associated with this commission
    
     |
    | 
    
    Processing Producer
    
     | 
    
    The producer who performed the commissionable event
    
     |
    | 
    
    Producer Production Code
    
     | 
    
    The production code for the producer who performed the commissionable event
    
     |
    

Did this article solve your issue?

Let us know so we can improve!

YesNo