---
title: "Record Summary Prompt Templates for Insurance"
source: "https://help.salesforce.com/s/articleView?id=ind.insurance_record_summary_prompt_templates_for_fsc_insurance.htm&language=en_US&type=5"
scraped: "2026-04-14"
filter: "ind.insurance_"
---# Record Summary Prompt Templates for Insurance

Record Summary Prompt Templates for Insurance[](https://help.salesforce.com/s?language=en_US)

You are here:

1.  [Salesforce Help](/s/?language=en_US)
2.  [Docs](/s/products?language=en_US)
3.  [Digital Insurance](https://help.salesforce.com/s/articleView?id=ind.insurance_admin_standard.htm&language=en_US&type=5)

# Record Summary Prompt Templates for Insurance

To generate summaries of Account, Insurance Policy, and Claim records, the Einstein Copilot for Insurance or Einstein Summary for Insurance uses record summary prompt templates.

The prompt templates are:

-   **Summarize Insurance Account**: Creates a plain text summary based on the Account record. The summary includes the account relationship, related insurance policies, and claims.
    
-   **Summarize Insurance Policy**: Creates a plain text summary based on the Insurance Policy record. The summary includes critical data such as coverage details, policy type, and renewal date.
    
-   **Summarize Insurance Claim**: Creates a plain text summary based on the Insurance Claim record. The summary includes critical data such as date of loss, current claim status, and description.
    

[Template-triggered prompt flows](https://help.salesforce.com/s/articleView?id=platform.flow_concepts_trigger_prompt_template_capability.htm&language=en_US&type=5) in the Prompt Builder provide data to these prompt templates.

These prompt flows are ready for use:

-   FSC Insurance GenAI: Summarize Insurance Account
    
-   FSC Insurance GenAI: Summarize Insurance Policy
    
-   FSC Insurance GenAI: Summarize Insurance Claims
    

To customize the available prompt templates, go to Prompt Builder, edit the template, and save it as a new template.

Note To avoid misleading results or hallucinations, deactivate the active template version before you activate the new version of the prompt template.

SEE ALSO

[Get to Know Prompt Builder](https://help.salesforce.com/s/articleView?id=ai.prompt_builder_get_to_know.htm&language=en_US&type=5)

[Set Up Einstein Generative AI](https://help.salesforce.com/s/articleView?id=ai.generative_ai_enable.htm&language=en_US&type=5)

[Enable Prompt Builder](https://help.salesforce.com/s/articleView?id=ai.prompt_builder_enable.htm&language=en_US&type=5)

[Use Multiple Versions of a Prompt Template](https://help.salesforce.com/s/articleView?id=ai.prompt_builder_use_multiple_versions.htm&language=en_US&type=5)

[Changing LLM Configurations](https://help.salesforce.com/s/articleView?id=ai.prompt_builder_changing_llm_configurations.htm&language=en_US&type=5)

[Activate and Deactivate Prompt Templates](https://help.salesforce.com/s/articleView?id=ai.prompt_builder_activate_deactivate_templates.htm&language=en_US&type=5)

Did this article solve your issue?

Let us know so we can improve!

YesNo