---
description: >-
  This section gives more information about the formulas structure and their
  implementation with Ritchie.
---

# Formulas

## Introduction

The formulas are, in Ritchie's context, the automation that can be executed to make an action in a short time, but more efficiently. 

{% hint style="info" %}
To get to know more about our current formulas on Ritchie, access the repository [**ritchie-formulas**](https://github.com/ZupIT/ritchie-formulas) ****on Github.
{% endhint %}

## Formula repositories

Formulas are stored in **formula repositories,** that need to have a particular structure.

Each repository must contain the following elements: 

* the formula folders. 
* a tree folder 
* a Makefile file 
* a copy-bin-configs.sh file 
* an unzip-bin-configs.sh file

![](../.gitbook/assets/repo.png)

Each **formula folder** will contain the executable code and files for a formula.

The **tree** folder is composed of a **tree.json** file that will contain the command tree of all formulas in the repository.

The **Makefile** file contains a reference to all formulas in the repository, as well as an executable command manipulating the files **copy-bin-configs.sh** and **unzip-bin-configs.sh**, in order to generate the executable files needed to test the formula\(s\) locally inside the [.rit folder]().

### Formula composition

{% hint style="info" %}
Each formula is composed of several files allowing its execution by the CLI.
{% endhint %}

For a formula to be executed by the terminal, it is necessary to have: 

* The tree.json file of the repository where the configured formula is located 
* An executable file
* A config.json file 

The **tree.json** file allows the CLI to know the commands and sub-commands associated with the formula. This is how it identifies where to download the formula files on the first execution \(on demand\).

The **executable file** contains the implementation of the formula. The CLI will download this file according to the operating system of the user's computer and execute this formula sending the input parameters that have been informed.

The **config.json** file contains the formula's input parameters. It allows the CLI to know what datas to ask the user when he executes the command in the terminal in order to process the formula correctly.

#### Config.json

This file contains the following information: 

* a description 
* the formula input parameters 

These input parameters are made up of the following fields: 

* name 
* type
* label 
* default \(optional\) 
* items \(optional\) 
* cache \(optional\)

```text
{
  "description": "Sample inputs in Ritchie.",
  "inputs" : [
    {
      "name" : "sample_text",
      "type" : "text",
      "label" : "Type : ",
      "cache" : {
        "active": true,
        "qty" : 6,
        "newLabel" : "Type new value. "
      }
    },
    {
      "name" : "sample_list",
      "type" : "text",
      "default" : "in1",
      "items" : ["in_list1", "in_list2", "in_list3", "in_listN"],
      "label" : "Pick your : "
    },
    {
      "name" : "sample_bool",
      "type" : "bool",
      "default" : "false",
      "items" : ["false", "true"],
      "label" : "Pick: "
    }
  ]
}
```

The **name** field refers to the name of the variable that will be extracted when implementing the formula. 

The **type** field represents the type of the variable \(currently there is only TEXT and BOOL\) 

The **label** field is the text that will appear to the user via PROMPT to inform this variable. 

The **default** field is the value of the variable that will come by default if the choice is a list of options. 

The **items** field is the list of possible options for the variable. 

The **cache** field allows to configure whether it is necessary to store the user's choices for this variable. It consists of 3 fields: 

* active 
* qty 
* newLabel. 

The **active** field indicates whether the cache is enabled or not. 

The **qty** field refers to the number of choices that can be stored in the cache.

The **newLabel** field is for the user to enter another value for the variable if those saved in the cache do not meet their needs.

### Tree.json

{% hint style="info" %}
**Each** Ritchie formula repository has a **command tree**.

This command tree is configured in a file called **tree.json**
{% endhint %}

It is through these JSON \(s\) that the CLI will be able to identify the commands it has access to, and the necessary datas to download the executables of the formulas.

The structure of a tree.json is as follows:

```text
{
  "commands": [
    {
      "usage": "aws",
      "help": "Apply Aws objects",
      "parent": "root"
    },
    {
      "usage": "apply",
      "help": "Apply Aws objects",
      "parent": "root_aws"
    },
    {
      "usage": "terraform",
      "help": "Apply Aws terraform objects",
      "formula": {
        "path": "aws/terraform",
        "bin": "terraform-cli-${so}",
        "bundle": "${so}.zip",
        "repoUrl": "https://commons-repo.ritchiecli.io/formulas"
      },
      "parent": "root_aws_apply"
    }
  ]
}
```

Let's continue with the example of the command `RIT AWS APPLY TERRAFORM`

Each command contained in this list can contain up to 4 parameters: 

* usage 
* help 
* parent 
* formula

The **usage** field refers to the word used in the command \(aws, apply and terraforma in the example\).

The **help** field represents the help message that will appear to the user if he enters this command.

The **parent** field indicates the previous commands in the tree, possibly using an underline \(\_\) to separate the commands. ROOT being a reserved word referring to the RIT command.

When a command contains only these 3 fields \(**usage, help, parent**\) it means that it is not executable, and that it is only part of a set of commands that together will execute a formula.

The **formula** field will contain the necessary information for the CLI to identify where to look for the executables needed to execute the formula. It consists of 3 fields:

* repoUrl 
* path 
* bin

The **repoUrl** field refers to the address where the formula's executable files are located.

{% hint style="warning" %}
It is important to note that Ritchie does not download all formulas at its installation. The CLI only downloads the executables of the formulas on demand, that is, when it executes the formulas commands for the first time.
{% endhint %}

The **path** field indicates the folder that will be created locally on the user's computer to add these executable files. 

The **bin** field tells you the name of the executable file that the CLI should download, according to the operating system \(OS\) of the user's machine. 

Running the commands from the AWS formula above, it is possible to get the following scenarios:

* `rit aws` 

```text
Apply Aws objects

Available Commands:
  apply       Apply Aws objects

Use "rit <command> --help" for more information about a given command.
```

* `rit aws apply`

```text
Apply Aws objects

Available Commands:
  terraform   Apply Aws terraform objects

Use "rit <command> --help" for more information about a given command.
```

* `rit aws apply terraform`

```text
Downloading config file...
Done.
Download formula...
Done.
Installing formula...
Directory Created: /Users/Dennis/.rit/formulas/aws/terraform/bin
File extracted: bin/terraform-cli-darwin
Done.
Use the arrow keys to navigate: ↓ ↑ → ←
Select your repository URL:
  ▸ https://github.com/zupit/iti-stack-core
    https://github.com/zupit/iti-stack-tools
```

The first commands \(**`rit aws`** and **`rit aws apply`**\) returned the help field associated with the command in tree.json, as soon as the available sub-commands for the user to execute a formula. 

The **`rit aws apply terraform`** command downloaded the formula's executables and started asking the user for input parameters.

### Makefile e Shellscripts

Those 3 files are used to generate files locally on the .rit folder when the user need to test the automation code he has implemented.

* Makefile 
* copy-bin-configs.sh file 
* unzip-bin-configs.sh file

When creating the new formula, the path where the formula is located in the repository have to be informed in the **Makefile** of the root of the repository, as the following example :

```text
#Makefiles

SC_SPRING_STARTER=scaffold/spring-starter
KAFKA=kafka
DOCKER=docker/compose

FORMULAS=$(SC_SPRING_STARTER) $(KAFKA) $(DOCKER)
```

In this file there is also a `test-local` command that allows the user to generate the executable files of one or more formulas and place them in the temporary Ritchie folder \(.rit\) located in the home of the user's machine.

```text
test-local:
ifneq ("$(FORM)", "")
	@echo "Using form true: "  $(FORM_TO_UPPER)
	$(MAKE) bin FORMULAS=$(FORM)
	mkdir -p $(HOME)/.rit/formulas
	rm -rf $(HOME)/.rit/formulas/$(FORM)
	./unzip-bin-configs.sh
	cp -r formulas/* $(HOME)/.rit/formulas
	rm -rf formulas
else
	@echo "Use make test-local form=NAME_FORMULA for specific formula."
	@echo "form false: ALL FORMULAS"
	$(MAKE) bin
	rm -rf $(HOME)/.rit/formulas
	./unzip-bin-configs.sh
	mv formulas $(HOME)/.rit
endif
	mkdir -p $(HOME)/.rit/repo/local
	rm -rf $(HOME)/.rit/repo/local/tree.json
	cp tree/tree.json  $(HOME)/.rit/repo/local/tree.json
```

The **copy-bin-configs.sh** and **unzip-bin-configs.sh** are actually manipulated by the **test-local** command to extract the executable files and **config.json** of the chosen formulas, and move them to the **.rit folder**.

#### There are 2 ways to use this Makefile command:

Informing the specific formula to test, according to the name informed in the Makefile:

```text
make test-local form={nome_formula} 
```

Executing directly the **test-local** script to add all formulas from the repository to the temporary .rit folder :

```text
make test-local
```

After adding the formula in .rit through the Makefile \(main\), it will be possible to execute the command associated with that formula through the terminal \(auto-completion will not work in this case\).

## Access to formulas

{% hint style="info" %}
All commands **accessible through the CLI** can be observed through the _Helper_
{% endhint %}

```text
➜ rit --help

A CLI that developers can build and operate
your applications without help from the infra staff.
Complete documentation is available at https://github.com/ZupIT/ritchie-cli

core commands:
  add         add objects
  completion  Add autocomplete for terminal
  clean       clean objects
  create      Create objects
  delete      Delete objects
  list        list objects
  set         Set objects
  show        Show objects
  update      update objects

commons commands:
  aws         Apply Aws objects
  docker      Manipulate docker objects
  github      Manipulate GitHub objects
  k8s         Manipulate k8s objects
  kafka       Kafka commands
  scaffold    Manipulate scaffold objects

Other Commands:

Options:
  -v, --version: version for rit

Usage:
  rit [flags] [options]

Use "rit <command> --help" for more information about a given command.
```

When a user will download Ritchie \([Single]() version\) or execute the `rit login` command \([Team]() version\) to access an organization's repositories, the CLI will download and merge the tree.json from the formula repositories to which the user has access.



![](../.gitbook/assets/fluxo-cli%20%281%29.png)

The junction of the repository trees will be the tree of all commands available via the CLI on the user's computer, which is presented in the _Helper_.

## Priority between repositories

{% hint style="info" %}
There is a concept of **priority** among the command trees of the **formula repositories**. 

This makes it possible to **avoid repetitive commands** after joining the trees of all commands by the CLI.
{% endhint %}

Here is the **default priority** defined in the CLI among the repositories:

* Priority 0: Core 
* Priority 1: Location 
* Priority 2: Other repositories

This rule allows each user \(_single_\) / organization \(team\) to define the priority among the other repositories.

### Example

It is possible for a user to choose between the 2 scenarios below:

![](https://lh4.googleusercontent.com/HjfbyCr7FUbOrhlx7uEqr7-fgjmVbivXPSk9X3CD92BPtF4sgy4ojBl4-HKAzAcI7OGacCGWVzMJCDPh_IfS8y3520_i-TwccY2PQEqrnXgrZKcSdBiOyEjBwzB1Uy9E1b3KQaPL)![](https://lh5.googleusercontent.com/Oc1HatluaibDzbcfd0N34oERi8al1zsJj6qB4XDNpueoP5xgizDIarZmQ2BoGCXFp0K-g5QnQC6-pn1eQFoO15QKmQEOklfJ_AdK7hN0EeHpK7T3HrIm_wN0G_rNcbN6LP7VFBDK)

#### **Scenario 1**

Priority would be given to commons commands over your team's commands.

#### S**cenario 2**

Priority would be given to team commands over commons commands. This would allow, for example, a user / team to use a command that is in the **ritchie-formulas** \(commons\) repository tree for a formula in their repository, performing a different operation with the same command, since it would have priority.

{% hint style="warning" %}
It is possible to configure the priority between the repositories in the **repo** folder of the [.rit folder](cli.md) where you have a configurable repositories.json file. 

For more information on how to manipulate [repositories](../getting-started/commands/using-first-commands/repositories.md), check out the documentation here: Repository.
{% endhint %}

