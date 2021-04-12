---
description: 'In this section, you will find information about a Ritchie formula folder.'
---

# Formula Folder

## What is the formula folder?

This folder contains the files with the formula's behavior. 

{% hint style="warning" %}
The folder structures defines the command tree, so **it's not indicated to update** folders names or include more files/folders, **if not** in the **src/\*** folder.
{% endhint %}

Each programming language has its own specificities, but the formula's structure is almost always the same, no matter what language is used, and will contain:

| File | Description |
| :--- | :--- |
| `config.json` | file to configure the formula inputs. |
| `main file` | file to extract local variables. |
| `pkg/formula file` | file to implement the formula operation. |
| `Dockerfile` | file to build docker images. |
| `README file` | file to explain what the formula does. |
| `Makefile file` | file to compile the formula's code \(_will be deprecated in 2021_\). |
| `build.sh file` | file to compile the formula's code in shell. |
| `metadata.json file` | file to tag the formula's information. |
| `set_unmask.sh file` | file used by the Makefile file. |
| `help.json files` | file to configure formula helper messages on the CLI. |

You can find all [**languages templates**](https://github.com/ZupIT/ritchie-formulas/tree/master/templates/create_formula/languages) on the ritchie-formulas repository.



### Formula folder examples

{% tabs %}
{% tab title="Golang" %}
![](../../../.gitbook/assets/go%20%281%29%20%281%29%20%281%29.png)

To change the formula's behavior for this language, you'll have at least to update the following files:

* **config.json:** Update the inputs configurations.
* **main.go:** Extract the inputs and call the formula's methods \(coded on **formula/\***\).
* **formula/\*:** Code the formula's behavior.
{% endtab %}

{% tab title="Java" %}
![](../../../.gitbook/assets/java%20%282%29%20%282%29%20%282%29.png)

To change the formula's behavior for this language, you'll have at least to update the following files:

* **config.json:** Update the inputs configurations.
* **main.java:** Extract the inputs and call the formula's methods \(coded on **formula/\***\).
* **formula/\*:** Code the formula's behavior.
{% endtab %}

{% tab title="Node" %}
![](../../../.gitbook/assets/node%20%283%29%20%283%29%20%283%29.png)

To change the formula's behavior for this language, you'll have at least to update the following files:

* **config.json:** Update the inputs configurations.
* **index.js:** Extract the inputs and call the formula's methods \(coded on **formula/\***\).
* **formula/\*:** Code the formula's behavior.
{% endtab %}

{% tab title="Python" %}
![](../../../.gitbook/assets/python%20%282%29.png)

To change the formula's behavior for this language, you'll have at least to update the following files:

* **config.json:** Update the inputs configurations.
* **main.py:** Extract the inputs and call the formula's methods \(coded on **formula/\***\).
* **formula/\*:** Code the formula's behavior.
{% endtab %}

{% tab title="Shell" %}
![](../../../.gitbook/assets/shell%20%282%29%20%281%29.png)

To change the formula's behavior for this language, you'll have at least to update the following files:

* **config.json:** Update the inputs configurations.
* **main.sh:** Extract the inputs and call the formula's methods \(coded on **formula/\***\).
* **formula/\*:** Code the formula's behavior.
{% endtab %}
{% endtabs %}

{% hint style="warning" %}
The structures defines the command, so **it's not indicated to update** folders names or include more files/folders **if not** in the **src/\*** folder.
{% endhint %}

