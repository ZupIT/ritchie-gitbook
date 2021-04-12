---
description: You will find in this section how to run a "hello-world" formula.
---

# "Hello World" formula

## Hello World

{% hint style="warning" %}
**Premisse**: After you finished the previous steps -[**installation**](../../../getting-started/install-cli/) **and** [**initialization**](../../../getting-started/initialize-cli.md) **- to access the** [**hello-world formula**](https://github.com/ZupIT/ritchie-formulas/tree/master/demo/hello-world) **\*\*to test Ritchie, you'll need to add the \[**ritchie-formulas-demo**\]\(**[https://github.com/ZupIT/ritchie-formulas-demo](https://github.com/ZupIT/ritchie-formulas-demo)**\) repository** `locally`\*\*.
{% endhint %}

To do so, you can use the **`rit add repo`** command, or execute the command line below:

```text
rit add repo --provider=Github --name=demo --repoUrl=https://github.com/ZupIT/ritchie-formulas-demo --priority=1
```

{% hint style="info" %}
You can also check which repositories you're using with the**`rit list repo`** command.
{% endhint %}

**Now that you have added the `demo` repository and check the details of the formula, you can execute this tutorial commands.**

### **Premisse: Check the formula's details**

To get details about a formula, you can execute the command using with the `--help` flag:

```text
rit demo hello-world --help
```

It will return all the flags available for the command execution.

#### On Ritchie, you have 6 possibilities to run a formula through those flags:

1. Using Prompt
2. Using Prompt and Docker 
3. Using Input Flags
4. Using Input Flags and Docker 
5. Using Stdin
6. Using Stdin and Docker 

To do so, type the following commands lines:

### Case 1: With Prompt

{% hint style="warning" %}
As **this formula has been coded using Golang**, it is necessary to have **Golang** installed on your computer to run it **locally**.
{% endhint %}

```text
rit demo hello-world
```

Select an option for each input parameter and see how the magic works:

![rit demo hello-world](../../../.gitbook/assets/large-gif-1054x366-%20%281%29.gif)

This is the default command line execution, that runs the formula locally using **prompt** to inform the input parameters.

### Case 2: With Prompt and Docker

You can run the same command using the **--docker** flag to execute it remotely \(on a container\), but still using **prompt** to inform the inputs parameters:

```text
rit demo hello-world --docker
```

{% hint style="warning" %}
**Docker** needs to be installed and running on your computer for this flag to work.  
In that case, you won't need to have **Golang** installed.
{% endhint %}

### Case 3: With Input Flags

You can also run the command informing the inputs through flags \(you can know which flags are available using the **`--help`** flag when executing a command\). This way, inputs parameters are informed directly with the command line.

```text
rit demo hello-world --rit_input_text=Dennis --rit_input_boolean=true --rit_input_list=everything --rit_input_password=Ritchie
```

{% page-ref page="../../standard-inputs/how-to-use-input-flags/" %}

### Case 4: With Input flags and Docker

When you combine both **`input flags`** and the **`--docker`** flag, it is possible to run a command remotely \(on a container\) with the input parameters directly informed on the command line:

```text
rit demo hello-world --rit_input_text=Dennis --rit_input_boolean=true --rit_input_list=everything --rit_input_password=Ritchie --docker
```

### Case 5: With Stdin

You can also run the command with the **--stdin** \(Standard input\) flag. This way, inputs parameters are also informed directly with the command line.

```text
echo '{"rit_input_text":"Dennis", "rit_input_boolean":"true", "rit_input_list":"everything", "rit_input_password":"Ritchie"}' | rit demo hello-world --stdin
```

{% hint style="warning" %}
Ritchie uses the **JSON** format to execute STDIN commands
{% endhint %}

{% page-ref page="../../standard-inputs/how-to-use-the-stdin-flag/" %}

### Case 6: With Stdin and Docker

When you combine both **--stdin** and **--docker** flags, it is also possible to run a command remotely \(on a container\) with the input parameters directly informed on the command line:

```text
echo '{"rit_input_text":"Dennis", "rit_input_boolean":"true", "rit_input_list":"everything", "rit_input_password":"Ritchie"}' | rit demo hello-world --stdin --docker
```

{% hint style="info" %}
Take a look at the formulas repositories \(ex: [**ritchie-formulas**](https://github.com/ZupIT/ritchie-formulas)\).

Most of the community formulas are composed of a [**README file**](https://github.com/ZupIT/ritchie-formulas/tree/master/demo/hello-world) explaining what the command does and how to run it.
{% endhint %}

## Next steps

In this section, you saw how to run formulas on Ritchie. To keep learning:

👉Check which formulas you can run using the following command:

```text
rit --help
```

👉See [**how to create new formulas**](../how-to-create-formulas.md).

