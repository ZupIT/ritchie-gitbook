---
description: You will find in this section how to publish formulas on Ritchie.
---

# How to publish formulas

## How to publish?

To publish a formula, you need to push it on **Github / Gitlab**, following these steps:

1. Create an exclusive repository for formulas \(it can be the repository created locally\) on Github / Gitlab.
2. Add a formula on the repository
3. Generate a release

## How to share?

1. Add the repository on Ritchie running the command: 

```text
rit add repo
```

Once the repository has been added, Ritchie will automatically use the latest release on your repository to access the available formulas.

![rit add repo command demonstration](../.gitbook/assets/rit-add-repo-3.gif)

{% hint style="info" %}
To **check** **the new added formulas command**, execute the **`rit --help`** command and take a look at new groups that will appear.
{% endhint %}

## Next steps 

On this section, you saw how to publish a formula on Ritchie. To keep configuring the formula: 

👉 Check out how to [**manipulate credentials**](https://docs.ritchiecli.io/how-to/manipulate-credentials) with your formulas.

👉 Check out our [**list of commands**](../developer/list-of-commands.md) to see the available automations on our community repo. 

