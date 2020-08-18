---
description: You will find in this section how to implement formulas on Ritchie.
---

# How to implement formulas

## How to implement? 

Once you [**create and test your formula**](how-to-create-formulas.md), Ritchie will generate a structure of files inside your workspace. Then, you can start implementing the new automation by updating this "Hello World template.

### Editable files 

To do this configuration, you hill have to update **3 files** located inside the **/src package** of the new formula’s root folder. 

#### 1.  **`config.json`**

The **config.json** file contains the formula's input parameters. It allows the CLI to know what datas to ask the user when he executes the command in the terminal in order to process the formula correctly.

These input parameters are made up of the following fields: 

* a docker image builder
* the formula inputs parameters.

Each input is composed of the following fields:

* `name` : variable name to extract.
* `type` : _**text**_ \(string\), _**bool**_ \(boolean\) or _**password**_ \(hidden string\).
* `label`  : text appearing on the CLI asking for the input.
* `default` \(_optional_\) : default input value \(if null\).
* `items` \(_optional_\) : list of input variable options.
* `cache` \(_optional_\) : 
  * `active`: if cache is enabled or not.
  * `qty`: amount of values to store.
  * `newLabel`: text appearing on the CLI asking for a new input. 

#### 2. **`main file`**

* The main file is used to extract the inputs asked in the config.json file.  _Inputs are extracted by the field **name** informed on the config.json file._
* This is also where are called the methods to realise the task / automation of the formula, manipulating  those input parameters. 

#### 3. `formula/* folder`

This folder contains the files with the formula's behavior. Methods called by the main.file are located inside the files inside this folder.

{% hint style="info" %}
Depending on the chosen language, it may be necessary to update more files, for example to manipulate dependencies.
{% endhint %}

See an example below of this structure \(in this case, it's a formula created in Golang\):

{% tabs %}
{% tab title="Golang" %}
![](../.gitbook/assets/go.png)

According to the image above, you can see the editable files:

* **config.json:** Update the inputs configurations.
* **main.go:** Extract the inputs and call the formula's methods \(coded on **formula/\***\).
* **formula/\*:** Code the formula's behavior.
* **help.json:** Update the command or subcommand description message.
{% endtab %}

{% tab title="Java" %}


![](../.gitbook/assets/java.png)

According to the image above, you can see the editable files:

* **config.json:** Update the inputs configurations.
* **main.java:** Extract the inputs and call the formula's methods \(coded on **formula/\***\).
* **formula/\*:** Code the formula's behavior.
* **help.json:** Update the command or subcommand description message.
{% endtab %}

{% tab title="Node" %}
![](../.gitbook/assets/node.png)

According to the image above, you can see the editable files:

* **config.json:** Update the inputs configurations.
* **index.js:** Extract the inputs and call the formula's methods \(coded on **formula/\***\).
* **formula/\*:** Code the formula's behavior.
* **help.json:** Update the command or subcommand description message.
{% endtab %}

{% tab title="Python" %}
![](../.gitbook/assets/python.png)

According to the image above, you can see the editable files:

* **config.json:** Update the inputs configurations.
* **main.py:** Extract the inputs and call the formula's methods \(coded on **formula/\***\).
* **formula/\*:** Code the formula's behavior.
* **help.json:** Update the command or subcommand description message.
{% endtab %}

{% tab title="Shell" %}
![](../.gitbook/assets/shell.png)

According to the image above, you can see the editable files:

* **config.json:** Update the inputs configurations.
* **main.sh:** Extract the inputs and call the formula's methods \(coded on **formula/\***\).
* **formula/\*:** Code the formula's behavior.
* **help.json:** Update the command or subcommand description message.
{% endtab %}
{% endtabs %}

{% hint style="warning" %}
The structures defines the command, so **it's not indicated to update** folders names or include more files/folders **if not** in the **src/\*** folder.
{% endhint %}

## Next steps 

On this section, you saw how to implement a formula on Ritchie. To keep configuring the formula: 

👉 Go to [**build a formula**](build-a-formula.md) to see how to continue the tests on the formulas you create. 

👉 Go to [**publish a formula**](how-to-publish-a-formula.md) to see how to transfer your work to a public repository. 

