---
description: 'In this section, you will find how to initialize Ritchie CLI.'
---

# Initialize CLI

## Step 1: Initialization

Run the following command to initialize Ritchie: 

```text
rit init
```

This command will ask the user three questions:

1. If he **wants to contribute anonymously** to Ritchie metrics.
2. If he **wants to add the community** formulas locally.
3. If he **wants the default** [**formula execution method**](../tutorials/formulas/how-to-run-formulas/) **to be local or through docker.** 

![rit init command](../.gitbook/assets/rit-init%20%283%29%20%281%29.gif)

Then, the command execution will create all the necessary configuration's files. 

## Step 2: Verify Initialization

### 1. Commons repository

If you added the community formulas repository, you can check it by using the following command:

```text
rit list repo
```

This command will return all formulas repositories the user has access locally.

![rit list repo command](../.gitbook/assets/large-gif-1448x466-.gif)

### 2. Ritchie folder

You can then check the **`.rit`** folder has been created on your **`$HOME`** directory.

{% hint style="info" %}
All operations done using Ritchie will be saved in this **.rit** **folder** \(credentials, repos, metrics...\)
{% endhint %}

