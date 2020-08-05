---
description: You will find in this section how to run formulas on Ritchie.
---

# How to run a formula

## How to run?

{% hint style="warning" %}
The formulas are executed locally by default, which means that you must have installed the programming languages dependencies to run a formula's code. 

For example, to run a formula written on Node, you have to have Node installed on your machine. 
{% endhint %}

That means all formulas can be executed regardless of the programming language used from the moment that you have **Docker** installed.

To run the formula, just use the command below:

```text
$ rit github update repository
```

![](../.gitbook/assets/rit-update-repo-3.gif)

In case you want to run a formula using Docker, just run the command adding the **flag --docker**.

```text
$ rit github update repository --docker
```

## Next steps 

On this section, you saw how to publish a formula on Ritchie. To keep learning abour Ritchie: 

👉 Check out our [**list of commands**](../developer/list-of-commands.md) to see the available automations on our community repo. 

