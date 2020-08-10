---
description: You will find in this section how to run a "hello-world" formula.
---

# Run the "hello-world" formula

After you finished the previous steps - __[**installation**](installation/) ****and ****[**initialization**](initialization.md) ****- you can run the ****[**hello-world formula**](https://github.com/ZupIT/ritchie-formulas/tree/master/demo/hello-world) ****to test Ritchie.

To do so, type the following commands lines: 

{% hint style="warning" %}
This command is available since [release 2.0.1](https://github.com/ZupIT/ritchie-formulas/releases) of ritchie-formulas repository. You can check which version of the commons repository you're using with the**`rit list repo`** command.
{% endhint %}

### With Prompt

```text
rit demo hello-world
```

Select an option for each input parameter and see how the magic works: 

![rit demo hello-world](../.gitbook/assets/large-gif-1054x366-%20%281%29.gif)

This is the default command line execution, that runs the formula locally using **prompt** to inform the input parameters.

### With Docker

You can run the same command using the **--docker** flag to execute it remotely \(on a container\), but still using **prompt** to inform the inputs parameters:

```text
rit demo hello-world --docker
```

{% hint style="warning" %}
**Docker** needs to be installed and running on your computer for this flag to work.
{% endhint %}

### With Stdin

You can also execute the command with the **--stdin** \(Standard input\) flag. That way, inputs parameters are informed directly with the command line. 

```
echo '{"input_text":"Dennis", "input_bool":"false", "input_list":"false", "input_password":"Ritchie"}' | rit demo hello-world --stdin
```

{% hint style="warning" %}
Ritchie uses the **json format** to execute STDIN commands
{% endhint %}

### Using Stdin + Docker

When you combine both **--stdin** and **--docker** flags, it is finally possible to run a command remotely \(on a container\) with the input parameters directly informed on the command line:

```text
echo '{"input_text":"Dennis", "input_bool":"false", "input_list":"false", "input_password":"Ritchie"}' | rit demo hello-world --stdin --docker
```

{% hint style="success" %}
Take a look at the formulas repositories \(ex: [**ritchie-formulas**](https://github.com/ZupIT/ritchie-formulas)\). 

Most of the community formulas are composed of a [**README file**](https://github.com/ZupIT/ritchie-formulas/tree/master/demo/hello-world) explaining what the command does and how to execute it.
{% endhint %}

