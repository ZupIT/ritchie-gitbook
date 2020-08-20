---
description: >-
  You will find in this section challenges to start implementing simple formulas
  on Ritchie with a gradual complexity.
---

# Level 2

## 1. Objective

Create a formula on Ritchie that will **return a JSON with Github credentials**.

{% hint style="info" %}
Command suggestion: **`rit github get credentials`**
{% endhint %}

## 2. Inputs

This formula needs to contain \(at least\) those two inputs parameters:

1. [ ] Username \(`GIT_USER`\). 
2. [ ] Token \( `GIT_TOKEN`\).

{% hint style="warning" %}
**Note**: The challenge consists in configure those inputs inside the **config.json** file, but run the formula without informing them as `prompt` or `stdin` \(they will be extracted automatically\).

You'll find all the informations you need in the [**how to manipulate credentials**](https://docs.ritchiecli.io/how-to/manipulate-credentials) tutorial section.
{% endhint %}

## 3. Step by step

The formula needs to follow the next steps:

1. [ ] Extract inputs parameters. 
2. [ ] Create the JSON with Github credentials. 
3. [ ] Return the result on the terminal.

## 4. Improvement suggestions

 If you want to play a little more, here are some suggestions:

* [ ] Develop some Github operation by manipulating these credentials. 
* [ ] Code a formula which will allow the user to create a repository on Github. 
* [ ] Code a formula which will allow the user to **add**, **commit** and **push** using one command only.  
* [ ] Code a formula which will allow the user to generate a release of the informed Github repository.

## Next steps 

👉 If you've completed the second challenge, let's go to the [level 3 challenge](level-3.md)!

