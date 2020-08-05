---
description: You will find in this section how to publish formulas on Ritchie.
---

# How to publish a formula

## How to publish?

To publish a formula, you need to push it on **Github / Gitlab**, following these steps:

1. Create an exclusive repository for formulas \(it can be the repository created locally\) on Github / Gitlab.
2. Add a formula on the repository
3. Generate a release
4. Add the repository on Ritchie running the command: 

```text
$ rit add repo
```

Once the repository has been added, Ritchie will automatically use the latest release on your repository to access the available formulas.

![](../.gitbook/assets/rit-add-repo-3.gif)

## Next steps 

On this section, you saw how to publish a formula on Ritchie. To keep configuring the formula: 

👉 Go to [**run a formula**](run-a-formula.md) to see how to proceed with formula's executions with Ritchie. 

👉 Check out our [**list of commands**](../developer/list-of-commands.md) to see the available automations on our community repo. 

