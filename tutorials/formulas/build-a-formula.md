---
description: 'In this section, you will find how to build formulas on Ritchie.'
---

# How to build formulas

{% hint style="danger" %}
This functionality is no longer available from Ritchie's 2.5.0 version. From now on, a formula build is automatically made on your CLI. 

If you're using a previous version just follow the instructions of this section.
{% endhint %}

## How to build?

After [**creating a formula**](how-to-create-formulas.md),  if you want to edit the code of the formula, it's necessary to **build** these changes to test the command with the new implementation. 

To do so, just run the command:  ****

```text
rit build formula
```

You must inform: 

* The **directory's path** where the formula is located.
* The **formula's path** to be builded \(the formula's command\). 

In case you want to update the formula's code in running time, you can use the **flag “--watch”** as shown in the command below:

```text
rit build formula --watch
```

## Next steps 

On this section, you saw how to implement a formula on Ritchie. To keep configuring the formula: 

👉 Go to [**publish a formula**](publish-a-formula.md) to see how to transfer your work to a public repository. 

