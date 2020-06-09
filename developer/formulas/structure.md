# Tree.json

{% hint style="info" %}
**Each** Ritchie formula repository has a **command tree**.

This command tree is configured in a file called **tree.json**
{% endhint %}

## Structure

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

{% page-ref page="access-to-formulas.md" %}

{% page-ref page="config.json.md" %}

{% page-ref page="priority.md" %}

