---
title: "Set Instance and Root Product Premium Formulas on Simulator"
source: "https://help.salesforce.com/s/articleView?id=ind.insurance_set_instance_and_root_product_premium_formulas_on_simulator_610533.htm&language=en_US&type=5"
scraped: "2026-04-14"
filter: "ind.insurance_"
---# Set Instance and Root Product Premium Formulas on Simulator

Set Instance and Root Product Premium Formulas on Simulator[](https://help.salesforce.com/s?language=en_US)

You are here:

1.  [Salesforce Help](/s/?language=en_US)
2.  [Docs](/s/products?language=en_US)
3.  [Digital Insurance](https://help.salesforce.com/s/articleView?id=ind.insurance_admin_standard.htm&language=en_US&type=5)

# Set Instance and Root Product Premium Formulas on Simulator

Make sure your insurance product premiums take optional coverages into account by using rating procedures for coverages in combination with formulas on the root product Simulate tab.

1.  Use your rating procedure to calculate premiums for all the coverages you plan to associate with a root product.
2.  Set up a formula on the root product Simulate tab to calculate the premium for the insured item instance.
3.  Set up a formula on the root product Simulate tab to calculate the total premium for the product.

[](https://help.salesforce.com/s?language=en_US)When you set up the formulas for the insured item instance premium and total product premium on the root product Simulate tab, the Simulator accounts for optional coverages that the user selects and deselects, and it displays the correct amounts for the insured items instances and total premium.

[](https://help.salesforce.com/s?language=en_US)Note Instead of setting up formulas on the root product Simulate tab, you can set up your rating procedure to calculate the insured item instance premium and the total product premium. But this method does not take optional coverage selections into account, which means that the premiums don't display correctly on the UI for users.

[](https://help.salesforce.com/s?language=en_US)

## Insured Item Instance Premium and Exposure

When an insured item instance is a parent of another insured spec or coverage, it must have its own pricing formula or rating procedure. For example, some auto products allow multiple vehicles to be added to a single policy. This type of policy is structured so that each selected coverage is the child to a specific vehicle. Each insured vehicle comes with its own input characteristics and coverage selections, which affect the rating for that specific vehicle. To make sure each vehicle instance is calculated, add a pricing formula to the Auto insured item.

To add a pricing formula to an insured item, start the Simulate tab of the root product. For the insured item instance, enter a price formula for the instance into the Total Pricing Formula. This is the formula that takes the output of the rating procedure (coverages) and adds them up to create a total price for one insured item instance.

To calculate and display the insurance company’s total exposure for this insured item instance, enter a variable or formula into the Total Insured Formula.

Add pricing formulas only to parent insured item specs. The pricing formula in a parent spec references the child specs of the parent. If an insured instance isn’t a parent to another product spec, there’s no reason to add a pricing formula.

If an insured item isn’t a parent spec and doesn’t contain a pricing formula, you can map the insured item spec to an output variable. Enter the appropriate output variable in the Pricing Source Mapping field of the product child item page. Don’t use the Pricing Formula field because entering the output variable there can cause issues with the rating procedure later.

[](https://help.salesforce.com/s?language=en_US)

## Root Product Premium and Exposure

For the root product, enter the formula that creates the total premium for the product. This is usually the sum of all instances of the insured item. Use the SUM() function with the insured item instance total premium formula.

For example, here's an insured item instance premium formula in the examples:

premiumBIPD + premiumCOLL + premiumCCD + premiumMED + premiumUM

The corresponding total root product premium formula is:

SUM(premiumBIPD + premiumCOLL + premiumCCD + premiumMED + premiumUM)

The SUM() formula takes arrays of each of the output variables in the insured item instance formula, sums each array, then sums up the total of all the arrays. Only the user-selected optional coverages will be included in the totals.

To calculate and display the total exposure the insurance company will carry for this policy, enter a variable or formula into the Total Insured Formula.

Did this article solve your issue?

Let us know so we can improve!

YesNo