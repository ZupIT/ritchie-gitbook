---
description: 'In this section, you will find how to share formulas on Ritchie.'
---

# How to share formulas

## How to share?

Once a formula repository has been published, other users can add it locally from its **URL** to access its formulas.

**Example**: [**`https://github.com/ZupIT/ritchie-formulas`**](https://github.com/ZupIT/ritchie-formulas)\*\*\*\*

To add a new repository on Ritchie, it is necessary to run the command: 

```text
rit add repo
```

Once the repository has been added, Ritchie will use the selected release on the repository to access the available formulas.

![rit add repo command demonstration](../../.gitbook/assets/rit-add-repo-3.gif)

{% hint style="warning" %}
If the formula repository is **private**, the user will have to inform his Github / Gitlab token.
{% endhint %}

To **check** **the new added formulas command**, you can run the **`rit list repo`** command to check your new repository, and then run the **`rit --help`** command to take a look at new formulas groups that will appear.

## Next steps 

On this section, you saw how to share a formula on Ritchie. To keep configuring the formula: 

👉 Check out how to [**manipulate credentials**](https://docs.ritchiecli.io/how-to/manipulate-credentials) with your formulas.

👉 Check out our [**list of commands**](../../reference/list-of-commands.md) to see the available automations on our community repo. 

