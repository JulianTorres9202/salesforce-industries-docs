---
title: "Data Model Updates for Insurance Spring '21"
source: "https://help.salesforce.com/s/articleView?id=ind.insurance_data_model_updates_for_insurance_spring__21.htm&language=en_US&type=5"
scraped: "2026-04-14"
filter: "ind.insurance_"
---# Data Model Updates for Insurance Spring '21

Data Model Updates for Insurance Spring '21[](https://help.salesforce.com/s?language=en_US)

You are here:

1.  [Salesforce Help](/s/?language=en_US)
2.  [Docs](/s/products?language=en_US)
3.  [Digital Insurance](https://help.salesforce.com/s/articleView?id=ind.insurance_admin_standard.htm&language=en_US&type=5)

# Data Model Updates for Insurance Spring '21

These are the data model updates for this release.

[](https://help.salesforce.com/s?language=en_US)

## New Data Model Objects

We added these objects to the data model for this release:

| 
New Object

 | 

Description

 |
| --- | --- |
| 

Cached Data Set

 | 

This object is used to group records in caching objects, such as the Datastore, and control the activation of the group using the IsActive flag.

This object includes the following fields:

-   CachedDataSet Name
    
-   Is Active: Indicates if the cached data set is active.
    

 |
| --- | --- |
| 

Contract Group

 | 

This object represents a collection of service points or service accounts.

This object includes the following fields:

-   Contract
    
-   Quote Group
    

 |
| --- | --- |
| 

Generic DocuSign Document

 | 

[](https://help.salesforce.com/s?language=en_US)This object provides information about the documents attached in a DocuSign eSignature envelope.

[](https://help.salesforce.com/s?language=en_US)This object includes the following fields:

[](https://help.salesforce.com/s?language=en_US)

-   Document Identifier: A document identifier within a DocuSign envelope.
    
-   Document Name
    
-   Document Source Id: SObject Id where the document was sourced.
    
-   Document Source Type: SObject where the document was sourced.
    
-   Generic Envelope
    
-   Envelope Identifier
    
-   File Extension: File extension of the document that was sourced.
    

 |
| --- | --- |
| 

Generic DocuSign Envelope

 | 

This object stores information about DocuSign envelopes.

This object includes the following fields:

[](https://help.salesforce.com/s?language=en_US)

-   Completed Date: Date the envelope was completed.
    
-   Declined Date
    
-   Email Message: Message sent to the recipient.
    
-   Email Subject
    
-   Envelope Identifier
    
-   Envelope Uri
    
-   Last Poll Date
    
-   Opportunity
    
-   Order
    
-   Quote
    
-   Sent Date
    
-   Status
    
-   Status Date: Date the envelope status was updated.
    
-   Viewed Date
    
-   Voided Date
    
-   Voided Reason
    

 |
| --- | --- |
| 

Generic DocuSign Recipient

 | 

This object provides information about the status of each recipient in a DocuSign eSignature envelope.

This object includes the following fields:

[](https://help.salesforce.com/s?language=en_US)

-   Access Code: This optional element specifies the access code a recipient has to enter to validate their identity.
    
-   Contact
    
-   Date Declined
    
-   Date Delivered
    
-   Date Sent
    
-   Date Signed
    
-   Decline Reason
    
-   Delivery Method
    
-   Generic Envelope
    
-   Envelope Identifier
    
-   Host Email: This is used for recipients that sign in-person.
    
-   Language
    
-   Recipient Name
    
-   Recipient Id
    
-   Routing Order
    
-   Signer Name
    
-   Status
    
-   Type
    

 |
| --- | --- |
| 

Opportunity Group

 | 

This object represents a collection of service points, service accounts, or any other grouping object.

This object includes the following fields:

[](https://help.salesforce.com/s?language=en_US)

-   Async Job: Stores the asynchronous job ID of any jobs running on this group.
    
-   Async Operation: Stores the asynchronous operation name of the group when it is locked for asynchronous operation.
    
-   Description
    
-   Expected Member Count
    
-   Group Cart: Reference to group cart or associate cart.
    
-   Has Unapplied Group Items
    
-   Locked By User: Indicates if an opportunity group is locked by a user.
    
-   Locked For: Reason for locking the opportunity group.
    
-   Member Count
    
-   Member Type: Stores developer name of CPQ Member Type custom metadata.
    
-   Multi Service Message Data: Stores messages that are generated and displayed in a MultiService feature.
    
-   Group One Time Cost Total: Final one-time cost total of all individual group items.
    
-   One Time Margin Total
    
-   Group One Time Total: Final one-time total of all individual group items.
    
-   Opportunity Group Margin Total
    
-   Opportunity
    
-   Group Recurring Cost Total: Final total of the recurring cost of all individual group items.
    
-   Recurring Margin Total
    
-   Group Recurring Total: Final recurring total of all individual group items.
    
-   Group Usage Cost Total: Final usage cost total of all individual group items.
    
-   Usage Margin Total
    
-   Group Usage Price Total: Final usage price total of all individual group items.
    

 |
| --- | --- |
| 

Order Group

 | 

This object represents a collection of service points or service accounts.

This object includes the following fields:

[](https://help.salesforce.com/s?language=en_US)

-   Async Job: Stores the asynchronous job ID of any jobs running on this group.
    
-   Async Operation: Stores the asynchronous operation name of the group when it is locked for asynchronous operation.
    
-   Description
    
-   Expected Member Count
    
-   Group Cart: Reference to group cart or associate cart.
    
-   Has Unapplied Group Items
    
-   Locked By User: Indicates if an opportunity group is locked by a user.
    
-   Locked For: Reason for locking the opportunity group.
    
-   Member Count
    
-   Member Type: Stores developer name of CPQ Member Type custom metadata.
    
-   Multi Service Message Data: Stores messages that are generated and displayed in a MultiService feature.
    
-   Group One Time Cost Total: Final one-time cost total of all individual group items.
    
-   One Time Margin Total
    
-   Group One Time Total: Final one-time total of all individual group items.
    
-   Order Group Margin Total
    
-   Order
    
-   Quote Group: Corresponding Quote Group from which this record is created.
    
-   Group Recurring Cost Total: Final total of the recurring cost of all individual group items.
    
-   Recurring Margin Total
    
-   Group Recurring Total: Final recurring total of all individual group items.
    
-   Group Usage Cost Total: Final usage cost total of all individual group items.
    
-   Usage Margin Total
    
-   Group Usage Price Total: Final usage price total of all individual group items.
    

 |
| --- | --- |
| 

Quote Group

 | 

A quote group can be a collection of service points or service accounts.

This object includes the following fields:

[](https://help.salesforce.com/s?language=en_US)

-   Async Job: Stores the asynchronous job ID of any jobs running on this group.
    
-   Async Operation: Stores the asynchronous operation name of the group when it is locked for asynchronous operation.
    
-   Description
    
-   Expected Member Count
    
-   Group Cart: Reference to group cart or associate cart.
    
-   Has Unapplied Group Items
    
-   Locked By User: Indicates if an opportunity group is locked by a user.
    
-   Locked For: Reason for locking the opportunity group.
    
-   Member Count
    
-   Member Type: Stores developer name of CPQ Member Type custom metadata.
    
-   Multi Service Message Data: Stores messages that are generated and displayed in a MultiService feature.
    
-   Group One Time Cost Total: Final one-time cost total of all individual group items.
    
-   One Time Margin Total
    
-   Group One Time Total: Final one-time total of all individual group items.
    
-   Quote
    
-   Quote Group Margin Total
    
-   Group Recurring Cost Total: Final total of the recurring cost of all individual group items.
    
-   Recurring Margin Total
    
-   Group Recurring Total: Final recurring total of all individual group items.
    
-   Group Usage Cost Total: Final usage cost total of all individual group items.
    
-   Usage Margin Total
    
-   Group Usage Price Total: Final usage price total of all individual group items.
    

 |
| 

Vlocity Contract Service Log

 | 

This object contains information about contract service requests made.

[](https://help.salesforce.com/s?language=en_US)This object includes the following fields:

-   Context Id
    
-   Context Type
    
-   DateTime Accepted
    
-   DateTime Completed
    
-   DateTime Started
    
-   Job Type
    
-   Request Data
    
-   Response Data
    
-   Service Type
    
-   Status
    
-   User Id
    

 |

[](https://help.salesforce.com/s?language=en_US)

## Enhanced Data Model Objects

We added fields and made other enhancements to the following objects for this release:

| 
Enhanced Object

 | 

What's Changed

 |
| --- | --- |
| 

Asset

 | 

This object includes the following fields:

-   Product Group Key
    
-   Product Hierarchy Group Key Path: Stores the result string obtained by replacing every Product Id in the Product Hierarchy Path with its Version Group key.
    

 |
| --- | --- |
| 

Vlocity Attribute

 | 

This object represents the definition of an attribute which can be used to profile, describe or configure items tracked in the database.

This object includes the following field:

-   Exclude From Basket Cache: Indicates if a product attribute should be excluded from the Basket Cache Key. When this field is set to false, the attribute is included while generating the Basket Cache Key.
    

 |
| --- | --- |
| 

Catalog Product Relationship

 | 

This object includes the following field:

-   Product Group Key: Version group key of the product.
    

 |
| --- | --- |
| 

Contract

 | 

This object includes the following fields:

-   Contract Group
    
-   Last DocuSign Envelope Id
    
-   Last DocuSign Envelope Status
    
-   Last DocuSign Job Id
    

 |
| --- | --- |
| 

Contract Document

 | 

This object represents an online version of a contract document. A contract document can have physical files, like Word or PDF files, attached to it.

[](https://help.salesforce.com/s?language=en_US)This object includes the following fields:

-   Contains Reconcile Redlines: Indicates if the contract reconcile section contains at least one redline.
    
-   Count Of Contains Reconcile Redlines: Total count of sections that contain redlines in the document version.
    
-   Is Section Info Stored On Doc: Indicates whether the Section Id information is populated on the document generated through Docx Templates.
    

 |
| --- | --- |
| 

Contract Document Section

 | 

This object contains details about each section of a generated contract document.

[](https://help.salesforce.com/s?language=en_US)This object includes the following fields:

-   Contains Reconcile Redlines: Indicates if the contract reconcile section contains at least one redline.
    
-   Remove Line After Section: If checked, a new line is not added after the section.
    

 |
| --- | --- |
| 

Customer Interaction Topic

 | 

This object captures data discussed or addressed during a customer interaction such as a customer account, a customer asset, a quote, or a case. This object could even be a specific field or aspect of an object such as a charge on a bill or a co-pay on a health insurance coverage.

This object includes the following fields:

-   Outcome: Captures the end result of the customer interaction topic.
    
-   Process Name: Captures the guided process that has created the customer interaction topic.
    
-   Reason: Captures the reason of the outcome.
    
-   Subscription: Records the subscription ID related to the customer interaction topic.
    

 |
| --- | --- |
| 

Vlocity Data Store

 | 

This object is to be used as a persistent cache.

This object includes the following field:

-   Cached Data Set: Identifies a Cached Data Set entry.
    

 |
| --- | --- |
| 

Document

 | 

This object includes the following field:

-   Document Source Id
    

 |
| 

Document Section

 | 

This object includes the following field:

-   Remove Line After Section: If checked, a new line is not added after the section.
    

 |
| 

Document Template

 | 

This object includes the following field:

-   [](https://help.salesforce.com/s?language=en_US)
    
    Is Section Ids Replaced: If checked, indicates that the DOCX contract boundary sections have been processed.
    

 |
| 

Document Template Section

 | 

[](https://help.salesforce.com/s?language=en_US)This object includes the following field:

-   Remove Line After Section: If checked, a new line is not added after the section.
    

 |
| 

Docusign Envelope Object Limits

 | 

[](https://help.salesforce.com/s?language=en_US)This object includes the following field:

-   Setup Value
    

 |
| 

Docusign Envelope Object Setting

 | 

This object includes the following fields:

-   Docusign Account Brand
    
-   Docusign Expire After
    
-   DocuSign Expire Enabled
    
-   DocuSign Expire Warn
    
-   DocuSign Reminder Delay
    
-   DocuSign Reminder Frequency
    
-   DocuSign Reminder Enabled
    
-   DocuSign Use Account Default Notification
    

 |
| 

Vlocity OmniScript

 | 

This object includes the following field:

-   Omni Process Type: Indicates the type of Omni Process - OmniScript, Integration Procedure, or Test Procedure.
    

 |
| 

Saved OmniScript

 | 

This object includes the following field:

-   Custom Status
    

 |
| 

Opportunity Product

 | 

[](https://help.salesforce.com/s?language=en_US)This object includes the following fields:

-   Product Group Key: Version Group Key of Product.
    
-   Product Hierarchy Group Key Path: Stores the string resulting from replacing every Product Id in the Product Hierarchy Path with its Version Group key.
    

 |
| 

Order

 | 

[](https://help.salesforce.com/s?language=en_US)This object includes the following fields:

-   First Submitted Date: Date of first submission to order management.
    
-   Multi Service Message Data: Stores messages that are generated and displayed in a MultiService feature.
    
-   Queued Timestamp: Timestamp when order submission is queued.
    

 |
| 

Order Product

 | 

[](https://help.salesforce.com/s?language=en_US)This object includes the following fields:

[](https://help.salesforce.com/s?language=en_US)

-   Product Group Key: Version Group Key of Product.
    
-   Product Hierarchy Group Key Path: Stores the string resulting from replacing every Product Id in the Product Hierarchy Path with its Version Group key.
    

 |
| 

Product Override Definition

 | 

This object identifies an overriding product child item or attribute assignment.

[](https://help.salesforce.com/s?language=en_US)This object includes the following fields:

[](https://help.salesforce.com/s?language=en_US)

-   Product Group Key: Version Group Key of Product.
    
-   Product Hierarchy Group Key Path: Stores the string resulting from replacing every Product Id in the Product Hierarchy Path with its Version Group key.
    
-   Promotion Item Group Key: Global group key of the promotion item.
    

 |
| 

Product

 | 

[](https://help.salesforce.com/s?language=en_US)This object includes the following fields:

-   Object Type Name
    
-   Specification Type Name
    

 |
| 

Product Child Item

 | 

This object represents relationships between the parent insurance product (such as plan types and policy types) and its child component specifications including coverages, insured parties and insured items.

[](https://help.salesforce.com/s?language=en_US)This object includes the following fields:

-   Child Product Name
    
-   Parent Product Name
    

 |
| 

Product Configuration Procedure

 | 

This object acts on attributes to hide them, disable them, require a value for them, assign a specific value to them or constrain the available choices for them.

[](https://help.salesforce.com/s?language=en_US)This object includes the following field:

-   Product Group Key: Version group key of product.
    

 |
| 

Product Relationship

 | 

This object represents relationships between two insurance products and their child components that defines the optional coverage specifications for a policy.

[](https://help.salesforce.com/s?language=en_US)This object includes the following fields:

[](https://help.salesforce.com/s?language=en_US)

-   Product Group Key: Version group key of product.
    
-   Related Product Group Key
    

 |
| 

Project Item

 | 

[](https://help.salesforce.com/s?language=en_US)This object includes the following fields:

-   Action
    
-   Root Item: Salesforce Id of the root project item under which this project item belongs.
    

 |
| 

Promotion

 | 

This object stores the definition of promotional pricing that can be made available to customers.

[](https://help.salesforce.com/s?language=en_US)This object includes the following fields:

-   Cpq Engine Hints: Defines configurations used in the CPQ Engine and Digital Commerce.
    

 |
| 

Promotion Item

 | 

This object represents the product or service that is applicable or automatically included for promotions.

[](https://help.salesforce.com/s?language=en_US)This object includes the following fields:

-   Context Product Group Key
    

 |
| 

Quote

 | 

[](https://help.salesforce.com/s?language=en_US)This object includes the following fields:

-   Parent Quote: Indicates if the quote has a parent quote. Parent quote here also refers to a master quote.
    
-   Quote Group: The group to which the service point associated with this quote is linked.
    

 |
| 

Quote Line Item

 | 

[](https://help.salesforce.com/s?language=en_US)This object includes the following fields:

[](https://help.salesforce.com/s?language=en_US)

-   Product Group Key: Version group key of product.
    
-   Product Hierarchy Group Key Path: Stores the string resulting from replacing every Product Id in the Product Hierarchy Path with its Version Group key.
    

 |
| 

Subscription

 | 

[](https://help.salesforce.com/s?language=en_US)This object includes the following fields:

-   Old MSISDN: Stores the previous phone number of the Subscription.
    
-   Service Identifier: Unique identifier of the service used by the customer.
    

 |
| 

Trailing Document Placeholder

 | 

This object tracks documents that are needed to make decisions about insurance related processes. For example, an application for life insurance may require one or more medical tests whose results must be submitted before underwriting can proceed. Trailing document placeholders can be tracked for quotes, applications, policies, claims or cases.

This object includes the following fields:

-   Involved Property
    
-   Involved Injury
    

 |
| 

Vlocity Attachment

 | 

This object represents a link to content that is either stored as an attachment in Salesforce or as web content in any URL-addressable content store.

[](https://help.salesforce.com/s?language=en_US)This object includes the following fields:

[](https://help.salesforce.com/s?language=en_US)

-   Product Group Key: Version group key of product.
    

 |

We added descriptions to these fields:

| 
Object

 | 

Description

 |
| --- | --- |
| 

Vlocity Action

 | 

[](https://help.salesforce.com/s?language=en_US)This object includes the following fields:

-   Execution Sequence: Determines the order in which Vlocity Actions are executed during a state transition.
    
-   Invocation Method Input: Input parameter that is passed on toInvokeMethodName\_\_c at runtime.
    
-   IsStateDefaultAction: Indicates if this is a default action. During a state transition, by default, only default actions are executed.
    
-   Vlocity State Model Version: The Vlocity State Model Version to which this Vlocity Action is specific.
    

 |
| 

Vlocity State Model Version

 | 

[](https://help.salesforce.com/s?language=en_US)This object includes the following fields:

-   Additional Objects: Write conditions and the relationship field to StateModel\_\_c.ObjectAPIName\_\_c. This is used to pull data from the parent to all applicable child objects.
    
-   On Creation Action: The action executed when an object record for which the state model is set up gets created.
    
-   Rule Evaluation Class Name: The custom Apex class for evaluating Vlocity State Transition Rules.
    
-   Rule Evaluation Method Name: The method in the custom Apex class for evaluating Vlocity State Transition Rules.
    

 |
| 

Vlocity State Transition

 | 

This object represents a state transition allowed within a given version of a Vlocity State Model. Master-detail child object of Vlocity State Model Version.

[](https://help.salesforce.com/s?language=en_US)This object includes the following fields:

[](https://help.salesforce.com/s?language=en_US)

-   Alternate: A state to which an object transitions if the state transition criteria is not met and the primary state transition is unsuccessful.
    
-   Default Transition: Indicates if ToState is the default transition from the FromState.
    
-   State Transition Completion Criteria: Determines when the state transition happens. For example, when the mode is set to AllTrue, the transition is affected only when all rules defined for the transition pass.
    

 |
| 

Vlocity State Transition Rule

 | 

This object stores the rules configured to be executed on an object state transition and the actions that get executed when the rules evaluate to true.

[](https://help.salesforce.com/s?language=en_US)This object includes the following fields:

-   Active: Indicates if the rule is active.
    
-   Conditions: Describes rule conditions.
    
-   Execution Sequence: The rule execution sequence.
    
-   False Action: This is an optional action associated with the rule. If rule evaluation is false, this action is executed.
    
-   True Action: This is an optional action associated with the rule. If rule evaluation is true, this action is executed.
    

 |

Did this article solve your issue?

Let us know so we can improve!

YesNo