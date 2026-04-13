---
title: "Auto Claims Overview"
source: "https://help.salesforce.com/s/articleView?id=ind.insurance_auto_claims_overview_omnistudio.htm&language=en_US&type=5"
scraped: "2026-04-13"
filter: "ind.insurance_"
---# Auto Claims Overview

Auto Claims Overview[](https://help.salesforce.com/s?language=en_US)

You are here:

1.  [Salesforce Help](/s/?language=en_US)
2.  [Docs](/s/products?language=en_US)
3.  [Digital Insurance](https://help.salesforce.com/s/articleView?id=ind.insurance_admin_standard.htm&language=en_US&type=5)

# Auto Claims Overview

The Auto Application includes a suite of claims functionality that lets an insurer take in First Notice of Loss (FNOL) data, create and update claim records, and adjudicate claims.

## Auto Claims Product Models

The foundation of the claims feature of Vlocity Insurance is claims product models. The product model provides the structure for the data JSON that moves through the claims business processes. It also contains the rules we defined to open claim records, open claim coverages, and add claim line items on a claim coverage.

The auto claim product model is named **Auto Claim**.

To learn more about Auto Claim, see [Auto Claims Product Models](https://help.salesforce.com/s/articleView?id=ind.insurance_auto_claims_product_model_omnistudio.htm&language=en_US&type=5 "The auto claim business processes uses the Auto Claim product model when creating, updating, and adjudicating claims.").

We hope that by looking deeply at this claim product model, you'll get ideas of how we built them that will help you when it's time to build your own auto claim products.

## Auto Claims FNOL

As part of the auto claim feature, we include a FNOL OmniScript that you can use to create sample claims in the Application org.

You can also dig under the hood to see how we created this OmniScript, including the data we collect and how it matches to attributes on the product model. You can also see (and open) the Omnistudio Data Mappers and Integration Procedures called by the OmniScript, and the services called as well.

To learn about the auto FNOL OmniScript, see [Auto Claims FNOL](https://help.salesforce.com/s/articleView?id=ind.insurance_auto_claims_first_notice_of_loss_omnistudio.htm&language=en_US&type=5 "Car accidents happen. When they do, policyholders need to submit First Notice of Loss (FNOL) information to their insurers to start the claims process rolling. This application includes an auto FNOL OmniScript that does just this.").

To learn about how claims FNOL works in general, see [](https://help.salesforce.com/s?language=en_US)[Claims First Notice of Loss](https://help.salesforce.com/s/articleView?id=ind.insurance_claims_first_notice_of_loss_619107.htm&language=en_US&type=5 "When policyholders, brokers, and insurance agents first notify an insurance provider about a loss, they use a First Notice of Loss (FNOL) flow. The FNOL flow kicks off claims processing, and supports the use of photos, police reports, and any other necessary files that support a claim.").

## Claims Adjuster Workbench

The Claims Adjuster Workbench comes out-of-the-box with all Vlocity Insurance claims modules. In the Auto application, you can use the Claims Adjuster Workbench to open, adjust, add to, modify, and pay line items on sample claims.

To learn about how the Claims Adjuster Workbench works, see [](https://help.salesforce.com/s?language=en_US)[Work With the Claims Adjuster Workbench](https://help.salesforce.com/s/articleView?id=ind.insurance_work_with_the_claims_adjuster_workbench_620413.htm&language=en_US&type=5 "With a cohesive view of coverages, claim participants, claim history, and financial data, claims adjusters can assess and adjudicate claims.")

The [Auto Claims Product Models](https://help.salesforce.com/s/articleView?id=ind.insurance_auto_claims_product_model_omnistudio.htm&language=en_US&type=5 "The auto claim business processes uses the Auto Claim product model when creating, updating, and adjudicating claims.") are the best place to start to learn about Auto claims.

-   **[Auto Claims Product Model](https://help.salesforce.com/s/articleView?id=ind.insurance_auto_claims_product_model_omnistudio.htm&language=en_US&type=5)**  
    The auto claim business processes uses the Auto Claim product model when creating, updating, and adjudicating claims.
-   **[Auto Claims First Notice of Loss](https://help.salesforce.com/s/articleView?id=ind.insurance_auto_claims_first_notice_of_loss_omnistudio.htm&language=en_US&type=5)**  
    Car accidents happen. When they do, policyholders need to submit First Notice of Loss (FNOL) information to their insurers to start the claims process rolling. This application includes an auto FNOL OmniScript that does just this.
-   **[Authorize Payment for Auto Claims with OS License](https://help.salesforce.com/s/articleView?id=ind.insurance_authorize_payment_for_auto_claims_with_omnistudio.htm&language=en_US&type=5)**  
    Claim approvers, claim handlers, and claim adjusters are all assigned a maximum limit that they can authorize a claim payment for. If the claim amount is over the authorized limit for a particular role, the claim needs to be approved by a claim manager before it can be paid. A guided OmniScript flow simplifies this approval process.
-   **[Auto Claims Initiate Recovery](https://help.salesforce.com/s/articleView?id=ind.insurance_auto_claims_initiate_recovery_omnistudio.htm&language=en_US&type=5)**  
    Claims adjusters have the responsibility of deciding how much money can be given for each claim. With the Claim Adjuster App, users can now quickly create a recovery record from the claim record.
-   **[View Claims as a Policyholder](https://help.salesforce.com/s/articleView?id=ind.insurance_view_claims_as_a_policyholder.htm&language=en_US&type=5)**  
    The claims detail page of the policyholder site gives policyholders a simple way to view claim details and policy terms standing, review recent claim activity, and upload documents needed to process the claim.

Did this article solve your issue?

Let us know so we can improve!

YesNo