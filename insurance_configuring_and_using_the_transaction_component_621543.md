---
title: "Configuring and Using the Transaction Component"
source: "https://help.salesforce.com/s/articleView?id=ind.insurance_configuring_and_using_the_transaction_component_621543.htm&language=en_US&type=5"
scraped: "2026-04-14"
filter: "ind.insurance_"
---# Configuring and Using the Transaction Component

Configuring and Using the Transaction Component[](https://help.salesforce.com/s?language=en_US)

You are here:

1.  [Salesforce Help](/s/?language=en_US)
2.  [Docs](/s/products?language=en_US)
3.  [Digital Insurance](https://help.salesforce.com/s/articleView?id=ind.insurance_admin_standard.htm&language=en_US&type=5)

# Configuring and Using the Transaction Component

The Transaction component list is supported for claims and assets (insurance policies). To use it, add the transaction component to the claims and asset detail pages, then associate it with an Integration Procedure.

[](https://help.salesforce.com/s?language=en_US)Here's the workflow:

1.  [Customize Transaction Objects](https://help.salesforce.com/s/articleView?id=ind.insurance_customize_transaction_objects_621560.htm&language=en_US&type=5 "Vlocity provides a Transactions object to support transaction component functionality.")
2.  Set Up a Transaction Component OmniForm
3.  Set Up Transaction Component Post IPs and Integration Procedures
4.  Add the Transaction Component to Pages

[](https://help.salesforce.com/s?language=en_US)

## Set Up a Transaction Component OmniForm

This OmniForm appears when you create a transaction in an asset or a claim.

[](https://help.salesforce.com/s?language=en_US)

1.  Go to OmniScript Designer and create a new OmniScript that you can use as an OmniForm. Enter:
    
    | 
    Field
    
     | 
    
    Value
    
     |
    | --- | --- |
    | 
    
    **Name**
    
     | 
    
    Transaction OmniForm or something similar
    
     |
    | 
    
    **Type**
    
     | 
    
    Claim or Asset
    
     |
    | 
    
    **SubType**
    
     | 
    
    Transaction
    
     |
    
2.  From Groups, drag a Step onto the OmniScript structure and name it Transaction.
3.  Add Inputs to the Step to create the transaction.
4.  From Actions, drag a Submit remote action under the step.

[](https://help.salesforce.com/s?language=en_US)

## Set Up Transaction Component Post IPs and Integration Procedures

Create two Integration Procedures for each object you want to add the transaction component to: a Post-Integration Procedure ("Post IP"), and an Integration Procedure that calls the Post IP.

[](https://help.salesforce.com/s?language=en_US)

1.  Go to OmniStudio Integration Procedures and click New to create a new PostIP integration procedure. Enter:
    
    | 
    Field
    
     | 
    
    Value
    
     |
    | --- | --- |
    | 
    
    **Name**
    
     | 
    
    ClaimPostIP, AssetPostIP, or something similar
    
     |
    | 
    
    **Type**
    
     | 
    
    Claim or Asset
    
     |
    | 
    
    **SubType**
    
     | 
    
    PostTransaction
    
     |
    
2.  Drag a Remote Action onto the Structure. Enter:
    
    | 
    Field
    
     | 
    
    Value
    
     |
    | --- | --- |
    | 
    
    **Element Name**
    
     | 
    
    Descriptive name
    
     |
    | 
    
    **Remote Class**
    
     | 
    
    InsuranceClaimHandler or InsuranceAssetHandler
    
     |
    | 
    
    **Remote Method**
    
     | 
    
    upsertClaimTransaction or upsertAssetTransaction
    
     |
    
3.  Drag an Omnistudio Data Mapper Post Action onto the Structure under the Remote Action.
    
    Note
    
    In this procedure, the Post IP calls a Data Mapper. Your Post IP can call a Data Mapper, an Apex class, or another action of your choice.
    
    1.  Give the action an Element Name.
        
    2.  Click the link beside the Data Mapper Interface field to create a new Data Mapper.
        
    3.  On the Vlocity Data Mapper Interface page, on the Object tab, enter either InsClaimReserveTransaction\_\_c or InsAssetReserveTransaction\_\_c.
        
    4.  In the Fields tab, enter information for the fields you will use on the transaction component.
        
    
    This is your Post IP. Now you can create an Integration Procedure that calls this Post IP.
    
4.  [](https://help.salesforce.com/s?language=en_US)
    
    Go to Vlocity Integration Procedures and click New. Enter:
    
    | 
    Field
    
     | 
    
    Value
    
     |
    | --- | --- |
    | 
    
    **Name**
    
     | 
    
    TransactionForm or something similar
    
     |
    | 
    
    **Type**
    
     | 
    
    Claim or Asset
    
     |
    | 
    
    **SubType**
    
     | 
    
    Transaction
    
     |
    
5.  [](https://help.salesforce.com/s?language=en_US)
    
    Drag an OmniForm action onto the Structure. Enter:
    
    | 
    Field
    
     | 
    
    Value
    
     |
    | --- | --- |
    | 
    
    **Element Name**
    
     | 
    
    Transaction or something similar
    
     |
    | 
    
    **Type**
    
     | 
    
    Claim or Asset
    
     |
    | 
    
    **SubType**
    
     | 
    
    Transaction
    
     |
    | 
    
    **Post IP**
    
     | 
    
    The name of the Post IP you just created
    
     |
    
    You reference this Integration Procedure (not the Post IP) when you add a transaction component to a page.
    

[](https://help.salesforce.com/s?language=en_US)

## Add the Transaction Component to Pages

When you add the transaction component to a page, you also specify the Integration Procedure for the object.

[](https://help.salesforce.com/s?language=en_US)

1.  Go to the asset or claim detail view, go to the gear menu, and select **Edit Page**.
    
2.  Drag and drop the **Vlocity Transactions List Component** onto the detail page.
    
3.  On the right pane, enter the name of the Integration Procedure for this type of object.
    

-   **[Customize Transaction Objects](https://help.salesforce.com/s/articleView?id=ind.insurance_customize_transaction_objects_621560.htm&language=en_US&type=5)**  
    Vlocity provides a Transactions object to support transaction component functionality.

Did this article solve your issue?

Let us know so we can improve!

YesNo