---
title: "Configuration Rule Action Types"
source: "https://help.salesforce.com/s/articleView?id=ind.insurance_admin_configuration_rule_action_types.htm&language=en_US&type=5"
scraped: "2026-04-13"
filter: "ind.insurance_"
---# Configuration Rule Action Types

Configuration Rule Action Types[](https://help.salesforce.com/s?language=en_US)

You are here:

1.  [Salesforce Help](/s/?language=en_US)
2.  [Docs](/s/products?language=en_US)
3.  [Digital Insurance](https://help.salesforce.com/s/articleView?id=ind.insurance_admin_standard.htm&language=en_US&type=5)

# Configuration Rule Action Types

Product Configurator supports different action types based on the condition criteria.

### Required Editions

<table class="slds-table slds-table_bordered slds-m-bottom_small edition" lwc-3eigj2skqo3=""><colgroup lwc-3eigj2skqo3=""><col style="width:100%" lwc-3eigj2skqo3=""></colgroup><tbody lwc-3eigj2skqo3=""><tr class="" lwc-3eigj2skqo3=""><td style="vertical-align:top;" class="slds-cell-wrap" lwc-3eigj2skqo3="">Available in: Lightning Experience</td></tr><tr class="" lwc-3eigj2skqo3=""><td style="vertical-align:top;" class="slds-cell-wrap" lwc-3eigj2skqo3="">Available in: <strong lwc-3eigj2skqo3="">Enterprise</strong>, <strong lwc-3eigj2skqo3="">Unlimited</strong>, and <strong lwc-3eigj2skqo3="">Developer</strong> Editions of Digital Insurance Platform where Product Configurator is enabled with the Revenue Lifecycle Management add-on</td></tr></tbody></table>

[](https://help.salesforce.com/s?language=en_US)

## Product Rules

Define conditions that determine how products and coverage options are configured based on specific criteria.

Action Types
| Action Type | Description | Example |
| --- | --- | --- |
| Auto-Add | Automatically add a product to the bundle when the rule evaluates to true. | If users select the Collision coverage, add the Roadside Assistance coverage to the quote. |
| Auto-Remove | Automatically remove a product from the bundle when the rule evaluates to true. | If users select the Comprehensive coverage, remove the Roadside Assistance coverage from the quote. |
| Hide Product | Hide the product option from the product catalog when the rule evaluates to true. | If the applicant's age is under 25 years, hide the Senior Health Plan coverage. |
| Disable Product | Disable the product option from the product catalog when the rule evaluates to true. | If the coverage type is Liability Only, then disable the Roadside Assistance option. |
| Set Default Product | Automatically add a default product to the bundle when the rule evaluates to true. Users can deselect the default product. | If users select the Comprehensive coverage, add the Accident coverage by default. |
| Validate | Make sure that a product and its attributes are correctly configured by showing a validation message to the user. | If the Make is Tesla, the Year is earlier than 2014, and the Comprehensive Deductible is less than $500, show the message: "Tesla cars older than 10 years must have a Comprehensive Coverage deductible of $500 or more.” |
| Require | Make sure that users include a product along with its attributes by showing a validation message to the user. | If the user selects Comprehensive coverage in the Auto Gold bundle without Collision Deductible Waiver, show the message: "Select Collision Deductible Waiver with Comprehensive coverage." |
| Exclude | Exclude a product along with its attributes by showing a validation message to the user. | If the user selects Comprehensive Coverage and tries to add Towing Service, show the message: “Towing Service is not available with Comprehensive Coverage.” |

[](https://help.salesforce.com/s?language=en_US)

## Attribute Rules

Show users and customers the specific product attributes that are applicable to them for the insurance products that you quote, sell, and service. Attribute rules apply to the whole attribute. To create rules for specific attribute values, use Attribute Value Rules instead.

Action Types
| Action Type | Description | Example |
| --- | --- | --- |
| Set Attribute | Set one or more attributes of a product to the appropriate value. Users can't override a value set by this rule. | If Collision coverage BI Person Limit is greater than $10000, then set Collision coverage Deductible as $500. |
| Set Default Attribute Value | Set one or more attributes of a product to the appropriate value. Users can change this value when going through a quote or policy flow. |
| Hide Attribute | Hide the attribute from the product when the rule evaluates to true. | If the coverage type is Third-Party Liability Only, then hide the Collision Deductible attribute. |
| Disable Attribute | Disable the attribute from the product when the rule evaluates to true. | If the coverage type is Comprehensive Coverage, disable the Third-Party Liability Limit attribute. |

Note The Set Attribute and Set Default Attribute Value actions don't apply to extended attributes because their values are read-only and sourced from related records.

[](https://help.salesforce.com/s?language=en_US)

## Attribute Value Rules

Show your users and customers the specific product attribute values that are applicable to them. Attribute value rules are only applicable for attributes that have multiple discrete values, for example currency and text dropdown lists. Attribute Value Rules apply to specific values of an attribute. Supported action types:

Action Types
| Action Type | Description | Example |
| --- | --- | --- |
| Hide Attribute Value | Hide one or more attribute values from the product when the rule evaluates to true. These rules apply only to picklist attributes, such as currency and text dropdowns. | If Driver Accident Points are greater than 5, hide the "Safe" value in Driver Rating. |
| Disable Attribute Value | Disable one or more attribute values from the product when the rule evaluates to true. | If the Vehicle Age is greater than 10 years, disable the "Premium" value in Coverage Level. |

[](https://help.salesforce.com/s?language=en_US)

## User Profile-Based Rules

User profile-based rules define conditions that adjust product configurations based on the user's role or profile. These rules make sure that different users, such as agents or customer service representatives, see and interact with only the product attributes and options that are tailored to their specific needs.

Action Types
| Action Type | Description | Example |
| --- | --- | --- |
| Profile-Based Set Attribute Value | Show users unique product attribute values based on their user profile. | If a customer service representative creates a travel insurance quote, set the luggage loss coverage limit to $250. If a sales representative creates a quote, set the same coverage limit to $500. |
| Profile-Based Hide Attribute | Hide product attributes from specific user profiles. | If an insurance representative creates an auto insurance quote, hide the Rental Car Limit attribute. |

Did this article solve your issue?

Let us know so we can improve!

YesNo