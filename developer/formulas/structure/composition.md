# Composition

{% hint style="info" %}
Each formula is composed of several files allowing its execution by the CLI.
{% endhint %}

For a formula to be executed by the terminal, it is necessary to have: 

* The tree.json file of the repository where the configured formula is located 
* A config.json file 
* An executable file

The **tree.json** file allows the CLI to know the commands and sub-commands associated with the formula. This is how it identifies where to download the formula files on the first execution \(on demand\).

The **config.json** file contains the formula's input parameters. It allows the CLI to know what datas to ask the user when he executes the command in the terminal in order to process the formula correctly.

The **executable file** contains the implementation of the formula. The CLI will download this file according to the operating system of the user's computer and execute this formula sending the input parameters that have been informed.

