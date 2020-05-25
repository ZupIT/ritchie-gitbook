# Command tree

{% hint style="info" %}
Commands used in Ritchie are grouped according to a **tree**.   
  
****It is important to know this concept in order to actually understand the structure of the product.
{% endhint %}

In the case of Ritchie, the **Cobra** \(a Golang library\) pattern was followed using the following logic of building core commands:

                                                 **RIT + VERB + NOUN**

To allow more options and freedom for users, it is also allowed to follow the pattern below in the construction of formula commands:

                                        **RIT + GROUP + VERB + NOUN**

The app name is Ritchie, so we use the name **rit** to start our command tree.

![](../.gitbook/assets/arvore-rit%20%281%29.png)

The **rit** command is therefore our parent command, or **root**. It is not executable \(it means that it will not start any operations if you use it alone in the terminal\). It is necessary to use executable sub-commands \(which are child commands, or branches, of the rit command\) in order to start any process.

The executable commands in Ritchie are the commands located at the last level of the tree.  
  
****For example, in the image above: 

* The **rit set context** command is executable, as it is at the last level of the tree. 
* The **rit kafka create** command is not executable as there is an executable **topic** subcommand, at the last level of the tree.

This command tree concept is the **core** of Ritchie's structure. All commands and sub-commands are mapped into a json that is updated or created when you download or update the CLI on your computer.

