---
description: >-
  This section gives more information about the formulas structure and their
  implementation with Ritchie.
---

# Formulas

## Introduction 

## Formula repositories

{% hint style="info" %}
Formulas are stored in **formula repositories**. 

These repositories need to have a particular structure.
{% endhint %}

Each repository must contain the following elements: 

* the formula folders. 
* a tree folder 
* a Makefile file 
* a copy-bin-configs.sh file 
* an unzip-bin-configs.sh file

![](../../.gitbook/assets/repo.png)

Each **formula folder** will contain the executable code and files for a formula.

The **tree** folder is composed of a **tree.json** file that will contain the command tree of all formulas in the repository.

The **Makefile** file contains a reference to all formulas in the repository, as well as an executable command manipulating the files **copy-bin-configs.sh** and **unzip-bin-configs.sh**, in order to generate the executable files needed to test the formula\(s\) locally inside the [.rit folder]().

## Formula composition

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



![](../../.gitbook/assets/fluxo-cli%20%281%29.png)

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
It is possible to configure the priority between the repositories in the **repo** folder of the [.rit folder]() where you have a configurable repositories.json file. 

For more information on how to manipulate [repositories](repository.md), check out the documentation here: Repository.
{% endhint %}

