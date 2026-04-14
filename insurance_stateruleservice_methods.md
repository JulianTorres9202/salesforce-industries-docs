---
title: "StateRuleService Methods"
source: "https://help.salesforce.com/s/articleView?id=ind.insurance_stateruleservice_methods.htm&language=en_US&type=5"
scraped: "2026-04-14"
filter: "ind.insurance_"
---# StateRuleService Methods

StateRuleService Methods[](https://help.salesforce.com/s?language=en_US)

You are here:

1.  [Salesforce Help](/s/?language=en_US)
2.  [Docs](/s/products?language=en_US)
3.  [Digital Insurance](https://help.salesforce.com/s/articleView?id=ind.insurance_admin_standard.htm&language=en_US&type=5)

# StateRuleService Methods

These are the available StateRuleService methods.

-   **[StateRuleService:getRuleLogs](https://help.salesforce.com/s/articleView?id=ind.insurance_stateruleservice__getrulelogs.htm&language=en_US&type=5)**  
    Use this service to retrieve rule logs for a target object, sorted by execution date in ascending order.
-   **[StateRuleService:getTransitionStates](https://help.salesforce.com/s/articleView?id=ind.insurance_stateruleservice__gettransitionstates.htm&language=en_US&type=5)**  
    Use this service to get default transition states, the **To** state of each from state transition, the current state, and the last default state for the target object.
-   **[StateRuleService:invokeRules](https://help.salesforce.com/s/articleView?id=ind.insurance_stateruleservice__invokerules.htm&language=en_US&type=5)**  
    Use this service to invoke state transition rules associated with a target state transition on a target object. If the rules satisfy the transition criteria, this service executes actions associated with the transition, optionally logs the results of the rule executions, and transitions the target object to the new state.

Did this article solve your issue?

Let us know so we can improve!

YesNo