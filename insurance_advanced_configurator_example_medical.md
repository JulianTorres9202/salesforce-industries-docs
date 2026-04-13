---
title: "Constraint Examples for Medical"
source: "https://help.salesforce.com/s/articleView?id=ind.insurance_advanced_configurator_example_medical.htm&language=en_US&type=5"
scraped: "2026-04-13"
filter: "ind.insurance_"
---# Constraint Examples for Medical

Constraint Examples for Medical[](https://help.salesforce.com/s?language=en_US)

You are here:

1.  [Salesforce Help](/s/?language=en_US)
2.  [Docs](/s/products?language=en_US)
3.  [Digital Insurance](https://help.salesforce.com/s/articleView?id=ind.insurance_admin_standard.htm&language=en_US&type=5)

# Constraint Examples for Medical

Review example constraints for a comprehensive health insurance model.

These constraints show how to enforce rules based on member age, gender, marital status, relationships, and user profile. Use these patterns to manage preventive care, chronic disease coverage, and outpatient behavior across primary and dependent members.

For full reference, you can review the [complete Medical CML file](https://resources.docs.salesforce.com/rel1/doc/en-us/static/pdf/insurance_advanced_configurator_medical_cml_file.pdf).

## Require PCW and Chronic Disease Coverage for Specific Member Profiles

If the primary member has outpatient coverage and is either a male over 40 or a married female, then Preventive Care & Wellness (PCW) coverage with a $5000 deductible is required, along with Chronic Disease Coverage.

What it covers

-   Multi-condition constraint
-   Require coverage constraint
-   Conditional attribute enforcement

CML Example

```
type PrimaryMember : Member {
    @(closeRelation=true, propagateUp=true, sequence=1)
    relation dependentmember : Member;
    @(sequence=3)
    relation chronicdisease : ChronicDisease[0..1];
    @(sequence=4)
    relation preventivecarewellness : PreventiveCareWellness[0..1];
    @(sequence=5)
    relation outpatient : OutPatient[0..1];

    boolean isClause1 = (Age >= 40 && Gender == "Male") || Marital_Status == "Married";
    boolean isPrimaryMemberOutPatientSelected = outpatient[OutPatient] > 0;

    constraint(isClause1 && isPrimaryMemberOutPatientSelected -> preventivecarewellness[PreventiveCareWellness].Deductible_Limit == 5000, "Preventive care & wellness message Deductible Limit is set 5k");
    require(isClause1 && isPrimaryMemberOutPatientSelected, chronicdisease[ChronicDisease], "Auto Add ChronicDisease");
}
```

## Enforce Constraints Based on Dependent Status and User Profile

If the primary member is female, the user is a standard user, and at least one dependent member is single, then certain attribute values are hidden, and coverage is required or excluded accordingly.

What it covers

-   Require coverage constraint
-   Exclude coverage constraint
-   Hide attribute value
-   Cross-product interaction

CML Example

```
@(contextPath = "SalesTransaction.UserProfile", attributeSource = "ST")
extern string UserProfile;

type PrimaryMember : Member {
    @(closeRelation=true, propagateUp=true, sequence=1)
    relation dependentmember : Member {
        depMemberSingleMaritalStatus = count(Marital_Status == 'Single');
    }
    @(sequence=2)
    relation criticalillnesssurgery : CriticalIllnessSurgery[0..1];
    @(sequence=4)
    relation preventivecarewellness : PreventiveCareWellness[0..1];
    @(sequence=5)
    relation outpatient : OutPatient[0..1];

    boolean isClause2 = Gender == 'Female' && UserProfile == "Standard User" && dependentmember.depMemberSingleMaritalStatus > 0;

    exclude(isClause2, preventivecarewellness[PreventiveCareWellness], "remove primary member PCW coverage");
}

type DependentMember : Member {
    @(sequence=4)
    relation dependentcriticalillnesssurgery : CriticalIllnessSurgery[0..1];

    boolean parentIsClause2 = parent(isClause2);
    rule(parentIsClause2, "hide", "attribute", "Gender", "value", "Female");
    require(parentIsClause2, dependentcriticalillnesssurgery[CriticalIllnessSurgery], "Auto add dep member critical illness surgery");
}

@(split = false)
type OutPatient {
    int Doctor_visit_copay = [0, 10, 25, 10000];
    boolean getClauseFlag = parent(parentIsClause2);
    rule(getClauseFlag, "hide", "attribute", "Doctor_visit_copay");
}
```

## Require Dependent PCW Based on Age and Parent PCW Deductible

If the dependent member is under 30 and the primary member’s PCW has an Out Network Deductible Limit of 250 or more, then the dependent must have PCW with an annual out-of-pocket limit of 20000.

What it covers

-   Multi-entity dependency
-   Cross-product constraint
-   Conditional attribute setting

CML Example

```
type PrimaryMember : Member {
    @(closeRelation=true, propagateUp=true, sequence=1)
    relation dependentmember : Member;
    @(sequence=4)
    relation preventivecarewellness : PreventiveCareWellness[0..1];

    int primarymemberPCWOut_Network_Deductible_Limit = preventivecarewellness[PreventiveCareWellness].Out_Network_Deductible_Limit;
}

type DependentMember : Member {
    @(sequence=2)
    relation dependentpreventivecarewellness : PreventiveCareWellness[0..1];

    int primmemberONDL = parent(primarymemberPCWOut_Network_Deductible_Limit);
    require((Age < 30 && primmemberONDL >= 250), dependentpreventivecarewellness[PreventiveCareWellness] {Annual_Out_of_Pocket_Limit = 20000},"Preventive Care Is Required OOPM is set to 20k");
}
```

## Require Chronic Disease and Set Copay for Standard Users

If the primary member has outpatient coverage and the user is a standard user, then a chronic disease must be added for the dependent, and the doctor visit copay must be set to 10000.

What it covers

-   Require coverage constraint
-   Attribute defaulting
-   User profile-based logic

CML Example

```
@(contextPath = "SalesTransaction.UserProfile", attributeSource = "ST")
extern string UserProfile;

type PrimaryMember : Member {
    @(closeRelation=true, propagateUp=true, sequence=1)
    relation dependentmember : Member;
    @(sequence=5)
    relation outpatient : OutPatient[0..1];

    boolean isClause4 = outpatient[OutPatient] > 0;
    constraint(outpatient[OutPatient] > 0 && UserProfile == "Standard User" -> outpatient.Doctor_visit_copay == 10000, "If OP cover then set Doctor visit to 10k");
}

type DependentMember : Member {
    @(sequence=3)
    relation dependentchronicdisease : ChronicDisease[0..1];

    boolean parentIsClause4 = parent(isClause4);
    require(parentIsClause4 && UserProfile == "Standard User", dependentchronicdisease[ChronicDisease], "Autoadd chronic disease cov for depmember");
}
```

## Require Chronic and Outpatient Coverage Based on Age Conditions

If the primary member is over 40 and the dependent member is under 30, the dependent must have outpatient coverage, and the primary member must have chronic disease coverage.

What it covers

-   Age-based condition logic
-   Multi-entity requirement
-   Sibling product constraint

CML Example

```
type PrimaryMember : Member {
    @(closeRelation=true, propagateUp=true, sequence=1)
    relation dependentmember : Member {
        depMemMaxAge = max(Age);
    }

    @(sequence=3)
    relation chronicdisease : ChronicDisease[0..1];

    require(Age > 40 && dependentmember.depMemMaxAge < 30, chronicdisease[ChronicDisease], "Auto Add ChronicDisease for Primary member");
}

type DependentMember : Member {
    @(sequence=1)
    relation dependentoutpatient : OutPatient[0..1];

    int primmemberAge = parent(Age);
    require(primmemberAge > 40 && Age < 30, dependentoutpatient[OutPatient], "Auto add OP cov for depmember");
}
```

Did this article solve your issue?

Let us know so we can improve!

YesNo