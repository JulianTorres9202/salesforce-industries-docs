---
title: "Attribute Rules"
source: "https://help.salesforce.com/s/articleView?id=ind.insurance_attribute_rules_607965.htm&language=en_US&type=5"
scraped: "2026-04-13"
filter: "ind.insurance_"
---# Attribute Rules

Attribute Rules[](https://help.salesforce.com/s?language=en_US)

You are here:

1.  [Salesforce Help](/s/?language=en_US)
2.  [Docs](/s/products?language=en_US)
3.  [Digital Insurance](https://help.salesforce.com/s/articleView?id=ind.insurance_admin_standard.htm&language=en_US&type=5)

# Attribute Rules

Show users and customers exactly the right product attributes and attribute values for the insurance products that you quote, sell, and service.

Attribute rules apply to a whole attribute. To create rules for specific attribute values, use [Attribute Value Rules](https://help.salesforce.com/s/articleView?id=ind.insurance_create_attribute_value_rules_608112.htm&language=en_US&type=5 "Use Attribute Value Rules to determine if and when an attribute value is visible to users.") instead.

## Types of Attribute Rules

Different types of attribute rules satisfy different requirements.

-   **Set Value**
    
    Sets a specified value on an attribute when the rule evaluates to true.
    
    User's can't override a value set by a Set Value attribute rule.
    
    Set Value attribute rules are run by the [InsProductService:getRatedProducts](https://help.salesforce.com/s/articleView?id=ind.insurance_insproductservice__getratedproducts.htm&language=en_US&type=5 "Use this service to get an array of one or more products, priced using rating procedures attached to those products. This service also includes extra features such as tax and fee calculations, filtering, and performance optimization.") and [InsProductService:repriceProduct](https://help.salesforce.com/s/articleView?id=ind.insurance_insproductservice__repriceproduct.htm&language=en_US&type=5 "Use this service to price one product using the rating procedure attached to that product. This service is usually called when a user selects a product and customizes its coverage.") services. They're also run by the LWC-based Quote UI when a user adds or updates a quote.
    
-   **Set Default Value**
    
    Sets a specified default value for this attribute when the rule evaluates to true.
    
    Users can change this value if they want.
    
    Note
    
    To enable default-value override rules for partner or community users, change the Sharing Setting for the Compiled Attribute Override and Attribute Assignment objects to **Public Read Only**.
    
    Attribute set default value rules are run by the [InsProductService:getRatedProducts](https://help.salesforce.com/s/articleView?id=ind.insurance_insproductservice__getratedproducts.htm&language=en_US&type=5 "Use this service to get an array of one or more products, priced using rating procedures attached to those products. This service also includes extra features such as tax and fee calculations, filtering, and performance optimization.") service. They're also run by the LWC-based Quote UI when a user adds or updates a quote.
    
-   **Message**
    
    Displays a message with this attribute when the rule evaluates to true.
    
    Attribute message rules are run by Javascript on the front end.
    
-   **Hide**
    
    Hides this attribute from users when the rule evaluates to true.
    
    Attribute hide rules are run by Javascript on the front end.
    

## Examples of Attribute Rules

Here are some scenarios where an attribute rule is a good fit for the product model:

-   Property insurance for a property within a quarter-mile of a fault requires a higher deductible for earthquake coverage.
    
-   Construction insurance for a wood-frame building has a lower cap for fire coverage.
    
-   Auto coverage for a business owner policy with a high coverage limit requires the policyholder answer additional questions.
    
-   A business owner policy with a higher deductible can have higher coverage limits.
    
-   A business owner policy that covers Valuable Papers requires a higher limit for Media Records Coverage.
    
-   A limit or deductible amount varies based on whether the user creating the quote is a customer service representative or a captive agent.
    

As you plan your rule configuration, learn how `InsProductService: getRatedProducts` takes attribute rules into account. To add a rule to an attribute, follow the steps in [Create Attribute Rules](https://help.salesforce.com/s/articleView?id=ind.insurance_create_attribute_rules_608035.htm&language=en_US&type=5 "Create attribute rules that define how attributes and their values are shown or hidden from users.").

The Rules icon shows the number of rules applied to an attribute:

For example, you want to hide an attribute for Specialist Copay if the value of the separate Specialist attribute is **No**.

Add the rule to the Specialist Copay attribute and reference the Specialist attribute and its value. Use the % character for variables. Your code looks like this: `%productCode.attributeCode%="No"`.

Your completed attribute rule looks like this:

In this example, the Product Code for the Large Group Health product is `LGH`and the Attribute Code for Specialist is `spec`, the code in the expression is:

```
%LGH.spec%="No"
```

If the value for the Specialist attribute is either empty or Yes, the Specialist Copay attribute will display.

If the value for the Specialist attribute is No, the Specialist Copay attribute is hidden.

In products used for commercial quoting, define the **Instance Key Formula** in a way that creates unique instance keys. For example, for a Vehicle product, use a formula that incorporates unique license or part numbers:

`vehicle.vehicleType + " " + vehicle.vehicleLicNum + " " + vehicle.vehicleChassisNum`

A well-formed **Instance Key Formula** ensures that products in a multi-root quote have unique instance key values, and that the attribute rules used for commercial quoting work consistently. Find the **Instance Key Formula** field on the product Details page.

-   **[Create Attribute Rules](https://help.salesforce.com/s/articleView?id=ind.insurance_create_attribute_rules_608035.htm&language=en_US&type=5)**  
    Create attribute rules that define how attributes and their values are shown or hidden from users.
-   **[Profile-Based Insurance Rules](https://help.salesforce.com/s/articleView?id=ind.insurance_profile-based_insurance_rules.htm&language=en_US&type=5)**  
    Customize your insurance product model internally and across customer channels by using rules tailored to different user profiles.

Did this article solve your issue?

Let us know so we can improve!

YesNo