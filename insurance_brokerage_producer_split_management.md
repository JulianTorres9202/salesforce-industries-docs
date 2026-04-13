---
title: "Producer Split Management"
source: "https://help.salesforce.com/s/articleView?id=ind.insurance_brokerage_producer_split_management.htm&language=en_US&type=5"
scraped: "2026-04-13"
filter: "ind.insurance_"
---# Producer Split Management

Producer Split Management[](https://help.salesforce.com/s?language=en_US)

You are here:

1.  [Salesforce Help](/s/?language=en_US)
2.  [Docs](/s/products?language=en_US)
3.  [Digital Insurance](https://help.salesforce.com/s/articleView?id=ind.insurance_admin_standard.htm&language=en_US&type=5)

# Producer Split Management

Producer splits refer to the distribution of commission or earnings among multiple producers or salespeople involved in a single sale or policy. Store and maintain producer splits to use them in commission processing.

### Required Editions

<table class="slds-table slds-table_bordered slds-m-bottom_small edition" lwc-3eigj2skqo3=""><colgroup lwc-3eigj2skqo3=""><col style="width:100%" lwc-3eigj2skqo3=""></colgroup><tbody lwc-3eigj2skqo3=""><tr class="" lwc-3eigj2skqo3=""><td style="vertical-align:top;" class="slds-cell-wrap" lwc-3eigj2skqo3="">Available in: Lightning Experience</td></tr><tr class="" lwc-3eigj2skqo3=""><td style="vertical-align:top;" class="slds-cell-wrap" lwc-3eigj2skqo3="">Available in: <strong lwc-3eigj2skqo3="">Professional</strong>, <strong lwc-3eigj2skqo3="">Enterprise</strong>, and <strong lwc-3eigj2skqo3="">Unlimited</strong> Editions where Financial Service Cloud and Insurance Brokerage are enabled</td></tr></tbody></table>

## Managing Producer Splits

You can define splits by explicitly naming the producers or by using a role-based approach. It’s important to have a clear and easily managed set of splits that suit your business needs.

[](https://help.salesforce.com/s?language=en_US)

## Explicit Producer Split Arrangement Definitions

In certain situations, it’s beneficial to have a producer split arrangement assigned to an insurance policy where each producer is explicitly named with their respective percentages.

Example

The producer split arrangement has line items that are assigned to John and Bill. When this arrangement is used on an insurance policy, ‌producers get 40% and 30%, respectively.

| Line Item | type | producer | percentage |
| --- | --- | --- | --- |
| ProducerSplitArrangementLineItem.Type | Commission | John | 40% |
| ProducerSplitArrangementLineItem.Type | Commission | Bill | 30% |
| ProducerSplitArrangementLineItem.Type | Commission | House | 30% |
| ProducerSplitArrangementLineItem.Type | Bonus | House | 100% |

[](https://help.salesforce.com/s?language=en_US)

## Producer Role Split Arrangement Definitions

In situations where the same percentages are used across multiple producers, split arrangement can become cumbersome because it requires creating a producer split arrangement record for every combination of producers, leading to a large number of permutations. In such cases, it’s efficient to use a role-based definition. With this approach, the producer split arrangement specifies the role that receives a percentage. This role-based producer split arrangement works alongside a separate producer split role assignment definition on an insurance policy to indicate which Producer ID is assigned to a role on the Insurance Policy record.

Example

The producer split arrangement has line items that are assigned to primary and secondary producer roles. When paired with a producer split role assignment record on an insurance policy that designates John as the Primary and Bill as the Secondary, these two producers receive 40% and 30% respectively.

| line item | type | producer role | percentage |
| --- | --- | --- | --- |
| ProducerSplitArrangementLineItem.Type | Commission | Primary | 40% |
| ProducerSplitArrangementLineItem.Type | Commission | Secondary | 30% |
| ProducerSplitArrangementLineItem.Type | Commission | House | 30% |
| ProducerSplitArrangementLineItem.Type | Bonus | House | 100% |

[](https://help.salesforce.com/s?language=en_US)

## Subsequent Producer Split Arrangements

If you want to further split the arrangement line item, provide the subsequent producer split arrangement in the Subsequent Producer Split Arrangement field when you create a producer arrangement line item. In this scenario, the producer split arrangement line item serves as a pass-through to another producer split arrangement record during processing. This technique is efficient for data organization practices and is an optional way to structure split assignments.

Example

Consider a scenario where a producer split arrangement line is 40% and the subsequent producer split arrangement is populated with an 80% split for the primary producer and a 20% split for the secondary producer. If a $1000 commission statement is being processed, $400 would be passed from the producer split arrangement line (40%) to the subsequent producer split arrangement. Then, the primary producer receives $320, which is 80% of $400, and the secondary producer receives $80, which is 20% of $400.

[](https://help.salesforce.com/s?language=en_US)

## Producer Team Split Definitions

Producers sometimes have a team or multiple teams with whom they share a portion of their commissions. In this scenario, each producer team is defined as a producer record. The producer and the team members are linked through the ProducerRelatedProducer functionality. In this setup, the team record is managed as a record in the producer role-based split and explicit split sections. Additional splitting is then applied through the ProducerRelatedProducer associations.

Example

Insurance Policy A - Producer shares commission with team:

[](https://help.salesforce.com/s?language=en_US)

-   Commissions statement line item is $1000
-   John gets $700 and Sally $300 as producers
-   John then gives $140 to Billy and $70 to Tom

-   **[Producer Split Arrangement and Line Items](https://help.salesforce.com/s/articleView?id=ind.insurance_brokerage_producer_split_arrangement_line_items.htm&language=en_US&type=5#insurance_brokerage_producer_split_arrangement_line_items)**  
    Create a producer split arrangement record and line items to define the percentage of split allocated to each producer, and then associate it with an account or insurance policy. This applies to explicit producer split arrangement definitions, producer role split arrangement definitions, and subsequent producer split arrangements.
-   **[Producer Role Assignments](https://help.salesforce.com/s/articleView?id=ind.insurance_brokerage_producer_split_assignments_overview.htm&language=en_US&type=5)**  
    Assign or reassign the producer role at account level and then inherit it to the policy for easy maintenance. Update the producer role for multiple accounts or policies in one go. The producer role assignment is applicable only when you use producer role split arrangement definitions.
-   **[Producer Split Assignment](https://help.salesforce.com/s/articleView?id=ind.insurance_brokerage_producer_split_assignments.htm&language=en_US&type=5)**  
    Assign producer split arrangements at the account level and inherit them to the child policies for easy maintenance. Producer split assignment is applicable to only explicit producer split arrangement definitions and producer role split definitions.

Did this article solve your issue?

Let us know so we can improve!

YesNo