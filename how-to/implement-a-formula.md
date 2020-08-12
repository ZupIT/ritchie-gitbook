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
*  the formula inputs parameters.

Each input is composed of the following fields:

* Name 
* Type
* Label 
* Default \(_optional_\) 
* Items \(_optional_\) 
* Cache \(_optional_\)

#### 2. **`main file`**

* The main file is used to extract the inputs asked in the config.json file.  _Inputs are extracted by the field **name** informed on the config.json file._
* This is also where are called the methods to realise the task / automation of the formula, manipulating  those input parameters. 

#### 3. `/pkg folder`

This folder contains the files with the formula's behavior. Methods called by the main.file are located inside the files inside this folder.

{% hint style="info" %}
Depending on the chosen language, it may be necessary to update more files, for example to manipulate dependencies.
{% endhint %}

See an example below of this structure \(in this case, it's a formula created in Golang\):

{% tabs %}
{% tab title="Golang" %}
![](../.gitbook/assets/estrutura.png)

As the image above, you can see the editable files:

* **config.json:** Update the inputs configurations.
* **main.go:** Extract the inputs and call the formula's methods \(coded on **pkg/\***\).
* **pkg/\*:** Code the formula's behavior.
* **help.json:** Update the formula description message.
{% endtab %}
{% endtabs %}

{% hint style="warning" %}
The structures defines the command, so **it's not indicated to update** folders names or include more files/folders **if not** in the **src/\*** folder.
{% endhint %}

## Next steps 

On this section, you saw how to implement a formula on Ritchie. To keep configuring the formula: 

👉 Go to [**build a formula**](build-a-formula.md) to see how to continue the tests on the formulas you create. 

👉 Go to [**publish a formula**](how-to-publish-a-formula.md) to see how to transfer your work to a public repository. 
