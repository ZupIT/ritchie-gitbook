---
description: 'In this section, you will find a path to how run formulas using Ritchie.'
---

# How to run formulas

## How to run?

There are two ways to run formulas on Ritchie :

1. Locally
2. Using Docker

The **default formulas execution method** has been defined during the initialization step with the**`rit init`**command. It can be changed executing the following command:

```text
rit set formula-runner
```

![rit set formula-runner command](../../../.gitbook/assets/large-gif-1374x404-.gif)

### 1. Locally

To run a formula locally it is necessary to have the formula programming languages dependencies installed on the computer.

**Example**: a ****formula written in **Node** will need **Node installed** on the computer, so it will be able to run locally.   


### 2. Through Docker

All formulas can run regardless the programming language used from the moment you have **`DOCKER`** installed and running.

{% hint style="info" %}
Check out on the following example [**how to run a "Hello World" formula** ](hello-world-formula.md)\*\*\*\*
{% endhint %}

{% hint style="warning" %}
**Docker user on MacOS:** To avoid the **‘Error: exit status 1’**, you have to **disable** the Cloud Experience, depending on your version. See how: 

Access on Docker: 

* Preferences &gt; Command Line &gt; Enable cloud experience.
{% endhint %}

###  3. Local & Docker Flags

You can force Ritchie CLI to execute a formula with a specific method using flags.

* The **`--local`** flag will execute a formula with locally \(if the default method is Docker\). 
* The **`--docker`** flag will execute a formula with Docker \(if the default method is local\). 

### 4. Containers with Ritchie

{% hint style="warning" %}
All formulas templates contain a **Dockerfile** which creates a container with **Ritchie CLI** installed.
{% endhint %}

## Next steps 

On this section, you saw how to run a formula on Ritchie. To keep learning:

👉 Go to [**Hello World formula**](hello-world-formula.md) to see different ways to run a formula on Ritchie. 

👉 Go to the [**create formulas**](../how-to-create-formulas.md) section to understand how to create your first automation with Ritchie.

