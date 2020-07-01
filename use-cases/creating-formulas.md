---
description: Step by step explaining how to create a new formula on Ritchie.
---

# Creating formulas

## Introduction 

The process to create a formula it is done through the **`rit create formula`** command. It creates the necessary structure for the user to start developing a new formula on his local machine.

{% hint style="info" %}
Before following the steps to create a formula, it is recommended to have **Ritchie** **properly installed** and **tested** to make sure all the commands are working.
{% endhint %}

## Step 1: Formula creation

When the **`rit create formula`** command is executed on the terminal, a few information are requested from the user :  
  
1. the **`new formula command`**  

The ideal is to follow the pattern rit + group + verb + noun.

2. the **`new formula programming language`** 

A _**Hello World template**_ will be created  in this language.

3. the **`workspace`** where the new formula will be added 

It can be an existing formula workspace. If there isn't any available, a default formula workspace will be created automatically, named **`ritchie-formulas-local`** in the **HOME** of the user's machine.  
****

![Creation of a new formula](https://lh5.googleusercontent.com/ZAkUuAxUQVqtusM_n3IThSnfvAy46zcmm9CwIBOvNiByqq3pN_MJZWoXQnTHzpffVtld1gjMc2pPuBaPNdgwWr1omPpAEKRLwN8rzSWUYWjXGesVZIjm5W0ZQgq0u_vUYCRpdZRc)

The **`rit create formula`** command also build the formula automatically \(it generates the formula executables files and add them to the [.rit folder](https://docs.ritchiecli.io/developer/cli#composition-of-the-rit-folder)\). 

That means it is possible to execute the new command directly after its creation. In that case, the formula _**Hello World template**_ will be executed as shown below :  
****

![Execution of the Hello World template](https://lh3.googleusercontent.com/iju8Rbeh1vm7adM9d-9Y-jxDaqE93VonK3Gr2fDKZBgV0uNkJ8pn-q97zM_WFQLiQOr3cDXknfaEa6Qyb6G9Cgzfr_gFJH-LvvQa-QRAHT8Pm1TJQ_QD7JcTE6bk0964Dyn0H_NU)

This _**Hello World template**_ is currently composed of 3 inputs parameters :

1. a sample text variable
2. a sample list of variables
3. a sample boolean variable

Those represents the 3 kinds of inputs currently available when using Ritchie.

## **Step 2: Formula structure**

All Ritchie formulas workspaces follow the same architecture, you can find more information [in the formulas section](https://docs.ritchiecli.io/developer/formulas).

When executing the **`rit create formula`** command, the new formula is added to the informed workspace, updating automatically the workspace structure with the _Hello World template_ files.

![ritchie-formula-local repository structure with rit demo create formula Hello World template ](../.gitbook/assets/rit-demo-create-formula.png)

## Step 3: **Formula implementation**

With the new formula structure generated successfully inside the chosen workspace, it is possible to start implementing the new automation, updating the Hello World template.

To implement the desired operation, it is necessary to update 3 files located inside the /src package of the new formula’s root folder :

1. The formula **`config.json`**, to configure the inputs. 
2. The **`main file`** \(generally used to extract those inputs\) 
3. The **`files in the /pkg folder`**.

Observation : Depending on the chosen language, it may be necessary to update more files, for example to manipulate dependencies.

{% hint style="warning" %}
**Some other instructions:**

❗Do not change the name of the formula's root folders \(group / verb / noun\) without updating the tree.json and Makefile \(of the workspace\) with the appropriated paths.

❗The tree.json and Makefile \(of the workspace\) are already created / updated by executing the rit create formula command. Consequently, you will not need to change them to be able to test the new formula, even after changing the files commented above.  
{% endhint %}

## Step 4: **Test the formula new implementation**

Once the new automation has been implemented, it necessary to execute the **`rit build formula`** command to update the formula executable files which has been generated at its creation.

When the rit build formula command is executed on the terminal, a few information are requested from the user :

1. the **`workspace`** where the formula has been implemented 
2. the **`path`** to the formula /src package \(group / verb / noun, if this pattern has been followed\) ****

![Build of a formula](https://lh3.googleusercontent.com/Anz1rV6HJ3e9mwSIW3IPTK77DVuYruASkphPW-Ro8Zo9_QhMkM7alNfRtJ8o741l-I7BYrI7sBnsHNMndH1Q7lUWNDvwksLA7UEQXGZMP6XAe6lbbwhdgG12XBpocpWprVHelLH6)

That’s it ! After building successfully the formula, it is possible to execute the formula command again to see the updated implementation.

{% hint style="info" %}
**Note** : the **`rit build formula`** command can also be used with a flag **`--watch`**.

Using this flag, the command will automatically “watch” the specified formula **`/src package`** and update the formula executable files if any change is saved by the user.
{% endhint %}

{% hint style="danger" %}
**Beta** : Currently, the rit build formula command isn’t available on Windows for all programming languages. The Golang language is the only language supported by this command on Windows so far. However, all languages are supported on Linux and MacOs.
{% endhint %}

