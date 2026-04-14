---
title: "Policyholder Digital Experience Site Component Catalog"
source: "https://help.salesforce.com/s/articleView?id=ind.insurance_policyholder_digital_experience_site_component_catalog_645782.htm&language=en_US&type=5"
scraped: "2026-04-14"
filter: "ind.insurance_"
---# Policyholder Digital Experience Site Component Catalog

Policyholder Digital Experience Site Component Catalog[](https://help.salesforce.com/s?language=en_US)

You are here:

1.  [Salesforce Help](/s/?language=en_US)
2.  [Docs](/s/products?language=en_US)
3.  [Digital Insurance](https://help.salesforce.com/s/articleView?id=ind.insurance_admin_standard.htm&language=en_US&type=5)

# Policyholder Digital Experience Site Component Catalog

The Policyholder site contains a bunch of components to get you started with providing your policyholders with functionality they can use to self-manage some parts of their policies.

These components are FlexCard based. They are created for use in the Policyholder site. These components are made with FlexCards that you can customize and activate to compile Lightning web components for use on the site.

Some of these components call data sources, such as:

-   Omnistudio Data Mappers
    
-   Integrations Procedures
    
-   Insurance Services
    

All of these data sources come out-of-the-box with Vlocity Insurance. The data sources are listed in the tables below.

Additionally, some components use Einstein Strategy Services which you need to configure for your org. Learn more about Einstein Strategy Services [here](https://help.salesforce.com/s/articleView?id=sf.https%3A%2F%2Fhelp.salesforce.com%2Fs%2F.htm&language=en_US&type=5).

[](https://help.salesforce.com/s?language=en_US)

## Policyholder Home Page

| 
Component

 | 

Designed for Desktop, Mobile or Both?

 | 

Data Source Called

 | 

What it Does

 |
| --- | --- | --- | --- |
| 

[Insurance Account Actions Component](https://help.salesforce.com/s/articleView?id=ind.insurance_t_insurance_account_actions_component_646375.htm&language=en_US&type=5 "Quickly provide your Policyholder site users with links to common account management tasks with the Insurance Account Actions component.")

 | 

Desktop

 | 

N/A

 | 

Quickly provide your Policyholder site users with links to common account management tasks with the Insurance Account Actions component.

 |
| 

[Mobile Insurance Account Actions Component](https://help.salesforce.com/s/articleView?id=ind.insurance_mobile_insurance_account_actions_component_646299.htm&language=en_US&type=5 "Quickly provide your mobile Policyholder site users with links to common account management tasks with the Mobile Insurance Account Actions component. The Mobile Insurance Account Actions component sits inside of the Mobile Insurance Header component.")

 | 

Mobile

 | 

N/A

 | 

Quickly provide your mobile Policyholder site users with links to common account management tasks with the Mobile Insurance Account Actions component.

 |
| 

[Insurance Articles Component](https://help.salesforce.com/s/articleView?id=ind.insurance_t_insurance_articles_component_646460.htm&language=en_US&type=5 "Show your Policyholder site users interesting and relevant articles to help keep them up-to-date on the latest news about your company with the Insurance Articles Component.")

 | 

Both

 | 

Data source called in child component

 | 

Show your Policyholder site users interesting and relevant articles to help keep them up-to-date on the latest news about your company with the Insurance Articles Component.

 |
| 

[Insurance Articles Child Component](https://help.salesforce.com/s/articleView?id=ind.insurance_t_insurance_articles_child_component_646525.htm&language=en_US&type=5 "Show your Policyholder site users articles that they might find helpful and interesting with the Insurance Articles Child component. It's a child component that sits inside of the Insurance Articles container component.")

 | 

Both

 | 

Einstein Strategy Service:

getNBARecommendations

 | 

Show your Policyholder site users articles that they might find helpful and interesting with the Insurance Articles Child component. It's a child component that sits inside of the Insurance Articles container component.

 |
| 

[Insurance Footer Component](https://help.salesforce.com/s/articleView?id=ind.insurance_t_insurance_footer_component_647161.htm&language=en_US&type=5 "Provide your Policyholder site users with links to helpful resources with the Insurance Footer component. We have included placeholder links that you can replace with your own links.")

 | 

Desktop

 | 

N/A

 | 

Provide your Policyholder site users with links to helpful resources with the Insurance Footer component. We have included placeholder links that you can replace with your own links.

 |
| 

[Mobile Insurance Footer Component](https://help.salesforce.com/s/articleView?id=ind.insurance_mobile_insurance_footer_component_647237.htm&language=en_US&type=5 "Provide your mobile Policyholder site users with links to helpful resources with the Mobile Insurance Footer component. We have included placeholder links that you can replace with your own links.")

 | 

Mobile

 | 

N/A

 | 

Provide your mobile Policyholder site users with links to helpful resources with the Mobile Insurance Footer component. We have included placeholder links that you can replace with your own links.

 |
| 

[Insurance Home Header Component](https://help.salesforce.com/s/articleView?id=ind.insurance_t_insurance_home_header_component_647404.htm&language=en_US&type=5 "Welcome your user to their own personalized Policyholder site with the Insurance Home Header component.")

 | 

Desktop

 | 

Data Mapper:

InsExtractAccountDetails

 | 

Welcome your user to their own personalized Policyholder site with the Insurance Home Header component.

 |
| 

[Mobile Insurance Home Header Component](https://help.salesforce.com/s/articleView?id=ind.insurance_mobile_insurance_home_header_component_647480.htm&language=en_US&type=5 "Welcome your mobile user to their own personalized Policyholder site with the Mobile Insurance Home Header component.")

 | 

Mobile

 | 

Data Mapper:

InsExtractAccountDetails

 | 

Welcome your mobile user to their own personalized Policyholder site with the Mobile Insurance Home Header component.

 |
| 

[Insurance Open Claims Component](https://help.salesforce.com/s/articleView?id=ind.insurance_t_insurance_open_claims_component_647727.htm&language=en_US&type=5 "Show your Policyholder site users a snapshot of their open claims, and link them to additional information about the claims with the Insurance Open Claims component.")

 | 

Desktop

 | 

Data source called in child component

 | 

Show your Policyholder site users a snapshot of their open claims, and link them to additional information about the claims with the Insurance Open Claims component.

 |
| 

[Mobile Insurance Open Claims Component](https://help.salesforce.com/s/articleView?id=ind.insurance_mobile_insurance_open_claims_component_647894.htm&language=en_US&type=5 "Show your mobile Policyholder users a snapshot of their open claims, and link them to additional information about the claims with the Mobile Insurance Open Claims component.")

 | 

Mobile

 | 

Data source called in child component

 | 

Show your mobile Policyholder users a snapshot of their open claims, and link them to additional information about the claims, with the Mobile Insurance Open Claims component.

 |
| 

[Open Claims Child Component](https://help.salesforce.com/s/articleView?id=ind.insurance_open_claims_child_component_647795.htm&language=en_US&type=5 "Use the Insurance Open Claims Child component to show your Policyholder site users a snapshot of their open claims, and link them to additional information about the claims. It's a child component that sits inside of the Insurance Open Claims container component.")

 | 

Desktop

 | 

Data Mapper: InsReadAccountPolicyClaims

 | 

Use the Insurance Open Claims Child component to show your Policyholder site users a snapshot of their open claims, and link them to additional information about the claims. It's a child component that sits inside of the Insurance Open Claims container component.

 |
| 

[Mobile Insurance Open Claims Child Component](https://help.salesforce.com/s/articleView?id=ind.insurance_mobile_insurance_open_claims_child_component_647961.htm&language=en_US&type=5 "Use the Mobile Insurance Open Claims Child component to show your Policyholder site users a snapshot of their open claims, and link them to additional information about the claims. It's a child component that sits inside of the Mobile Insurance Open Claims container component.")

 | 

Mobile

 | 

Data Mapper: InsReadAccountPolicyClaims

 | 

Use the Mobile Insurance Open Claims Child component to show your Policyholder site users a snapshot of their open claims, and link them to additional information about the claims. It's a child component that sits inside of the Mobile Insurance Open Claims container component.

 |
| 

[Insurance Policy List Component](https://help.salesforce.com/s/articleView?id=ind.insurance_policy_list_component_648476.htm&language=en_US&type=5 "Show your Policyholder site users a list of insurance policies they have with the Insurance Policy List component. It's a container component that displays a label and a list of policies in the Insurance Policy List Child component.")

 | 

Desktop

 | 

Data source called in child component

 | 

Show your Policyholder site users a list of insurance policies they have with the Insurance Policy List component. It's a container component that displays a label and a list of policies in the Insurance Policy List Child component.

 |
| 

[Mobile Insurance Policy List Component](https://help.salesforce.com/s/articleView?id=ind.insurance_t_mobile_insurance_policy_list_component_648702.htm&language=en_US&type=5 "Show your mobile Policyholder site users a list of insurance policies they have with the Mobile Insurance Policy List component. It's a container component that displays a label and a list of policies in the Mobile Insurance Policy List Child component.")

 | 

Mobile

 | 

Data source called in child component

 | 

Show your mobile Policyholder site users a list of insurance policies they have with the Mobile Insurance Policy List component. It's a container component that displays a label and a list of policies in the Mobile Insurance Policy List Child component.

 |
| 

[Insurance Policy List Child Component](https://help.salesforce.com/s/articleView?id=ind.insurance_policy_list_child_component_648540.htm&language=en_US&type=5 "Display a list of insurance policies your Policyholder site users have with the Insurance Policy List Child component. It's a child component that sits inside of the Policy List component container and displays information about all of the policies the user has.")

 | 

Desktop

 | 

Data Mapper: InsReadAccountPolicies

 | 

Display a list of insurance policies your Policyholder site users have with the Insurance Policy List Child component. It's a child component that sits inside of the Insurance Policy List component container and displays information about all of the policies the user has.

 |
| 

[Mobile Insurance Policy List Child Component](https://help.salesforce.com/s/articleView?id=ind.insurance_t_mobile_insurance_policy_list_child_component_648761.htm&language=en_US&type=5 "Display a list of insurance policies your mobile Policyholder site users have with the Mobile Insurance Policy List Child component. It's a child component that sits inside of the Mobile Insurance Policy List component container and displays information about policies the user has.")

 | 

Mobile

 | 

Data Mapper: InsReadAccountPolicies

 | 

Display a list of insurance policies your mobile Policyholder site users have with the Mobile Insurance Policy List Child component. It's a child component that sits inside of the Mobile Insurance Policy List component container and displays information about all of the policies the user has.

 |
| 

[Insurance Policy List Flyout Component](https://help.salesforce.com/s/articleView?id=ind.insurance_policy_list_flyout_component_648865.htm&language=en_US&type=5 "Show your Policyholder site users a breakdown of the policy premium, taxes, and fees right on the policy list with the Insurance Policy List Flyout Component. The Insurance Policy List Flyout component is a child of the Insurance Policy List, Mobile Insurance Policy List, and Insurance Policy Details components.")

 | 

Both

 | 

N/A

 | 

Show your Policyholder site users a breakdown of the policy premium, taxes, and fees right on the policy list with the Insurance Policy List Flyout Component. The Insurance Policy List Flyout component is a child of the Insurance Policy List, Mobile Insurance Policy List, and Insurance Policy Details components.

 |
| 

[Insurance Policy List Icons Component](https://help.salesforce.com/s/articleView?id=ind.insurance_policy_list_icons_component_648655.htm&language=en_US&type=5 "Display an icon of your choice to denote the type of policy on the policy list with the Insurance Policy List Icons component.")

 | 

Both

 | 

N/A

 | 

Display an icon of your choice to denote the type of policy on the Insurance Policy List with the Insurance Policy List Icons component. It's a child component that sits inside of the Insurance Policy List container component.

 |
| 

[Insurance Recent Activity Component](https://help.salesforce.com/s/articleView?id=ind.insurance_recent_activity_component_649144.htm&language=en_US&type=5 "Show your Policyholder site users a snapshot of the recent activity on their policies with the Insurance Recent Activity component.")

 | 

Desktop

 | 

Data source called in child component

 | 

Show your Policyholder site users a snapshot of the recent activity on their policies with the Insurance Recent Activity component.

 |
| 

[Mobile Insurance Recent Activity Component](https://help.salesforce.com/s/articleView?id=ind.insurance_t_mobile_insurance_recent_activity_component_649287.htm&language=en_US&type=5 "Show your mobile Policyholder site users a snapshot of the recent activity on their policies with the Mobile Insurance Recent Activity component.")

 | 

Mobile

 | 

Data source called in child component

 | 

Show your mobile Policyholder site users a snapshot of the recent activity on their policies with the Mobile Insurance Recent Activity component.

 |
| 

[Insurance Recent Activity Child Component](https://help.salesforce.com/s/articleView?id=ind.insurance_recent_activity_child_component_649207.htm&language=en_US&type=5 "Show your Policyholder site users a snapshot of their recent activity with the Insurance Recent Activity Child component. It's a child component that sits inside of the Insurance Recent Activity container component.")

 | 

Desktop

 | 

Integration Procedure: InsAccount\_GetStories

 | 

Show your Policyholder site users a snapshot of their recent activity with the Insurance Recent Activity Child component . It's a child component that sits inside of the Insurance Recent Activity container component.

 |
| 

[Mobile Insurance Recent Activity Child Component](https://help.salesforce.com/s/articleView?id=ind.insurance_t_mobile_insurance_recent_activity_child_component_649346.htm&language=en_US&type=5 "Show your mobile Policyholder site users a snapshot of their recent activity with the Mobile Insurance Recent Activity Child component. It's a child component that sits inside of the Mobile Insurance Recent Activity container component.")

 | 

Mobile

 | 

Integration Procedure: InsAccount\_GetStories

 | 

Show your mobile Policyholder site users a snapshot of their recent activity with the Mobile Insurance Recent Activity Child component . It's a child component that sits inside of the Mobile Insurance Recent Activity container component.

 |
| 

[Your Agent Component](https://help.salesforce.com/s/articleView?id=ind.insurance_your_agent_component_649428.htm&language=en_US&type=5 "Your Policyholder site users can view details and contact their agent from the Your Agent component.")

 | 

Both

 | 

Data Mapper: InsReadAccountContactDetails

 | 

Your Policyholder site users can view details and contact their agent from the Your Agent component.

 |

[](https://help.salesforce.com/s?language=en_US)

## Policyholder Policies Page

| 
Component

 | 

Designed for Desktop, Mobile, or Both?

 | 

Data Source Called

 | 

What it Does

 |
| --- | --- | --- | --- |
| 

[Insurance Manage Policy Component](https://help.salesforce.com/s/articleView?id=ind.insurance_t_insurance_manage_policy_component_647566.htm&language=en_US&type=5 "Quickly provide your Policyholder site users with links to common policy management tasks with the Insurance Manage Policy component.")

 | 

Desktop

 | 

Data Mapper:

InsGetPolicyDetails

 | 

Quickly provide your Policyholder site users with links to common policy management tasks with the Insurance Manage Policy component.

 |
| 

[Mobile Insurance Manage Policy Component](https://help.salesforce.com/s/articleView?id=ind.insurance_mobile_insurance_manage_policy_component_647648.htm&language=en_US&type=5 "Quickly link your mobile Policyholder site users to common policy management tasks with the Mobile Insurance Manage Policy component.")

 | 

Mobile

 | 

Data Mapper:

InsGetPolicyDetails

 | 

Quickly link your mobile Policyholder site users to common policy management tasks with the Mobile Insurance Manage Policy component.

 |
| 

[Insurance Policy Claims Component](https://help.salesforce.com/s/articleView?id=ind.insurance_policy_claims_component_648060.htm&language=en_US&type=5 "Show your Policyholder site users a snapshot of their open claims on a policy and link them to additional information about the claims with the Insurance Policy Claims component.")

 | 

Both

 | 

Data source called in child component

 | 

Show your Policyholder site users a snapshot of their open claims on a policy and link them to additional information about the claims with the Insurance Policy Claims component.

 |
| 

[Insurance Policy Claims Child Component](https://help.salesforce.com/s/articleView?id=ind.insurance_policy_claims_child_component_648123.htm&language=en_US&type=5 "Use the Insurance Policy Claims Child component to show your Policyholder site users a snapshot of their open claims on a policy and link them to additional information about the claim. It's a child component that sits inside of the Insurance Policy Claims container component.")

 | 

Both

 | 

Data Mapper:

InsGetPolicyClaimList

 | 

Use the Insurance Policy Claims Child component to show your Policyholder site users a snapshot of their open claims on a policy and link them to additional information about the claim. It's a child component that sits inside of the Insurance Policy Claims container component.

 |
| 

[Insurance Policy Details Component](https://help.salesforce.com/s/articleView?id=ind.insurance_policy_details_component_648218.htm&language=en_US&type=5 "Show your Policyholder site users details about insured items associated with their policy with the Insurance Policy Details component.")

 | 

Both

 | 

Insurance Service:

InsuranceAssetHandler:getPolicyDetails

 | 

Show your Policyholder site users details about insured items associated with their policy with the Insurance Policy Details component.

 |
| 

[FSC Insurance Policy Details Component](https://help.salesforce.com/s/articleView?id=ind.insurance_fsc_insurance_policy_details_component_647316.htm&language=en_US&type=5 "Show your Policyholder site users details about insured items associated with their FSC policy with the FSC Insurance Policy Details component.")

 | 

Both

 | 

Insurance Service:

InsPolicyService:getPolicyDetails

 | 

Show your Policyholder site users details about insured items associated with their FSC policy with the FSC Insurance Policy Details component.

 |
| 

[Insurance Policy Header Component](https://help.salesforce.com/s/articleView?id=ind.insurance_policy_header_component_648304.htm&language=en_US&type=5 "Display the policy name and key policy data for your Policyholder Experience site users with the Insurance Policy Header Component.")

 | 

Desktop

 | 

Data Mapper:

InsGetPolicyDetails

 | 

Display the policy name and key policy data for your Policyholder site users with the Insurance Policy Header Component.

 |
| 

[Mobile Insurance Policy Header Component](https://help.salesforce.com/s/articleView?id=ind.insurance_t_mobile_insurance_policy_header_component_648386.htm&language=en_US&type=5 "Display the policy name and key policy data for your mobile Policyholder site users with the Mobile Insurance Policy Header Component.")

 | 

Mobile

 | 

Data Mapper:

InsGetPolicyDetails

 | 

Display the policy name and key policy data for your mobile Policyholder site users with the Mobile Insurance Policy Header Component.

 |
| 

[Insurance Policy Overview Component](https://help.salesforce.com/s/articleView?id=ind.insurance_policy_overview_component_648926.htm&language=en_US&type=5 "Show your Policyholder site users key information about their policy with the Insurance Policy Overview Component.")

 | 

Both

 | 

Data Mapper:

InsGetPolicyDetails

 | 

Show your Policyholder site users key information about their policy with the Insurance Policy Overview Component.

 |
| 

[Insurance Policy Transaction Component](https://help.salesforce.com/s/articleView?id=ind.insurance_policy_transaction_component_649008.htm&language=en_US&type=5 "Show your Policyholder site users recent transactions on their policy with the Insurance Policy Transaction component. It's a container component that displays a label and a list of transactions in the child component.")

 | 

Both

 | 

Data source called in child component

 | 

Show your Policyholder site users recent transactions on their policy with the Insurance Policy Transaction component. It's a container component that displays a label and a list of transactions in the Insurance Policy Transaction Child component.

 |
| 

[Insurance Policy Transaction Child Component](https://help.salesforce.com/s/articleView?id=ind.insurance_policy_transaction_child_component_649070.htm&language=en_US&type=5 "Display a list of recent transactions on a policy to your Policyholder site users with the Insurance Policy Transaction Child component. It's a child component that sits inside of the Insurance Policy Transactions container component.")

 | 

Both

 | 

Data Mapper:

InsGetPolicyTransactionsList

 | 

Display a list of recent transactions on a policy to your Policyholder site users with the Insurance Policy Transaction Child component. It's a child component that sits inside of the Insurance Policy Transactions container component.

 |

[](https://help.salesforce.com/s?language=en_US)

## Policyholder Billing Page

| 
Component

 | 

Designed for Desktop, Mobile, or Both?

 | 

Data Source Called

 | 

What it Does

 |
| --- | --- | --- | --- |
| 

[Insurance Billing Description Component](https://help.salesforce.com/s/articleView?id=ind.insurance_t_insurance_billing_description_component_646590.htm&language=en_US&type=5 "Show your Policyholder site users an overview of their billing information with the Insurance Billing Description component.")

 | 

Both

 | 

Data Mapper:

InsExtractAccountBillingDetails

 | 

Show your Policyholder site users an overview of their billing information with the Insurance Billing Description component.

 |
| 

[Insurance Billing Description Child Component](https://help.salesforce.com/s/articleView?id=ind.insurance_t_insurance_billing_description_child_component_646670.htm&language=en_US&type=5 "Use the Insurance Billing Description Child component to show your Policyholder site users an overview of their billing information, and link them to additional information about their billing account. The Insurance Billing Description Child component sits inside of the Insurance Billing Description component container.")

 | 

Both

 | 

Data Mapper:

InsExtractAccountBillingDetails

 | 

Use the Insurance Billing Description Child component to show your Policyholder site users an overview of their billing information, and link them to additional information about their billing account. It's a child component that sits inside of the Insurance Billing Description container component.

 |
| 

[Insurance Billing Header Component](https://help.salesforce.com/s/articleView?id=ind.insurance_t_insurance_billing_header_component_646904.htm&language=en_US&type=5 "The Insurance Billing Header component displays a Billing info label and the policyholder's name for your Policyholder site users.")

 | 

Desktop

 | 

Data Mapper:

InsExtractAccountBillingDetails

 | 

Display a Billing info label and the policyholder's name for your Policyholder site users with the Insurance Billing Header component.

 |
| 

[Mobile Insurance Billing Header Component](https://help.salesforce.com/s/articleView?id=ind.insurance_mobile_insurance_billing_header_component_646997.htm&language=en_US&type=5 "The Mobile Insurance Billing Header component displays a Billing info label and the policyholder's name for your mobile Policyholder site users.")

 | 

Mobile

 | 

Data Mapper:

InsExtractAccountBillingDetails

 | 

The Mobile Insurance Billing Header component displays a Billing Info label and the policyholder's name for your mobile Policyholder site users.

 |
| 

[Insurance Billing Strategy Child Component](https://help.salesforce.com/s/articleView?id=ind.insurance_t_insurance_billing_strategy_child_component_646852.htm&language=en_US&type=5 "Provide your Policyholder site users with billing option strategies the help them manage their accounts with the Insurance Billing Strategy Child component. The Insurance Billing Strategy Child component sits inside of the Insurance Billing Description component.")

 | 

Both

 | 

Einstein Strategy Service:

getNBARecommendations

 | 

Provide your Policyholder site users with billing option strategies to help them manage their accounts with the Insurance Billing Strategy Child component. The Insurance Billing Strategy Child component sits inside of the Insurance Billing Description component.

 |
| 

[Insurance Billing Transaction Component](https://help.salesforce.com/s/articleView?id=ind.insurance_t_insurance_billing_transaction_component_647090.htm&language=en_US&type=5 "Your Policyholder site users can view a summary of previous transactions on their account on the Insurance Billing Transactions component.")

 | 

Both

 | 

Data Mapper:

InsGetPolicyTransactionDetails

 | 

Your Policyholder site users can view a summary of previous transactions on their account on the Insurance Billing Transactions component.

 |
| 

[Insurance Policy Billing Child Component](https://help.salesforce.com/s/articleView?id=ind.insurance_t_insurance_policy_billing_child_component_646789.htm&language=en_US&type=5 "Show your Policyholder Experience site users an overview of the amount due for their policies with the Insurance Policy Billing Child component. The Insurance Policy Billing Child component sits inside of the Insurance Billing Description Child component container.")

 | 

Both

 | 

Data Mapper:

InsGetPolicyTransactionDetails

 | 

Show your Policyholder site users an overview of the amount due for their policies with the Insurance Policy Billing Child component. The Insurance Policy Billing Child component sits inside of the Insurance Billing Description Child component container.

 |

[](https://help.salesforce.com/s?language=en_US)

## What's Next?

Ready to get started? Read [Set Up Your Digital Experience Site](https://help.salesforce.com/s/articleView?id=ind.insurance_set_up_your_digital_experience_site_649987.htm&language=en_US&type=5 "Create an Experience site for your users using the templates provided in the Insurance FSC unmanaged package.").

-   **[Mobile Insurance Account Actions Component](https://help.salesforce.com/s/articleView?id=ind.insurance_mobile_insurance_account_actions_component_646299.htm&language=en_US&type=5)**  
    Quickly provide your mobile Policyholder site users with links to common account management tasks with the Mobile Insurance Account Actions component. The Mobile Insurance Account Actions component sits inside of the Mobile Insurance Header component.
-   **[Insurance Account Actions Component](https://help.salesforce.com/s/articleView?id=ind.insurance_t_insurance_account_actions_component_646375.htm&language=en_US&type=5)**  
    Quickly provide your Policyholder site users with links to common account management tasks with the Insurance Account Actions component.
-   **[Insurance Articles Component](https://help.salesforce.com/s/articleView?id=ind.insurance_t_insurance_articles_component_646460.htm&language=en_US&type=5)**  
    Show your Policyholder site users interesting and relevant articles to help keep them up-to-date on the latest news about your company with the Insurance Articles Component.
-   **[Insurance Billing Description Component](https://help.salesforce.com/s/articleView?id=ind.insurance_t_insurance_billing_description_component_646590.htm&language=en_US&type=5)**  
    Show your Policyholder site users an overview of their billing information with the Insurance Billing Description component.
-   **[Insurance Billing Header Component](https://help.salesforce.com/s/articleView?id=ind.insurance_t_insurance_billing_header_component_646904.htm&language=en_US&type=5)**  
    The Insurance Billing Header component displays a Billing info label and the policyholder's name for your Policyholder site users.
-   **[Mobile Insurance Billing Header Component](https://help.salesforce.com/s/articleView?id=ind.insurance_mobile_insurance_billing_header_component_646997.htm&language=en_US&type=5)**  
    The Mobile Insurance Billing Header component displays a Billing info label and the policyholder's name for your mobile Policyholder site users.
-   **[Insurance Billing Transaction Component](https://help.salesforce.com/s/articleView?id=ind.insurance_t_insurance_billing_transaction_component_647090.htm&language=en_US&type=5)**  
    Your Policyholder site users can view a summary of previous transactions on their account on the Insurance Billing Transactions component.
-   **[Insurance Footer Component](https://help.salesforce.com/s/articleView?id=ind.insurance_t_insurance_footer_component_647161.htm&language=en_US&type=5)**  
    Provide your Policyholder site users with links to helpful resources with the Insurance Footer component. We have included placeholder links that you can replace with your own links.
-   **[Mobile Insurance Footer Component](https://help.salesforce.com/s/articleView?id=ind.insurance_mobile_insurance_footer_component_647237.htm&language=en_US&type=5)**  
    Provide your mobile Policyholder site users with links to helpful resources with the Mobile Insurance Footer component. We have included placeholder links that you can replace with your own links.
-   **[FSC Insurance Policy Details Component](https://help.salesforce.com/s/articleView?id=ind.insurance_fsc_insurance_policy_details_component_647316.htm&language=en_US&type=5)**  
    Show your Policyholder site users details about insured items associated with their FSC policy with the FSC Insurance Policy Details component.
-   **[Insurance Home Header Component](https://help.salesforce.com/s/articleView?id=ind.insurance_t_insurance_home_header_component_647404.htm&language=en_US&type=5)**  
    Welcome your user to their own personalized Policyholder site with the Insurance Home Header component.
-   **[Mobile Insurance Home Header Component](https://help.salesforce.com/s/articleView?id=ind.insurance_mobile_insurance_home_header_component_647480.htm&language=en_US&type=5)**  
    Welcome your mobile user to their own personalized Policyholder site with the Mobile Insurance Home Header component.
-   **[Insurance Manage Policy Component](https://help.salesforce.com/s/articleView?id=ind.insurance_t_insurance_manage_policy_component_647566.htm&language=en_US&type=5)**  
    Quickly provide your Policyholder site users with links to common policy management tasks with the Insurance Manage Policy component.
-   **[Mobile Insurance Manage Policy Component](https://help.salesforce.com/s/articleView?id=ind.insurance_mobile_insurance_manage_policy_component_647648.htm&language=en_US&type=5)**  
    Quickly link your mobile Policyholder site users to common policy management tasks with the Mobile Insurance Manage Policy component.
-   **[Insurance Open Claims Component](https://help.salesforce.com/s/articleView?id=ind.insurance_t_insurance_open_claims_component_647727.htm&language=en_US&type=5)**  
    Show your Policyholder site users a snapshot of their open claims, and link them to additional information about the claims with the Insurance Open Claims component.
-   **[Mobile Insurance Open Claims Component](https://help.salesforce.com/s/articleView?id=ind.insurance_mobile_insurance_open_claims_component_647894.htm&language=en_US&type=5)**  
    Show your mobile Policyholder users a snapshot of their open claims, and link them to additional information about the claims with the Mobile Insurance Open Claims component.
-   **[Insurance Policy Claims Component](https://help.salesforce.com/s/articleView?id=ind.insurance_policy_claims_component_648060.htm&language=en_US&type=5)**  
    Show your Policyholder site users a snapshot of their open claims on a policy and link them to additional information about the claims with the Insurance Policy Claims component.
-   **[Insurance Policy Details Component](https://help.salesforce.com/s/articleView?id=ind.insurance_policy_details_component_648218.htm&language=en_US&type=5)**  
    Show your Policyholder site users details about insured items associated with their policy with the Insurance Policy Details component.
-   **[Insurance Policy Header Component](https://help.salesforce.com/s/articleView?id=ind.insurance_policy_header_component_648304.htm&language=en_US&type=5)**  
    Display the policy name and key policy data for your Policyholder Experience site users with the Insurance Policy Header Component.
-   **[Mobile Insurance Policy Header Component](https://help.salesforce.com/s/articleView?id=ind.insurance_t_mobile_insurance_policy_header_component_648386.htm&language=en_US&type=5)**  
    Display the policy name and key policy data for your mobile Policyholder site users with the Mobile Insurance Policy Header Component.
-   **[Insurance Policy List Component](https://help.salesforce.com/s/articleView?id=ind.insurance_policy_list_component_648476.htm&language=en_US&type=5)**  
    Show your Policyholder site users a list of insurance policies they have with the Insurance Policy List component. It's a container component that displays a label and a list of policies in the Insurance Policy List Child component.
-   **[Mobile Insurance Policy List Component](https://help.salesforce.com/s/articleView?id=ind.insurance_t_mobile_insurance_policy_list_component_648702.htm&language=en_US&type=5)**  
    Show your mobile Policyholder site users a list of insurance policies they have with the Mobile Insurance Policy List component. It's a container component that displays a label and a list of policies in the Mobile Insurance Policy List Child component.
-   **[Insurance Policy List Flyout Component](https://help.salesforce.com/s/articleView?id=ind.insurance_policy_list_flyout_component_648865.htm&language=en_US&type=5)**  
    Show your Policyholder site users a breakdown of the policy premium, taxes, and fees right on the policy list with the Insurance Policy List Flyout Component. The Insurance Policy List Flyout component is a child of the Insurance Policy List, Mobile Insurance Policy List, and Insurance Policy Details components.
-   **[Insurance Policy Overview Component](https://help.salesforce.com/s/articleView?id=ind.insurance_policy_overview_component_648926.htm&language=en_US&type=5)**  
    Show your Policyholder site users key information about their policy with the Insurance Policy Overview Component.
-   **[Insurance Policy Transaction Component](https://help.salesforce.com/s/articleView?id=ind.insurance_policy_transaction_component_649008.htm&language=en_US&type=5)**  
    Show your Policyholder site users recent transactions on their policy with the Insurance Policy Transaction component. It's a container component that displays a label and a list of transactions in the child component.
-   **[Insurance Recent Activity Component](https://help.salesforce.com/s/articleView?id=ind.insurance_recent_activity_component_649144.htm&language=en_US&type=5)**  
    Show your Policyholder site users a snapshot of the recent activity on their policies with the Insurance Recent Activity component.
-   **[Mobile Insurance Recent Activity Component](https://help.salesforce.com/s/articleView?id=ind.insurance_t_mobile_insurance_recent_activity_component_649287.htm&language=en_US&type=5)**  
    Show your mobile Policyholder site users a snapshot of the recent activity on their policies with the Mobile Insurance Recent Activity component.
-   **[Your Agent Component](https://help.salesforce.com/s/articleView?id=ind.insurance_your_agent_component_649428.htm&language=en_US&type=5)**  
    Your Policyholder site users can view details and contact their agent from the Your Agent component.

Did this article solve your issue?

Let us know so we can improve!

YesNo