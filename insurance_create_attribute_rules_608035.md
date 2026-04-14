---
title: "Create Attribute Rules"
source: "https://help.salesforce.com/s/articleView?id=ind.insurance_create_attribute_rules_608035.htm&language=en_US&type=5"
scraped: "2026-04-14"
filter: "ind.insurance_"
---# Create Attribute Rules

Create Attribute Rules[](https://help.salesforce.com/s?language=en_US)

You are here:

1.  [Salesforce Help](/s/?language=en_US)
2.  [Docs](/s/products?language=en_US)
3.  [Digital Insurance](https://help.salesforce.com/s/articleView?id=ind.insurance_admin_standard.htm&language=en_US&type=5)

# Create Attribute Rules

Create attribute rules that define how attributes and their values are shown or hidden from users.

1.  Open the child spec or root product spec you want to add attribute rules to.
2.  On the Attributes tab, click the row of the attribute you want to add a rule to.
3.  On the right pane where the attribute details are, click the Rules icon [](https://help.salesforce.com/s?language=en_US) at the top of the pane.
4.  Click **Add Rule**.
5.  Choose a **Type**.
    
    -   **Hide**
        
        Hides this attribute/value if the expression you enter in step 4 = true.
        
    -   **Message**
        
        Displays a message if the expression = **true**.
        
        You can choose from four message types:
        
        -   **Information**: Black text
            
        -   **Warning**: Orange text
            
        -   **Error**: Red text
            
            In an OmniScript LWC, if you select Error for tasks associated with an attribute value rule the error message displays, but the user can continue with the task without resolving the error.
            
        -   **Recommendation**: Blue text
            
    -   **Set Value**
        
        Displays a value if the expression = **true**. You must enter a value to set. The value can be calculated, static, or any of the functions listed in the **Functions** box below.
        
    -   **Set Default Value**
        
        Sets a default value for this attribute to display if the rule condition is met. The user can change this value when going through a quote or policy flow.
        
        The `InsProductService: getRatedProducts` runs this rule.
        
    
6.  Enter the rule into **Expression**.
    
    If you're creating a Set Value or Set Default Value attribute rule that applies to a specific user profile, use the syntax `USER_PROFILE == '<_profile name_>'`. For example:
    
    `USER_PROFILE == 'Customer Service Representative'`
    
    Important
    
    If you use a Picklist attribute in a Set Value or Set Default Value rule, verify that the rule expresses the attribute's data type as text for the Value to Set and in the rule's Expression. Picklist attribute values are stored as text, even if the corresponding picklist has another **Data Type**, such as **Number**.
    

Did this article solve your issue?

Let us know so we can improve!

YesNo