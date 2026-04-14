---
title: "Insurance Policy Payment Schedule"
source: "https://help.salesforce.com/s/articleView?id=ind.insurance_insurance_policy_payment_schedule.htm&language=en_US&type=5"
scraped: "2026-04-14"
filter: "ind.insurance_"
---# Insurance Policy Payment Schedule

Insurance Policy Payment Schedule[](https://help.salesforce.com/s?language=en_US)

You are here:

1.  [Salesforce Help](/s/?language=en_US)
2.  [Docs](/s/products?language=en_US)
3.  [Digital Insurance](https://help.salesforce.com/s/articleView?id=ind.insurance_admin_standard.htm&language=en_US&type=5)

# Insurance Policy Payment Schedule

The **Insurance Policy Payment Schedule** defines the agreed-upon payment plan between an insurance policyholder and the insurance company. It shows the scheduled payments including the premiums, taxes, and fees for a policy record across the policy term.

Click the **Related** Tab to view the payment schedule of an insurance policy.

The **Insurance Policy Payment Schedule** object displays a list of **Insurance Policy Payment Schedule Entry** records. The number of payment schedule entries depends on the premium frequency in the Policy Details. For example, if the frequency is monthly, the payment schedule shows 12 entries. If the frequency is quarterly, the payment schedule shows four entries. Each payment schedule entry corresponds to a Schedule Date and contains information such as the premium amount and payment status.

-   Entry Number
    
    Auto-generated unique identifier for each payment schedule entry.
    
-   Schedule Date
    
    The date of the premium payment of the policy.
    
-   Premium Amount
    
    The amount to be paid against the insurance policy. This amount depends on the premium calculation method and premium frequency. If the premium calculation method is modal, the total policy premium amount is divided equally across the policy period. If the premium calculation method is daily, the premium amount for an entry depends on the number of days in a given month.
    
-   Fee Amount
    
    The fee that's part of the payment schedule entry. This amount depends on the premium calculation method and premium frequency. If the premium calculation method is modal, the total fee amount is divided equally across the policy period. If the premium calculation method is daily, the fee amount depends on the number of days in a given month.
    
-   Tax Amount
    
    The tax that's part of the payment schedule entry. This amount depends on the premium calculation method and premium frequency. If the premium calculation method is modal, the total tax amount is divided equally across the policy period. If the premium calculation method is daily, the tax amount depends on the number of days in a given month.
    
-   Is Paid
    
    Indicates if the premium is paid for the payment schedule entry.
    
-   Total Amount
    
    The sum of the premium amount, fee amount, and tax amount.
    
-   Status
    
    The default status of a payment schedule entry is **Valid**. This field helps prevent double accounting in payment schedules.
    
    -   For Policy Issuance and Policy Endorsement transactions, payment schedule entries always have the status as **Valid** as there is no consolidation of payment schedule entries.
    -   For cancellation and reinstatement transactions, an insurance policy payment schedule entry can have a status of **Valid** or **Invalid**.
    -   For cancellation, if there is any unpaid payment schedule entry, then those are consolidated in a cancellation payment schedule entry, and the status of this entry is marked as **Valid**. The entries which are consolidated are marked **Invalid**.
    -   If during reinstatement, the cancellation refund payment schedule is unpaid, then the reinstatement service automatically updates the status of this payment schedule to **Invalid**. It consolidates the cancellation refund amount into the "Reinstatement by payment schedule" entry and sets the status of this entry to
        
        **Valid.**
        
-   Insurance Policy Transaction
    
    The transaction type, such as endorsement, cancellation, or reinstatement.
    

## Configure the Insurance Policy Payment Schedule

The Insurance Policy Payment Schedule is calculated at the policy level. To fetch the payment schedule for a policy, set the `includePaymentSchedule` option to `true` in the Insurance transaction services such as InsPolicyService:createUpdatePolicy. This option is available for all the services that impact the policy's premium.

Along with the `includePaymentSchedule` option, set `useIsPaidFlag` to `true` to fetch the **Insurance Policy Payment Schedule Detail** for each Insurance Policy Payment Schedule Entry.

## Insurance Policy Payment Schedule Detail

The Insurance Payment Schedule Entry Detail separates a payment schedule entry into its component parts. The entry detail includes premiums, taxes, and fees for each coverage, insured item, and participant on the policy.

To view the respective payment schedule entry details, click the Entry Number in the **Insurance Policy Payment Schedule**, and then the Related tab.

-   Entry Name: The name of the entry contributing to the payment schedule.
    
-   Fee Amount: The fee for the corresponding entry such as a coverage, asset, or participant that's part of the payment schedule entry.
    
-   Insurance Payment Schedule Entry: The Insurance Payment Schedule Entry associated with the Insurance Payment Schedule Entry Detail.
-   Insurance Policy: The Insurance Policy associated with the Insurance Payment Schedule Entry Detail.
-   Insurance Policy Asset: The Insurance Policy Asset associated with the Insurance Payment Schedule Entry Detail.
-   Insurance Policy Coverage: The Insurance Policy Coverage associated with the Insurance Payment Schedule Entry Detail.
-   Insurance Policy Participant: The Insurance Policy Participant associated with the Insurance Payment Schedule Entry Detail.
-   Premium Amount: The premium for the corresponding entry such as coverage, asset, or participant that's part of the payment schedule entry.
-   Tax Amount: The tax for the corresponding entry such as coverage, asset, or participant that's part of the payment schedule entry.

Did this article solve your issue?

Let us know so we can improve!

YesNo