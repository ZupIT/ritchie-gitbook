---
description: >-
  In this section, you will find definitions for the main terms and expressions
  used in the documentation and in Ritchie, or in discussions within the
  developer community.
---

# Key Concepts

{% hint style="danger" %}
Let's assume you're familiar with **Standard Streams,** **CLI**, **JSON** format and **automations** concepts.
{% endhint %}

## Formulas

{% hint style="info" %}
**Formulas** are nothing more than **automations**. That is, they are codes called through the command lines to perform some operation. 
{% endhint %}

## **Formulas o**n demand

The first time the user executes the command associated with a formula on the terminal, the executable file for that formula is downloaded according to the operating system installed on his computer. 

The config.json file is downloaded at the same time, with the **formula input parameters**, necessary for the code implemented in the executable file to be executed. 

These input parameters will be informed by the user: 

* after he types the command in the terminal \(if via [prompt](getting-started/commands/prompt.md)\) 
* before typing the command in the terminal \(if via [stdin](getting-started/commands/stdin.md)\) 

... before actually executing the formula.  
****

![](.gitbook/assets/fluxo-formulas%20%283%29.png)

## Execution of a formula \(with prompt\)

![](.gitbook/assets/rit-scaffold-generate-coffee-go.gif)

**`rit scaffold generate coffee-go`** is an executable command associated with a formula in the CLI's tree.

As it was the first time that the command was executed, it is possible to observe that Ritchie downloaded a config file and the formula's binary in sequence.

After downloading the files, Ritchie asked the user for some datas: 

* name
* type of coffee 
* delivery

Those datas are the **input** **parameters** of the formula.

Once these parameters were informed, the formula was successfully executed \(according to what the logs presented\).

## Command Tree

{% hint style="info" %}
Commands used in Ritchie are grouped according to a **tree**.   
  
****It is important to know this concept in order to actually understand the structure of the product.
{% endhint %}

In the case of Ritchie, the **Cobra** \(a Golang library\) pattern was followed using the following logic of building core commands:

                                                 **RIT + VERB + NOUN**

To allow more options and freedom for users, it is also allowed to follow the pattern below in the construction of formula commands:

                                        **RIT + GROUP + VERB + NOUN**

The app name is Ritchie, so we use the name **rit** to start our command tree.

![](.gitbook/assets/arvore-rit%20%281%29.png)

The **rit** command is therefore our parent command, or **root**. It is not executable \(it means that it will not start any operations if you use it alone in the terminal\). It is necessary to use executable sub-commands \(which are child commands, or branches, of the rit command\) in order to start any process.

The executable commands in Ritchie are the commands located at the last level of the tree.  
  
****For example, in the image above: 

* The **rit set context** command is executable, as it is at the last level of the tree. 
* The **rit kafka create** command is not executable as there is an executable **topic** subcommand, at the last level of the tree.

This command tree concept is the **core** of Ritchie's structure. All commands and sub-commands are mapped into a json that is updated or created when you download or update the CLI on your computer.

