---
title: "Property Quote OmniScript"
source: "https://help.salesforce.com/s/articleView?id=ind.insurance_property_quote_omniscript_omnistudio.htm&language=en_US&type=5"
scraped: "2026-04-14"
filter: "ind.insurance_"
---# Property Quote OmniScript

Property Quote OmniScript[](https://help.salesforce.com/s?language=en_US)

You are here:

1.  [Salesforce Help](/s/?language=en_US)
2.  [Docs](/s/products?language=en_US)
3.  [Digital Insurance](https://help.salesforce.com/s/articleView?id=ind.insurance_admin_standard.htm&language=en_US&type=5)

# Property Quote OmniScript

Look under the hood of the property insurance quote process with details of the quote OmniScript.

The property quote OmniScript is:

-   Type: **property**
    
-   SubType: **HomeQuote**
    
-   OmniScript Name: **Homeowners Quote**
    

[](https://help.salesforce.com/s?language=en_US)

You can launch this OmniScript from the following applications, where it can be accessed by the types of users described:

-   Broker Portal (Newport)
    
    For use by brokers and agents
    
-   Interaction Console (Lightning)
    
    Internal insurance agent
    
-   Vlocity Admin (Newport)
    
    -   Internal insurance agent
        
    -   Vlocity admin
        

The Homeowners Quote OmniScript calls three other OmniScripts:

-   CreatePersonAccountForQuote
    
-   [QuoteProposal](https://help.salesforce.com/s/articleView?id=ind.insurance_quote_proposal_omniscript_518099.htm&language=en_US&type=5 "For the lines of business that need documents that contain the details of a quote (rather than or in addition to showing the quote details on the UI), this OmniScript can create quote documents.")
    
-   QuoteWrapUp
    

[](https://help.salesforce.com/s?language=en_US)

## How It Works

This section describes how someone who goes through the Homeowners Quote OmniScript to create a quote will see and interact with it. We'll go through this OmniScript step by step, as though we were a broker or an agent creating a quote for a potential customer.

This OmniScript starts out expecting an account number to be passed to it as input, so we use an existing account for Ernie Newcomb.

The Homeowners Quote OmniScript starts with an intro page.

After clicking **Next**, we enter address information about the property to be insured.

Tip

You can click AutoFill on any page to fill out data quickly when you test this OmniScript.

The **Effective Date** defaults to today's date.

We enter more information about the property to be insured.

We enter information about the property's contents.

Now it's time to review the coverages, make changes to any of the values we need to, and add, remove, or modify values on optional coverages.

Finally, we confirm and (if needed) add to contact information.

The OmniScript calls a reusable OmniScript, QuoteProposal, and generates a PDF document that contains the details of the quote.

Lastly, this OmniScript calls the QuoteWrapUp OmniScript to conclude the quoting process. The UI displays the quote number, the total annual premium, and the date the quote expires.

[](https://help.salesforce.com/s?language=en_US)

## What's In It

The Homewoners Quote is LWC Enabled. It's available in the new Visual Design Studio, so that's what the screenshot of the OmniScript structure shows.

This is the complete structure of the Homeowners Quote OmniScript:

Did this article solve your issue?

Let us know so we can improve!

YesNo