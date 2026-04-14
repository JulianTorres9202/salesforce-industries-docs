---
title: "Fetch Group Class Contribution Records for Premium Calculation"
source: "https://help.salesforce.com/s/articleView?id=ind.insurance_fetch_group_class_contribution_record_for_premium_calculation.htm&language=en_US&type=5"
scraped: "2026-04-14"
filter: "ind.insurance_"
---# Fetch Group Class Contribution Records for Premium Calculation

Fetch Group Class Contribution Records for Premium Calculation[](https://help.salesforce.com/s?language=en_US)

You are here:

1.  [Salesforce Help](/s/?language=en_US)
2.  [Docs](/s/products?language=en_US)
3.  [Digital Insurance](https://help.salesforce.com/s/articleView?id=ind.insurance_admin_standard.htm&language=en_US&type=5)

# Fetch Group Class Contribution Records for Premium Calculation

During enrollment, fetch all the valid group class contribution records for the group class associated with each member.

Valid records are group class contributions with a start date on or before the contract start date, an end date on or after the contract end date, and a type that's not blank or null.

The logic used to select the group class contribution record from the fetched list to calculate premium for a specific census member and plan combination are described in the later sections. For each of the below mentioned cases, if there are multiple group class contribution records, the most recently modified group class contribution record is picked up to calculate premium.

## With Member Level Premium For Subscriber

-   `ContractGroupPlanID` + `MemberType` = `Subscriber`
    
-   `ContractGroupPlanID`
    
-   `ProductID` + `MemberType` = `Subscriber`
    
-   `ProductID`
    
-   `ProductCategory` \+ `MemberType` = `Subscriber`
    
-   `ProductCategory`
    

## With Member Level Premium for Dependent

-   `ContractGroupPlanID` \+ `MemberType` = `Dependent`
    
-   `ContractGroupPlanID` + `MemberType` = `Subscriber`
    
-   `ContractGroupPlanID`
    
-   `ProductID` + `MemberType` \= `Dependent`
    
-   `ProductID` \+ `MemberType` = `Subscriber`
    
-   `ProductID`
    
-   `ProductCategory` + `MemberType` = `Dependen`t
    
-   `ProductCategory` + `MemberType` = `Subscriber`
    
-   `ProductCategory`
    

## Without Member Level Premium for Primary and Dependent

-   `ContractGroupPlanID` + `MemberType` = `Subscriber`
    
-   `ContractGroupPlanID`
    
-   `ProductID` + `MemberType` = `Subscriber`
    
-   `ProductID`
    
-   `ProductCategory` + `MemberType` = `Subscriber`
    
-   `ProductCategory`
    

Did this article solve your issue?

Let us know so we can improve!

YesNo