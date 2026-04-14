---
title: "Contract Business Process"
source: "https://help.salesforce.com/s/articleView?id=ind.insurance_contract_business_process_omnistudio.htm&language=en_US&type=5"
scraped: "2026-04-14"
filter: "ind.insurance_"
---# Contract Business Process

Contract Business Process[](https://help.salesforce.com/s?language=en_US)

You are here:

1.  [Salesforce Help](/s/?language=en_US)
2.  [Docs](/s/products?language=en_US)
3.  [Digital Insurance](https://help.salesforce.com/s/articleView?id=ind.insurance_admin_standard.htm&language=en_US&type=5)

# Contract Business Process

After you've created a quote, you will likely want to create a contract to clearly define the services the group will get. This section tells you how to create a contract from your quote with just one click!

You can create a contract through the:

[](https://help.salesforce.com/s?language=en_US)

-   [OmniScript flow](https://help.salesforce.com/s/articleView?id=ind.insurance_contract_business_process_omnistudio.htm&language=en_US&type=5 "After you've created a quote, you will likely want to create a contract to clearly define the services the group will get. This section tells you how to create a contract from your quote with just one click!")
    
-   [Quote UI](https://help.salesforce.com/s/articleView?id=ind.insurance_contracts_using_the_quote_ui_omnistudio.htm&language=en_US&type=5 "You can create a contract using the quote UI, which is built with Lightning Web Components.")
    

Depending on your role, you can create contracts from different parts of the application:

| 
Role

 | 

Create a Contract from

 |
| --- | --- |
| 

Internal insurance agent

 | 

Quote UI

Vlocity Admin Lighting Experience

 |
| 

Vlocity Admin

 | 

Vlocity Admin Lighting Experience

 |

[](https://help.salesforce.com/s?language=en_US)

## Contracts Using the OmniScript Flow

If you are a Vlocity admin, you can find the Contract Creation OmniScript in the Vlocity OmniScript Designer under:

-   Type - InsGVB
    
-   SubType - CreateContract
    
-   OmniScript Name - Create Contract
    

The OmniScript starts off by asking users to review group information.

That's actually all that users need to do. The OmniScript generates the proposal document.

[](https://help.salesforce.com/s?language=en_US)

## How Does It Work?

Is it magic? Is it voodoo? No, it's our OmniScript!

| 
Component Name

 | 

Component Type

 | 

What It Does

 | 

What It Calls

 |
| --- | --- | --- | --- |
| 

getQuoteDetails

 | 

Omnistudio Data Mapper Extract Action

 | 

Retrieves the quote details

 | 

None

 |
| 

getAccountDetails

 | 

Data Mapper Extract Action

 | 

Retrieves the quote ID and the account ID

 | 

Ins\_ReadAccountDetails\_CreateContractOS

 |
| 

setContractStatus

 | 

Set Values

 | 

Sets the contract status as Draft

 | 

None

 |
| 

setaccountId

 | 

Set Values

 | 

Set the account ID

 | 

None

 |
| 

setContractTerm

 | 

Set Values

 | 

Sets the time period for which the contract is valid

 | 

None

 |
| 

EmployerInformation

 | 

Step comprising multiple blocks

 | 

Displays the group information, billing information and contract dates for the quote

 | 

None

 |
| 

setProposalValues

 | 

Set Values

 | 

Sets the contract title

 | 

None

 |
| 

createContractAndCensusIp

 | 

Integation Procedure

 | 

Sets the enrollment census ID and creates a contract ID

 | 

InsCreateContractAndCensusIP

 |
| 

ContractProposal1

 | 

OmniScript

 | 

Generates the proposal

 | 

InsGVB/ContractProposal

 |

[](https://help.salesforce.com/s?language=en_US)

## What's Next?

Members can now enroll themselves in the plans you've selected. For instructions on how to go about it, see the [Enrollment Business Process](https://help.salesforce.com/s/articleView?id=ind.insurance_member_enrollment_business_process_omnistudio.htm&language=en_US&type=5 "After your organization has signed a contract for insurance services, you can enroll yourself and your family in medical, dental, and vision plans of your choice. We've created a simple process to show this can be done. Read on for details of how you can quickly enroll yourself.").

-   **[Contracts Using the Quote UI](https://help.salesforce.com/s/articleView?id=ind.insurance_contracts_using_the_quote_ui_omnistudio.htm&language=en_US&type=5)**  
    You can create a contract using the quote UI, which is built with Lightning Web Components.
-   **[Contract Proposal OmniScript](https://help.salesforce.com/s/articleView?id=ind.insurance_contract_proposal_omniscript_omnistudio.htm&language=en_US&type=5)**  
    For the lines of business that need documents that contain the details of a contract (rather than or in addition to showing the contract details on the UI), this OmniScript can create proposal documents.

Did this article solve your issue?

Let us know so we can improve!

YesNo