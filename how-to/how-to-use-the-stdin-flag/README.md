---
description: 'In this section, you will find everything about STDIN flag.'
---

# Using STDIN flag

Informing inputs through **arguments** or **flags** allows the user to automate workflows. It is particularly useful when you're manipulating other tools within a script, as you can automate operations without having to interact with the terminal. 

{% hint style="danger" %}
The **`--stdin`** flag on Ritchie has been developed to support this scenario as well.  
  
In that case, the input parameters need to be informed in a **JSON format**:

**`echo`**`'{"key":"value"}'`**`|`**`RIT (GROUP) VERB NOUN` **`--stdin`**
{% endhint %}

![Executing a formula on Ritchie with STDIN](../../.gitbook/assets/screen-shot-2020-08-27-at-15.22.10.png)

## Next steps

You saw in this section how works the --stdin flag. If you want to keep reading about Ritchie's commands:

👉 Check out the [**formulas commands**](formulas-commands.md) to see more automation possibilities.  

👉 Check out the [**Core Commands**](core-commands.md) to see know all commands that can be used through stdin. 

