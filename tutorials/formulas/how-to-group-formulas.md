---
description: 'In this section, you will understand how to  group formulas on Ritchie.'
---

# How to group formulas

## What is an aggregation?

On Ritchie, it is possible to **run formulas inside formulas.** This process is what we call **Formula aggregation.**‌

This functionality allows you, for example, to make operations in which you need to run consecutive formulas. 

Check out on the following topics how works this aggregation. 

## How to group?

### 1. Premisse

To group formulas, it is necessary to use **Standard Inputs**. On the following page, we have a detailed explanation to how this works: 

{% page-ref page="../standard-inputs/" %}

### 2. Execution <a id="2-execution"></a>

When [**implementing a formula**](https://app.gitbook.com/@zup-products/s/ritchie/~/diff/drafts/-MHIAf91S1RlTOvJs_KU/how-to/implement-a-formula/@drafts), the file where the operation is coded needs to execute a command line associated to a formula.‌

The grouped formula command line needs to be executed using **Standard Inputs**, which means informing the inputs parameters directly on the code.‌

### 3. Example <a id="3-example"></a>

The **`rit publish repo`** formula has been implemented using formula aggregation, that you can find its [**formula implementation**](https://github.com/ZupIT/ritchie-formulas/tree/master/publish/repo).

On the example below, you'll find below how this aggregation works on the code part, using **`Input flags`**.

{% hint style="warning" %}
This formula has been implemented using **`Shell`**and the reasoning would be the same for any other programming language.
{% endhint %}

```text
runFormula() {
  if [ "Github" == $PROVIDER ]
  then
    echo "🐙 Github provider selected"
    rit github publish repo --privacy=$PRIVACY --project_name=$PROJECT_NAME --workspace_path=$WORKSPACE_PATH --version=$VERSION
  elif [ "Gitlab" == $PROVIDER ]
  then
    echo "🦊 Gitlab provider selected"
    rit gitlab publish repo --privacy=$PRIVACY --project_name=$PROJECT_NAME --workspace_path=$WORKSPACE_PATH --version=$VERSION
  else
    echo "🤖 Unexpected Provider informed. Check it please and try again."
  fi
}
```

Here, according to the input informed by the user, two different formulas can be executed:‌

* **`rit github publish repo`**
* **`rit gitlab publish repo`**

To do so, the grouped formulas inputs parameters are informed dynamically according to the inputs parameters of the main formula \(**`rit publish repo`**\). 

Depending on the operation, the **`input flags`** used for the command could be generated according to other operations performed through the formula execution before executing the grouped formula command line.‌

## Next steps <a id="next-steps"></a>

You saw in this section how to use formula aggregation. If you want to keep reading about Ritchie's commands:‌

​👉 Check out the [**challenges**](../../challenges/what-are-these-challenges.md) we created to apply all the Ritchie concepts you learned.‌

​👉 Check out our [**list of commands**](../../reference/list-of-commands-and-flags.md) to see the available automations on our community repo.

