---
title: "Constraint Examples for AutoSilver"
source: "https://help.salesforce.com/s/articleView?id=ind.insurance_advanced_configurator_example_autosilver.htm&language=en_US&type=5"
scraped: "2026-04-13"
filter: "ind.insurance_"
---# Constraint Examples for AutoSilver

Constraint Examples for AutoSilver[](https://help.salesforce.com/s?language=en_US)

You are here:

1.  [Salesforce Help](/s/?language=en_US)
2.  [Docs](/s/products?language=en_US)
3.  [Digital Insurance](https://help.salesforce.com/s/articleView?id=ind.insurance_admin_standard.htm&language=en_US&type=5)

# Constraint Examples for AutoSilver

Review example constraints designed for the AutoSilver product model to support complex auto insurance logic.

Use these constraint examples to understand how to apply conditional logic across vehicle characteristics, coverage selections, and cross-product interactions.

For full reference, you can review the [complete AutoSilver CML file](https://resources.docs.salesforce.com/rel1/doc/en-us/static/pdf/insurance_advanced_configurator_auto_silver_cml_file.pdf).

## Require Medical Coverage for High-Value Older Cars

If the most expensive car is over $50,000 and the oldest car is from before 2020, Medical Payment Coverage with a $2000 limit is required.

What it covers

-   Multi-instance constraint
-   Require coverage constraint
-   Cross-product constraint

CML Example

```
type AutoSilver {
    @(closeRelation = true, propagateUp = true, sequence = 1)
    relation auto : Vehicle { 
        maxAutoValue = max(Auto_Value); 
        minAutoYear = min(Year);
    }

    boolean constraint1 = auto.maxAutoValue >= 50000 && auto.minAutoYear < 2020;
    require(constraint1, medicalpayments[MedicalPayments], "Auto add Medical Payments");
    constraint(constraint1 && medicalpayments[MedicalPayments] > 0 -> medicalpayments[MedicalPayments].Limit == 2000, "Medical coverage set to $2000 for older high-value vehicles");
}

type Auto {
    @(configurable = false)
    decimal(2) Auto_Value;

    int Year = [1980..2026];
}

type MedicalPayments {
    @(defaultValue = "1000", domainComputation = false)
    int Limit = [1000, 2000, 5000, 10000, 25000, 50000];
}
```

## Require Collision Coverage for Newer Vehicles

Adds Collision coverage with a $5000 limit for vehicles newer than 2023.

What is covers

-   Require coverage constraint
-   Cross-product constraint

CML Example

```
type Auto {
    int Year = [1980..2026];
}

type Vehicle : Auto {
    relation collision : Collision[0..1];

    boolean constraint2 = Year > 2023;
    constraint(constraint2 -> collision[Collision], "auto add collision coverage"); 
    constraint(constraint2 && collision[Collision] > 0 -> collision[Collision].Limit == 5000, "set collision limit to 5000");
}

@(split = false)
type Collision {
    @(defaultValue = "1000", domainComputation = false)
    int Limit = [1000, 2000, 5000, 10000, 25000, 50000];
} 
```

## Exclude Uninsured Motorist Coverage for Older Vehicles

Prevents the selection of Uninsured Motorist coverage when a vehicle is older than 2020 and Collision coverage with a $200 deductible is selected.

What it covers

-   Exclude coverage constraint
-   Cross-product constraint

CML Example

```
type Auto {
    int Year = [1980..2026];
}

type Vehicle : Auto {
    @(sequence = 4)
    relation comprehensive : Comprehensive[0..1];

    @(sequence = 3)
    relation uninsuredMotorist : UninsuredMotorist[0..1];

    boolean constraint3 = collision[Collision] > 0 && collision[Collision].Deductible == 200 && Year < 2020;
    exclude(constraint3, uninsuredMotorist[UninsuredMotorist]);
}

@(split = false)
type Collision {
    @(defaultValue = "1000", domainComputation = false)
    int Limit = [1000, 2000, 5000, 10000, 25000, 50000];

    @(domainComputation = false)
    int Deductible = [0, 50, 100, 200, 500];
}   

@(split = false)
type UninsuredMotorist;
```

## Driver Licensing Age Validation

Ensures that a driver's age and age at first license are both greater than 16.

What It Covers

-   Base constraint

CML Example

```
type Driver {
    @(configurable = false)
    int Age = [0..100];

    int Age_First_Licensed = [0..100];

    message(Age_First_Licensed < 16, "Don’t know who gave you license to driver before 16, legally!", "Warning");
    message(Age < 16, "Error”: Driver is underaged to be added to the quote", "Error");
}
```

## Require BIPD When Certain Conditions Are Met

This constraint requires BIPD coverage when certain vehicle, driver, and price conditions are met, and Medical Payments are not selected. It also hides attributes and values in the BIPD coverage.

What it covers

-   Multi-instance constraint
-   Require coverage constraint
-   Cardinality constraint
-   Parent cardinality constraint
-   Cross-product constraint
-   Grandchild products constraint
-   Siblings products constraint

CML Example

```
type AutoSilver {
   @(closeRelation = true, propagateUp = true, sequence = 1)
   relation auto : Vehicle {
       maxDriverAccPoint1 = max(maxDriverAccPoint);
       autoHasAntiTheft = count(Has_Anti_Theft > 0);
   }

   @(sequence = 2)
   relation bodilyinjurypropertydamage : BodilyInjuryPropertyDamage[0..1];
   
   @(sequence = 3)
   relation medicalpayments : MedicalPayments[0..1] {
       medicalLimit = Limit;
       medicalDeductible = Deductible;
  }

  @(tagName = "ItemTotalPrice")
  decimal(2) totalPrice;

   boolean autoCondition = auto[Vehicle] > 0 &&  !auto.autoHasAntiTheft;
   boolean driverCondition = auto.maxDriverAccPoint1 > 5;
   boolean totalPriceCondition = totalPrice > 10;
   boolean constraint5 = autoCondition && driverCondition && totalPriceCondition && medicalpayments[MedicalPayments] == 0;
   @(abort = true)
   require(constraint5, bodilyinjurypropertydamage[BodilyInjuryPropertyDamage], "BIPD is required when Auto IsElectricVehicle and Antitheft is false and Driver accident points > 5 and Collision is selected and MedicalPayments is NOT selected");

}

type Auto {
   boolean Has_Anti_Theft;
}

type Vehicle : Auto {
   int maxDriverAccPoint = driver.maxDriverAccPoint;

   @(closeRelation = true, propagateUp = true, sequence = 1)
   relation driver : AutoDriver[0..5] {
   	maxDriverAccPoint = max(Driver_Accident_Points);
   }

type Driver {
   int Driver_Accident_Points = [0..10];
}

type MedicalPayments {
   @(defaultValue = "1000", domainComputation = false)
   int Limit = [1000, 2000, 5000, 10000, 25000, 50000];

}

@(split = false)
type BodilyInjuryPropertyDamage {
   @(defaultValue = "1000", domainComputation = false)
   int Property_Damage_Per_Accident_Limit = [500, 1000, 1500, 2000];

   @(defaultValue = "1000", domainComputation = false)
   int Bodily_Injury_Per_Accident_Limit = [500, 1000, 1500, 2000];

   boolean rootconstraint5 = parent(constraint5);
   rule(rootconstraint5, "hide", "attribute", "Property_Damage_Per_Accident_Limit");
   rule(rootconstraint5, "hide", "attribute", "Bodily_Injury_Per_Accident_Limit","value", 2000);

}
```

## Require BIPD for Standard Users with Medical Payments

Adds BIPD coverage with a $1000 Bodily Injury Per Person Limit when a standard user selects Medical Payment coverage with $1000 limit and a high unit price.

What it covers

-   Require coverage constraint
-   Cardinality constraint
-   Cross-product constraint
-   Siblings products constraint

CML Example

```
@(contextPath = "SalesTransaction.UserProfile", attributeSource = "ST")
extern string UserProfile;

type AutoSilver {
   @(sequence = 3)
   relation medicalpayments : MedicalPayments[0..1] {
       medicalLimit = Limit;
       medicalDeductible = Deductible;
       medicalInputUnitPrice = inputUnitPrice;
   }

   @(sequence = 2)
   relation bodilyinjurypropertydamage : BodilyInjuryPropertyDamage[0..1];

   boolean constraint6 = medicalpayments[MedicalPayments] == 1 && medicalpayments.medicalDeductible == 500 && UserProfile == "Standard User" && medicalpayments.medicalInputUnitPrice > 220;
   require(constraint6, bodilyinjurypropertydamage[BodilyInjuryPropertyDamage], "BIPD is required when MedicalPayments is selected at 1k limit");
   constraint(constraint6 && bodilyinjurypropertydamage[BodilyInjuryPropertyDamage] -> bodilyinjurypropertydamage[BodilyInjuryPropertyDamage].Bodily_Injury_Per_Person_Limit == 1000);
}

@(split = false)
type BodilyInjuryPropertyDamage {
   @(defaultValue = "1000", domainComputation = false)
   int Bodily_Injury_Per_Person_Limit = [500, 1000, 1500, 2000];
}

@(split = false)
type MedicalPayments {
   @(defaultValue = "100", domainComputation = false)
   int Deductible = [0, 50, 100, 200, 500];

   @(tagName = "InputUnitPrice")
   decimal(2) inputUnitPrice;
}
```

Did this article solve your issue?

Let us know so we can improve!

YesNo