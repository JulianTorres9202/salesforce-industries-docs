---
title: "Insurance Policy Lightning Web Components"
source: "https://help.salesforce.com/s/articleView?id=ind.insurance_insurance_policy_commercial_lightning_web_component_621400.htm&language=en_US&type=5"
scraped: "2026-04-14"
filter: "ind.insurance_"
---# Insurance Policy Lightning Web Components

Insurance Policy Lightning Web Components[](https://help.salesforce.com/s?language=en_US)

You are here:

1.  [Salesforce Help](/s/?language=en_US)
2.  [Docs](/s/products?language=en_US)
3.  [Digital Insurance](https://help.salesforce.com/s/articleView?id=ind.insurance_admin_standard.htm&language=en_US&type=5)

# Insurance Policy Lightning Web Components

Use the Insurance Policy Lightning web components to easily view and manage policies.

## Insurance Policy Lightning Web Component

The Policy UI Lightning web component runs attribute rules and attribute value rules, and then shows the details, coverages, and insured items that are available for any given policy.

The Policy UI Lightning web component also works with the Salesforce Financial Services Cloud version of the Insurance Policy object.

Note If the sharing settings for Policies are set to Controlled by Parent, then a user does not need Edit access to the Account object to update Policies. This sharing setting overrides other access restrictions to the Account object; the user can edit Policies even if they have Read Only access to Accounts. Read [Sharing Settings](https://help.salesforce.com/s/articleView?id=platform.managing_the_sharing_model.htm&language=en_US&type=5) to learn more about how sharing settings work.

[](https://help.salesforce.com/s?language=en_US)

## Compact Policy History Timeline with Insurance History Lightning Web Component

You can configure the Insurance History Lightning web component (LWC) to display a timeline of policy activity in a single, chronological feed that's easy to scan and drill into. See essential activity at a glance and expand content like notes and emails to dive into more detail.

[](https://help.salesforce.com/s?language=en_US)To learn more, see [Configure History Timelines with Insurance History LWC](https://help.salesforce.com/s/articleView?id=ind.insurance_configure_history_timelines_with_insurance_history_lwc.htm&language=en_US&type=5 "You can configure the Insurance History Lightning web component (LWC) to display a timeline of quote, claim, or policy activity in a single, chronological feed that's easy to scan and drill into. See essential activity at a glance and expand content like notes and emails to dive into more detail.").

Note

You can also configure history timelines for quote and claim activity. Your org includes a [DataPack for building a History tab for claims](https://help.salesforce.com/s/articleView?id=ind.insurance_configure_insurance_history_with_claim_history_lwc_datapack_620180.htm&language=en_US&type=5 "You can configure the Insurance History Lightning web component to create a cohesive view of all things happening with a claim. A DataPack included with your org gets you started. It has story object configuration that brings essential content into a Claim History tab out of the box.").

## Action Lightning Web Component

Vlocity has included three Actions out of the box: the **Issue Policy** and **Issue FSC Policy** buttons on the Quote record type and the **Modify Policy** button on the Policy (Asset) and Insurance Policy (FSC) record types. These are examples of [PubSub](https://help.salesforce.com/s/articleView?id=xcloud.os_firing_a_pubsub_event_from_an_action_on_an_lwc_card.htm&language=en_US&type=5) Actions.

You can also add custom Vlocity Actions to these Vlocity Cards layouts (**ins-quote-actions** contains the **Issue Policy** and **Issue FSC Policy** PubSub Actions and **ins-asset-actions** or **ins-insurance-policy-actions** contain the **Modify Policy** PubSub Action). To add custom actions, see [Adding a Custom Action to an LWC Card](https://help.salesforce.com/s/articleView?id=xcloud.os_adding_a_custom_action_to_an_lwc_card.htm&language=en_US&type=5).

## Insurance Policy Commercial Lightning Web Component

Commercial policies can have complex product structures with multiple levels of insured items. Each insured item can have its own set of coverages and coverage terms. A commercial policy can have coverages and ratings on parent, child, and grandchild insured items.

[](https://help.salesforce.com/s?language=en_US)The Insurance Policy Commercial Lightning web component is designed to help your users view complex policies and feature a side panel to view line item details. Buttons for common actions display prominently so your users can easily modify the policy or view the policy version history.

[](https://help.salesforce.com/s?language=en_US)Note

To make the Insurance Policy Commercial LWC available for your users, you must add it to the Insurance Policies page. Read [Lightning App Builder](https://help.salesforce.com/s/articleView?id=platform.lightning_app_builder_overview.htm&language=en_US&type=5) to learn about adding custom components to your lightning pages.

This component supports multi-root policies. Multi-root policies consist of a parent policy that is linked to multiple child policies. Users can view all child policies on the same UI and navigate to the individual policies by clicking the view policy button.

Tip

To make these buttons available to your users, select the **Show Actions** and **Show Modified Policy Button** options on the Insurance Policy Commercial LWC in the Lightning App Builder. Read [Create and Configure Lightning Experience Record Pages](https://help.salesforce.com/s/articleView?id=platform.lightning_app_builder_customize_lex_pages.htm&language=en_US&type=5) to learn how.

[](https://help.salesforce.com/s?language=en_US)Click the arrow next to a line item to expand and view information about the coverage in the side panel.

[](https://help.salesforce.com/s?language=en_US)On the Insurance Policy Commercial LWC, you can see:

[](https://help.salesforce.com/s?language=en_US)

-   Root insurance products
    
-   Coverages on the root insurance product
    
-   Total Premium
    
-   Total taxes and fees
    
-   [](https://help.salesforce.com/s?language=en_US)
    
    Premiums, attributes, and coverages for each insured item or grandchild insured item
    
-   [](https://help.salesforce.com/s?language=en_US)
    
    Taxes and fees on the premiums for each insured item or grandchild insured item
    

[](https://help.salesforce.com/s?language=en_US)

## See Also

-   [Commercial Quoting](https://help.salesforce.com/s/articleView?id=ind.insurance_commercial_quoting_613425.htm&language=en_US&type=5 "Easily configure, reprice, and navigate complex commercial quotes with multi-level insured item relationships and coverages.")
    
-   [Manage Insurance Policies](https://help.salesforce.com/s/articleView?id=ind.insurance_policy_administration_621128.htm&language=en_US&type=5 "Insurance Policy Administration extends throughout the lifecycle of an insurance policy. Any updates made to a policy during its term are managed through policy transactions.")
    
-   [Multi-Root Quoting](https://help.salesforce.com/s/articleView?id=ind.insurance_multi_root_quoting_613315.htm&language=en_US&type=5 "Configure, navigate, and reprice complex quotes with multi-level insured item relationships and coverages with Vlocity Insurance multi-root quoting.")
    

Did this article solve your issue?

Let us know so we can improve!

YesNo