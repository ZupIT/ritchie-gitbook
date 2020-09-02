---
description: You will find in this section how to initialize rit.
---

# Initialize rit

### Step 1: Initialization

You must execute the following command to initialize Ritchie: 

```text
rit init
```

This command will ask the user two questions:

* if he wants to contribute anonymously to Ritchie metrics.
* if he wants to add the community formulas locally.

![rit init command](../.gitbook/assets/rit-init-optimized.gif)

Then, the command execution will create all the necessary configuration's files. 

### Step 2: Verify Initialization

#### 2.1 Commons repository

If you added the community formulas repository, you can check it by using the following command:

```text
rit list repo
```

This command will return all formulas repositories the user has access locally.

![rit list repo command](../.gitbook/assets/large-gif-1448x466-.gif)

#### 2.2 Ritchie folder

You can then check the **`.rit`** folder has been created on your **`$HOME`** directory.

{% hint style="info" %}
All operations done using Ritchie will be saved in this **.rit** **folder** \(credentials, repos, metrics...\)
{% endhint %}

