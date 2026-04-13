---
title: "Create and Test a Constraint in Constraint Rules Engine"
source: "https://help.salesforce.com/s/articleView?id=ind.insurance_advanced_configurator_create_constraint_model.htm&language=en_US&type=5"
scraped: "2026-04-13"
filter: "ind.insurance_"
---# Create and Test a Constraint in Constraint Rules Engine

Create and Test a Constraint in Constraint Rules Engine[](https://help.salesforce.com/s?language=en_US)

You are here:

1.  [Salesforce Help](/s/?language=en_US)
2.  [Docs](/s/products?language=en_US)
3.  [Digital Insurance](https://help.salesforce.com/s/articleView?id=ind.insurance_admin_standard.htm&language=en_US&type=5)

# Create and Test a Constraint in Constraint Rules Engine

Create a constraint using the Constraint Builder and test it within the Configurator UI. The example defines constraints for default values based on a selected state and product structure.

Permission Set
| Permission Set Name | Description |
| --- | --- |
| Product Configuration Constraints Designer | Create and manage constraint types and rules in Configurator with Constraint Rules Engine. |

In this example, you’ll define a constraint that sets default values for vehicle make and model based on the selected state in an auto insurance configuration. The constraint ensures:

-   State defaults to CA
-   If State is CA, vehicle Make defaults to Lexus and Model to RX350

1.  From the App Launcher, find and select **Constraint Models**.
2.  Click **New Constraint Model**.
3.  Enter a name and API name for the constraint model.
4.  Specify InsuranceContext in Context Definition.
5.  Save the constraint model.
6.  On the Details page, select the version name of the constraint model.
7.  In the Constraint Builder header in the upper left corner, select **CML Editor**.
8.  In the Constraint Builder, copy this constraint into the editor.
    
    ```
    type AutoInsurance {
        string State;
    
        relation vehicles : Vehicle;
    
        constraint(State=="CA", "State must be CA");
    
    }
    
    type Vehicle {
        string Make;
    
        string Model;
    
        constraint(Make=="Lexus", "Make must be Lexus");
    
    }
    
    type Auto : Vehicle {
        constraint(Model=="RX350", "Model must be RX350");
    
    }
    ```
    
    If your Auto Root product doesn’t include a State attribute, remove the State field and the corresponding constraint from the constraint definition.
    
9.  Save your changes.
10.  Create a Type Association for the AutoInsurance type.
     1.  Click **AutoInsurance** in the Types section of the builder.
     2.  In the Associations tab, select **Type Association**.
     3.  Click **Create Association** and then select these values in Association Details.
         
         -   Object Category: Product
         -   Object to Map: Auto Root
         
     4.  Save your changes.
11.  Create a Relationship Association for the AutoInsurance type.
     1.  Click **AutoInsurance** in the Types section of the builder.
     2.  In the Associations tab, select **Relationship Association**.
     3.  Click **Create Associations** and then select these values.
         
         -   Type Relationship: Vehicles
         -   Bundle: Auto Root
         -   Product or Product Class: Auto Vehicle Class
         
     4.  Save your changes.
12.  Create a Type Association for the Vehicle type.
     1.  Click **Vehicle** in the Types section of the builder.
     2.  In the Associations tab, select **Type Association**.
     3.  Click **Create Association** and then select these values.
         
         -   Object Entity: Product Classification
         -   Object to Map: Auto Vehicle Class
         
     4.  Save your changes.
13.  Create a Type Association for the Auto type.
     1.  Click **Auto** in the Types section of the builder.
     2.  In the Associations tab, select Type Association.
     3.  Click **Create Association** and then select these values.
         
         -   Object Entity: Product
         -   Object to Map: Auto Bundle
         
     4.  Save your changes.
14.  Save and activate your constraint model.

[](https://help.salesforce.com/s?language=en_US)

## Test the Constraint in the Configurator

1.  Create or open a quote and then set or update the Transaction Type to Advanced Configurator (or your custom label for Advanced Configurator).
2.  Add the Auto Root product to the quote.
3.  Select the **Configure** option against the Auto Root quote line item.
4.  Ensure that the default value of the State attribute ia CA.
5.  Change the state to NV.
6.  Click **Add Vehicles**, then select Auto Bundle.
7.  Click the configure icon next to Auto Bundle and verify that Make defaults to Lexus and Model defaults to RX350.

Did this article solve your issue?

Let us know so we can improve!

YesNo