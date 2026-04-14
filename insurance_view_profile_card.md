---
title: "View Profile Card"
source: "https://help.salesforce.com/s/articleView?id=ind.insurance_view_profile_card.htm&language=en_US&type=5"
scraped: "2026-04-14"
filter: "ind.insurance_"
---# View Profile Card

View Profile Card[](https://help.salesforce.com/s?language=en_US)

You are here:

1.  [Salesforce Help](/s/?language=en_US)
2.  [Docs](/s/products?language=en_US)
3.  [Digital Insurance](https://help.salesforce.com/s/articleView?id=ind.insurance_admin_standard.htm&language=en_US&type=5)

# View Profile Card

Customer service representatives can view an insurance customer’s basic information on the Profile Card.

The Profile card is built using OmniStudio and includes these customer details:

-   Name and Profile Picture
    
-   Address and Contacts
    
-   Tags
    
-   Policy Types
    

Name and Profile Picture

The profile card displays the photo and nickname of the active customer community user linked to the account. If there is no active user, the profile card displays a default icon, and no nickname appears. If there are multiple user records for an account, the profile card shows the details of the last created user.

Tags

The Insurance Agent Console has these preconfigured tags:

1.  Customer Since: This tag shows the year this account record was created.
    
2.  Upcoming Birthday: This tag is shown if the birthday is within the next two weeks. Displays ‘Birthday Today’ if the birthday is today.
    
3.  Age: This tag is displayed when the customer is over 50 years old or is a minor.
    
4.  High-Value Customer: This tag is displayed when the customer pays more than $100,000 as a Standard Premium across all of their insurance policies
    

You can customize tags based on your requirements.

Policy Types

The profile card displays the different types of insurance policies that a customer owns. If the customer has more than five policy types, the profile card displays only the first five policies sorted alphabetically.

Customize the Profile Card

To customize a Profile card, clone the card in OmniStudio, and then modify the card and the corresponding DataRaptor for custom content. If the Profile card is missing from your **Insurance Agent Console**, go to the Lightning App Builder and add the `OrganicINSISEProfileCard` to the page layout.

Did this article solve your issue?

Let us know so we can improve!

YesNo