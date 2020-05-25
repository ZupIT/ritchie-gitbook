---
description: >-
  In this section, you will find initial information about Ritchie before
  delving into the product.
---

# Overview

{% hint style="info" %}
Ritchie is a **CLI** \(Command Line Interface\) which allows to **create**, **store** and **share** automations **efficiently** and **securely**, with a team or with the whole community.
{% endhint %}

{% embed url="https://www.youtube.com/watch?v=5S9CHC3QarQ&feature=youtu.be" %}

## Installation

{% page-ref page="getting-started/installation/linux.md" %}

{% page-ref page="getting-started/installation/windows.md" %}

{% page-ref page="getting-started/installation/macos.md" %}

## **Where Ritchie came from?**

Ritchie's objective is to improve the developer’s experience, bringing them more autonomy, automating and simplifying the execution of commands that are widely used in the process of creating and developing digital products. Its name is a tribute to **Dennis Ritchie**, one of the creators of Unix \(predecessor of Linux\) and also of the C language. One of the pioneer of the digital world as we know it today.  
  
Despite the number of multidisciplinary teams in the market, a great challenge still is to reduce the dependence that developers have on inputs coming from the infrastructure and operations teams. **DevOps** did a lot to remedy this bottleneck, but it did not completely eliminate the dependency between areas.

{% hint style="warning" %}
With that in mind, we bring a tool to the community that promotes a **NoOps** movement, a solution that automates repetitive operations and streamlines processes \(also known as toil\) that are often hampered in the infrastructure. This will give developers the ability to perform operations that were exclusively the infrastructure's domain.
{% endhint %}

In that way, professionals - on all fronts - gain time to work on more complex and relevant tasks to generate value for their project.

![Demonstration of a formula following the NoOps mindset](.gitbook/assets/rit-demo-deploy-project%20%281%29.gif)

## **What does Ritchie do?**

{% hint style="warning" %}
The tool allows you to create **formulas** that, in other terms, represent programs and /or commands that will facilitate the daily programming work.
{% endhint %}

Let’s take as an example a _microservices_ web application that process payments. In general, the common process for executing this project is to create a whole previous infrastructure, defining a language in the system that will be programmed, downloading dependencies and defining the rules that should be used for the project.

![WITHOUT Ritchie](.gitbook/assets/en-sem-ritchie.png)

**With Ritchie**, it's possible to define this configuration using a formula, creating this infrastructure directly by a command line, which in this case will delivered all the structure of the project with all files automatically configured. That helps on avoiding an important time spent on infrastructure and configurations.

Another example - _quite common in teams that operate through **DevOps**_ - is that developers who depend on the infrastructure team to release logs and thus access and operate a system that is in production. When using Ritchie, it is possible to create formulas with access to this system, making the logs available to any user on his terminal.

This, especially in cases of onboarding into development teams, is very advantageous in order to release the permitted accesses and allow developers to start producing as soon as they are integrated into the project.

![WITH Ritchie](.gitbook/assets/en-com-ritchie.png)

## **What makes Ritchie unique ?**

Because it is a CLI tool, Ritchie seeks to improve the operational **experience of developers** to its maximum, simplifying repetitive and easy-to-execute tasks that, in many cases, demand a lot of professionals to remember all commands, in addition to their parameters and arguments.

The objective was to reduce the rework of looking for this information in documentation and, thus, promote more time for the development team to focus on their deliveries.

So, instead of writing down on the command lines which parameters and / or arguments the user needs to inform, we do the opposite: Ritchie presents the available options and goes, line by line, asking for the information needed for the command to work, in an interactive way.

{% hint style="warning" %}
In addition, Ritchie works as a **single repository of formulas**. While other CLIs are usually focused on operations related to a single application, in Ritchie you can find, in one place, the operations related to all your registered formulas.
{% endhint %}

In addition, Ritchie works as a single repository of formulas. While other CLIs are usually focused on operations related to a single application, in Ritchie you can find, in one place, the operations related to all your registered formulas.

In the example below, we have the execution of a scaffold command with the coffee formula. As the user signals which formula he wants to use, the system automatically passes, line by line, asking which specific parameters must be considered to perform the desired action.  


![](https://lh3.googleusercontent.com/joDVqE3Km8ePNO0j7vNvfwvZVHJ8mqq9l4x4Webot9pGDdjyoo6BTp7hr39PEb9EBLC43RhsDkIs_7GmxU_YT2KmSCkhOtmJWxtSA6uGEz0a-7Ar4Bfi5zvHkgy2zaMyRkHNle8w)





