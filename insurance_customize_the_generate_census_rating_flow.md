---
title: "Customize the Generate Census Rating Flow"
source: "https://help.salesforce.com/s/articleView?id=ind.insurance_customize_the_generate_census_rating_flow.htm&language=en_US&type=5"
scraped: "2026-04-14"
filter: "ind.insurance_"
---# Customize the Generate Census Rating Flow

Customize the Generate Census Rating Flow[](https://help.salesforce.com/s?language=en_US)

You are here:

1.  [Salesforce Help](/s/?language=en_US)
2.  [Docs](/s/products?language=en_US)
3.  [Digital Insurance](https://help.salesforce.com/s/articleView?id=ind.insurance_admin_standard.htm&language=en_US&type=5)

# Customize the Generate Census Rating Flow

To use the Generate Census Rating flow for large group quoting, add the fields you use for rating to action elements.

1.  From Setup, in the Quick Find box, enter Flows, and then select **Flows**.
2.  Open the flow that you made by configuring the Generate Census Rating flow template.
    
    This flow is used to rate one family (the family of one groupCensusMemberId).
    
3.  Edit the Get Group Census Member Family action. In the Select Group Census Member Fields to Store in Variable list, add fields from the Group Census Member object that you use for rating.
    
    For example, if your Rating Expression Set uses the **Gender** and **Age** of a member, add the **Gender** and **Birthdate** fields.
    
    Note Don’t remove the GroupClassId, RelationshipToPrimaryMember, and PrimaryGroupCensusMemberId fields from the list.
    
4.  Edit the Get Account action. In the Select Account Fields to Store in Variable list, add fields from the Account object that you use for rating.
5.  Edit the Get Group Census action. In the Select Group Census Fields to Store in Variable list, add fields from the Group Census object that you use for rating.
6.  Save and activate your flow.

Did this article solve your issue?

Let us know so we can improve!

YesNo