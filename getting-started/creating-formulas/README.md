---
description: Step by step explaining how to create a new formula on Ritchie.
---

# Creating formulas

## Introduction 

The process to create a formula it is done through the _**`rit create formula`**_ command, that creates the necessary structure for the user to start developing a new formula on his machine.

It is important to have in mind before following the steps to create a formula, it is recommended to have Ritchie properly installed and tested to make sure the commands are working. 

## Step 1: Execute the formula 

When this command is executed on the terminal, an input is requested from the user, the **command** that will execute the new formula.

{% hint style="info" %}
Remember, the ideal is to follow the pattern **rit + group + verb + noun.**
{% endhint %}

![Create new formula example ](../../.gitbook/assets/rit-create-formula.gif)

## **Step 2: Direct to a repository** 

When the command for creating a formula is executed, you can choose to inform the path to a formula repository already on the machine.

If there isn't any formula repository available, a formula repository will be created automatically, named **ritchie-formulas-local** in the **HOME** of the user's machine. 

{% hint style="info" %}
If it isn't informed anything and this local repository exists, the new formula will be added there, automatically updating its structure. 
{% endhint %}

Here is an example of the structure of the local repository with a formula \(inside the group folder\).

![](https://lh3.googleusercontent.com/Tz7C28jLzbXdqABAVo1BUWXr_uMkBcIxwsEXvze8OYVOU3Gs6mLoMhIF5EFYp6bq7bQjE8wvyuFxLWR5Qx2xBLSCnLorRc9kc6DWZVHQu09P_WV4BL4TkQ4SsWrCez0nEmqCSiD4)

## Step 3: Organize the formula folder 

{% hint style="info" %}
It is good to remember the **`rit create formula`**command automatically creates a folder for the formula in the repository according to the input provided.
{% endhint %}

The formula folder has the following structure :

![](https://lh4.googleusercontent.com/lu-BipM4Ym4qc3EeGXLNoEyvDknCZ1ZUtAvUxWra0v4uyyKi71gZiUAJzwi2n4UlwqPwdhKROps945TJ6g6i_kfi_TmlqC-nC-JOVl7T3Oy6Ks5Fnoy8Ok1lwVViRn36JAV-JAg0)

The contents of the **SRC** folder are standardized according to the chosen language, and are always composed of the following elements: 

### The main file 

The **main** file is the formula's executable. It that starts the code that will be called by the terminal. It will be created according to the language entered as input to the command, and will contain a standard implementation example. 

### The Makefile file \(of the formula\) 

The **Makefile** \(formula\) file is different from the Makefile file in the repository. The Makefile \(formula\) allows to generate the executables of the formula, while the Makefile of the repository allows both to generate the executables of all formulas, as well as to test the formulas locally by adding these executables in the .rit folder. 

### The config.json file 

The **config.json** file contains **3 standard inputs** as an example, which are extracted and manipulated in the main file of the formula. 

### The pkg folder 

The **pkg** folder will be composed of the other code files that, together with the main file, will allow the formula to be executed. They will be created in the chosen language. 

If you first created a formula by creating the local repository, the formula repository and folder will follow the structure below :

![](https://lh5.googleusercontent.com/6oPMzmvLxb9PGmC9a6U7KfLt4oCpEnFhOHXXOoGkgMgmaQi4kKHDo5epvU27HbWbBvM1mC1K2aruXfGPQrtWJMibeXmXmN19NbI7S81Djz11Axc0fCG2GtTNCAYivuI2iMMxMLZK)

## Step 4: Implement the formula

Once you have created the formula in your repository and accessed its folder, it is time to implement your automation.

It is necessary to change 3 places to implement the desired operation: 

* The **config.json** of the formula for configuring the inputs. 
* The **main** file \(generally used to extract those inputs\)
* The files in the **pkg folder.** 

If another language was used, it may be necessary to change more files.

{% hint style="warning" %}
**Some other instructions**:

❗Do not change the name of the formula's root folders \(group / verb / noun\) without updating the **tree.json** and **Makefile** \(of the repository\) with the appropriated paths. 

❗Remember that **tree.json** and **Makefile** \(of the repository\) are already created / changed by executing the `rit create formula` command. Consequently, you will not need to change them to be able to test the new formula, even after changing the files commented above.

It is possible to make some adjustments to these files if you need to_._ For example, if you need to change the decrypted message or the command helper associated with your formula, you will need to make these changes in **tree.json.**
{% endhint %}

