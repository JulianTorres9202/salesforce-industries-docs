---
title: "Add and Configure Products on a Group Quote"
source: "https://help.salesforce.com/s/articleView?id=ind.insurance_group_benefits_core_add_and_configure_group_quote.htm&language=en_US&type=5"
scraped: "2026-04-14"
filter: "ind.insurance_"
---# Add and Configure Products on a Group Quote

Add and Configure Products on a Group Quote[](https://help.salesforce.com/s?language=en_US)

You are here:

1.  [Salesforce Help](/s/?language=en_US)
2.  [Docs](/s/products?language=en_US)
3.  [Digital Insurance](https://help.salesforce.com/s/articleView?id=ind.insurance_admin_standard.htm&language=en_US&type=5)

# Add and Configure Products on a Group Quote

Use the configurator to add a root product to a group quote and configure its group classes, members, and coverages.

### Required Editions

<table class="slds-table slds-table_bordered slds-m-bottom_small edition" lwc-3eigj2skqo3=""><colgroup lwc-3eigj2skqo3=""><col style="width:100%" lwc-3eigj2skqo3=""></colgroup><tbody lwc-3eigj2skqo3=""><tr class="" lwc-3eigj2skqo3=""><td style="vertical-align:top;" class="slds-cell-wrap" lwc-3eigj2skqo3="">Available in: Lightning Experience</td></tr><tr class="" lwc-3eigj2skqo3=""><td style="vertical-align:top;" class="slds-cell-wrap" lwc-3eigj2skqo3="">Available in: <strong class="uicontrol" lwc-3eigj2skqo3="">Professional</strong>, <strong class="uicontrol" lwc-3eigj2skqo3="">Enterprise</strong>, and<strong class="uicontrol" lwc-3eigj2skqo3=""> Unlimited</strong> Editions of Digital Insurance with Digital Insurance Product Admin Add On, Digital Insurance Group Benefits AddOn, Digital Insurance Group Enrollment AddOn,Digital Insurance Group Benefits Customer Community AddOn, and Digital Insurance Group Benefits Partner Community AddOn licenses</td></tr></tbody></table>

| User Permissions Needed |
| --- |
| To add and configure products on group quote | Digital Insurance Group Census Quote Contract Management, Digital Insurance Group Census Quote Contract Management Partner Community |

Census Rating Type

When you create a group quote, you must select a Census Rating Type. This choice determines the level of detail used to calculate premiums.

-   Summary Based – Uses attributes from the Group Census Group Class Summary entity. Admins configure attributes such as Total Members or Total Dependents and link them to fields on the group class summary. This option is useful when you want faster, high-level rating without evaluating each member individually. Premiums are calculated at the group class summary level.
-   Member Based – Uses attributes from the Group Census Member entity. Admins configure attributes such as Age and Gender and link them to fields on the member record. This option is useful when you need more accurate pricing based on each member or family. Rating is applied at the member or family level, and premiums are calculated at the overall group level.

1.  From the App Launcher, find and select **Quotes**.
2.  Click **New Quote**.
3.  Specify these details.
    
    -   Enter a name.
    -   Select Insurance Quote Type as **New Group Business**.
    -   Select the Group Census to use.
    -   Select an account.
    -   Choose a census rating type: Summary Based or Member Based.
    
4.  Save your changes.
5.  On the quote details page, click **Browse Catalogs**.
6.  Select a price book. For example, Standard Price Book.
7.  Save your changes.
8.  Select a catalog. For example Group Insurance.
9.  Click **Next**.
    
    The product catalog shows all product categories and products in those categories.
    
10.  Find the product you want to add. For example, Critical Illness Silver.
11.  Click configure (gear icon) next to a selected product or add the root product directly and then configure the product later from the Insurance Quote Line Item Grid.
12.  Configure the selected product.
     1.  Click **Add Group Summary**.
         
         -   If members in your census are associated with a group class, select one or more group census group class summary records based on the group classes for which you want the product to be available.
         -   If the members in your census aren’t associated with a group class or you want the same configuration for all the members irrespective of group classes, select the group census group class summary record where group class is blank. This record represents the entire group census.
         
     2.  Save your changes. The configurator API invokes the product configuration flow. For each group census group summary record, the configurator creates a group class instance, links extended attributes, adds a member placeholder, and adds the product’s coverages under that member.
         
         During rating, this placeholder member is replaced with the specific members of the associated group census to fetch the attributes in case of member-based rating.
         
     3.  Use the gear icon against the member quote line item to configure coverages applicable to all the members within that group class or group census.
13.  Click **Save and Exit** to apply the configuration and return to the quote. The Quote Line Item Grid shows the complete hierarchy: Root Product, Group Class, Members, and Coverages.

Did this article solve your issue?

Let us know so we can improve!

YesNo