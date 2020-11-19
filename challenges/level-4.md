---
description: >-
  In this section, you will find a step by step to use the formula encapsulation
  concept.
---

# Level 4: Encapsulation

## Objective

Create a formula on Ritchie that will **encapsulate another formula inside it.**

{% hint style="warning" %}
You'll find all the informations you need in the [**how to encapsulate formulas**](../tutorials/formulas/encapsulate-formulas.md) tutorial section.
{% endhint %}

  
****The idea is to encapsulate at least 2 formulas inside another one: 

* **`rit math sum numbers`** \(Level 1\)
* **`rit math multiply numbers`** \(TODO\)

{% hint style="info" %}
Command suggestion: **`rit math calculate`**
{% endhint %}

## Inputs

This formula needs to contain \(at least\) those three inputs parameters:

1. Number one \(`RIT_UMBER_ONE`\). 
2. Number two \(`RIT_NUMBER_TWO`\). 
3. Operation \(`RIT_OPERATION`\).

## Step by step

To implement this formula, it will be necessary to follow the steps below:

**Premisse:** Creation of the **`rit math multiply numbers`** formula \(same as level 1\).

1. Extract all inputs parameters. 
2. Execute the rit formula according to the selected operation:
   * **multiply** should call **`rit math multiply numbers`**
   * **sum** should call **`rit math sum numbers`**
3. Return the result on the terminal.

## Improvement suggestions

 If you want to play a little more, here are some suggestions:

* Add more operations. 
* Add the option to inform any quantity of numbers as inputs.

