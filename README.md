---
description: >-
  You will find in this section all initial information about Ritchie before
  getting deeper into the product.
---

# Overview

## What is Ritchie?

Ritchie is an **open source framework** that creates and tweaks a CLI for your team. It allows you to easily create, build and share formulas.

{% embed url="https://youtu.be/PtKFco2pIqs" %}

## **Versioning** 

Currently, Ritchie has **two available versions** to be used. On this documentation, we'll focus on **Ritchie** **version 2.0.**

### **What's new?**

The main differences on this current version are: 

* You don't need to upload binaries to cloud storage because all formulas will be hosted on Github or Gitlab
* You can version your formulas using git tags 
* The command tree will be dinamically generated on the added repositories. So, you won't need to edit a tree.json file. 
* The formulas build will be more stable for Windows \(without using other tools' dependencies\)
* The formula execution will be possible through container and you can also keep the pattern of running without container. 
* You can use a command to list all credentials setted 
* You have a tutorial to guide you with CLI tips. 
* You have an autocomplete support for 2 new shells \(fish e powershell\)

## **How does Ritchie work?**

In a general context, the common process for executing a project is to create a whole previous infrastructure, defining a language in the system that will be programmed, downloading dependencies and defining the rules that should be used for the project.

![WITHOUT Ritchie](.gitbook/assets/en-sem-ritchie.png)

**With Ritchie**, it's possible to define this configuration using a formula, creating this infrastructure directly by a command line, which in this case will delivered all the structure of the project with all files automatically configured. That helps on avoiding an important time spent on infrastructure and configurations.

![WITH Ritchie](.gitbook/assets/en-com-ritchie.png)

