---
title: "How the Process Commission Flow Works"
source: "https://help.salesforce.com/s/articleView?id=ind.insurance_brokerage_commission_statement_process_flow.htm&language=en_US&type=5"
scraped: "2026-04-13"
filter: "ind.insurance_"
---# How the Process Commission Flow Works

How the Process Commission Flow Works[](https://help.salesforce.com/s?language=en_US)

You are here:

1.  [Salesforce Help](/s/?language=en_US)
2.  [Docs](/s/products?language=en_US)
3.  [Digital Insurance](https://help.salesforce.com/s/articleView?id=ind.insurance_admin_standard.htm&language=en_US&type=5)

# How the Process Commission Flow Works

The Process Commission flow processes producer commissions by identifying the insurance policy, computing and creating producer commission records, and updating the status of the associated commission statement line item.

### Required Editions

<table class="slds-table slds-table_bordered slds-m-bottom_small edition" lwc-3eigj2skqo3=""><colgroup lwc-3eigj2skqo3=""><col style="width:100%" lwc-3eigj2skqo3=""></colgroup><tbody lwc-3eigj2skqo3=""><tr class="" lwc-3eigj2skqo3=""><td style="vertical-align:top;" class="slds-cell-wrap" lwc-3eigj2skqo3="">Available in: Lightning Experience</td></tr><tr class="" lwc-3eigj2skqo3=""><td style="vertical-align:top;" class="slds-cell-wrap" lwc-3eigj2skqo3="">Available in: <strong lwc-3eigj2skqo3="">Professional</strong>, <strong lwc-3eigj2skqo3="">Enterprise</strong>, and <strong lwc-3eigj2skqo3="">Unlimited</strong> Editions where Financial Service Cloud and Insurance Brokerage are enabled</td></tr></tbody></table>

## Find Insurance Policy

The process starts when the flow calls the Find Insurance Policy invocable action. The action finds the insurance policy associated with a commission statement line item that matches the specified criteria, and updates the commission statement line item record with the Policy ID.

The default value for matching criteria is shipped out of the box with the flow, and you can customize it according to your requirement.

```
InsurancePolicyNumber:PolicyName AND
InsurancePolicyEffectiveDate:EffectiveFromDate AND
LineOfCoverage:LineOfCoverage AND
ClientAccountName:NameInsured.Name
```

If the insurance policy isn’t found, then the status of the associated commission statement line item is set to a status that was mapped with the Failure system status of commission statement line item.

## Compute Producer Splits

The flow then calls the Compute Producer Split invocable action. The action begins with the retrieval of the active producer split assignment from the policy.

[](https://help.salesforce.com/s?language=en_US)Note A producer split assignment is considered active if the Apply to Date field in the commission statement line item falls between the effective date and end date of the producer split assignment.

The producer split arrangement is fetched from the producer split assignment. The system maps the split type of producer split arrangement line item with the commission type of the commission statement line item to determine the producer split arrangement model, and then processes the commission accordingly.

| Line item type | what the flow does |
| --- | --- |
| Explicit | Calculates producer commission by using the split percentage defined for each producer. |
| Role-based | Identifies producers assigned to the policy for each role and calculates producer commission by using the split percentage defined for each producer role. If the producer is identified as a team, then the flow initiates the team-based producer computation. |
| Team-based | Identifies team members and their associated split percentages and calculates producer commission based on the split percentages defined for the producer role and team members. |
| Subsequent | If the subsequent arrangement field is populated with a different split arrangement, the process continues to call the next producer split arrangement until all the split arrangement line items are resolved to either an explicit or role-based split record. |
| Book of Business Split Type | If the system finds a mapping between the commission type of commission statement line item and Broker Revenue Split Arrangement type, then the Producer Allocation Amountfield in the Producer Commission is populated with the Book of Business revenue credit after processing the commission. |

[](https://help.salesforce.com/s?language=en_US)Note The commission split arrangement sometimes contains line items for more than one type of commission, such as commission and bonus. In such a scenario, processing takes place for commission and bonus against the respective commission statement line items.

If the system can’t determine the producer split assignment, the commission statement line item status is set to a status that was mapped with the Failure system status of commission statement line item.

## Create Producer Commissions

Finally, the Create Producer Commissions invocable action creates records for the commissions that producers receive for the insurance policy associated with the specified commission statement line item, and updates the status of the commission statement line item record.

Did this article solve your issue?

Let us know so we can improve!

YesNo