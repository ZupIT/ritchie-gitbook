---
description: You will find in this section how to run a "hello-world" formula.
---

# "Hello World" formula

## Hello World

After you finished the previous steps - __[**installation**](../../getting-started/installation/) ****and ****[**initialization**](../../getting-started/initialization.md) ****- the ****[**hello-world formula**](https://github.com/ZupIT/ritchie-formulas/tree/master/demo/hello-world) ****will be available ****to test Ritchie.

{% hint style="warning" %}
This command is available since [**release 2.0.1**](https://github.com/ZupIT/ritchie-formulas/releases) of [**ritchie-formulas**](https://github.com/ZupIT/ritchie-formulas) repository. 

You can check which version of the repository you're using with the**`rit list repo`** command.
{% endhint %}

On Ritchie, you have 4 possibilities to run a formula: 

1. Using Prompt
2. Using Prompt and Docker 
3. Using Stdin
4. Using Stdin and Docker 

To do so, type the following commands lines: 

### Case 1: With Prompt

{% hint style="warning" %}
As **this formula has been coded using Golang**, it is necessary to have **Golang** installed on the computer to execute it **locally**.
{% endhint %}

```text
rit demo hello-world
```

Select an option for each input parameter and see how the magic works: 

![rit demo hello-world](../../.gitbook/assets/large-gif-1054x366-%20%281%29.gif)

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

### Case 3: With Stdin

You can also execute the command with the **--stdin** \(Standard input\) flag. That way, inputs parameters are informed directly with the command line. 

```
echo '{"input_text":"Dennis", "input_bool":"false", "input_list":"everything", "input_password":"Ritchie"}' | rit demo hello-world --stdin
```

{% hint style="warning" %}
Ritchie uses the **json format** to execute STDIN commands
{% endhint %}

{% page-ref page="../how-to-use-the-stdin-flag/" %}

### Case 4: With Stdin and Docker

When you combine both **--stdin** and **--docker** flags, it is finally possible to run a command remotely \(on a container\) with the input parameters directly informed on the command line:

```text
echo '{"input_text":"Dennis", "input_bool":"false", "input_list":"everything", "input_password":"Ritchie"}' | rit demo hello-world --stdin --docker
```

{% hint style="info" %}
Take a look at the formulas repositories \(ex: [**ritchie-formulas**](https://github.com/ZupIT/ritchie-formulas)\). 

Most of the community formulas are composed of a [**README file**](https://github.com/ZupIT/ritchie-formulas/tree/master/demo/hello-world) explaining what the command does and how to execute it.
{% endhint %}

## Next steps

In this section, you saw how to run formulas on Ritchie. To keep learning: 

👉Check which formulas you can run using the following command:

```text
rit --help
```

👉See [**how to create new formulas**](../how-to-create-formulas.md).

