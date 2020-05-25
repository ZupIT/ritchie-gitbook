# Formula repositories

{% hint style="info" %}
Formulas are stored in **formula repositories**. 

These repositories need to have a particular structure.
{% endhint %}

Each repository must contain the following elements: 

* the formula folders. 
* a tree folder 
* a Makefile file 
* a copy-bin-configs.sh file 
* an unzip-bin-configs.sh file

![](../../../.gitbook/assets/repo.png)

Each **formula folder** will contain the executable code and files for a formula.

The **tree** folder is composed of a **tree.json** file that will contain the command tree of all formulas in the repository.

The **Makefile** file contains a reference to all formulas in the repository, as well as an executable command manipulating the files **copy-bin-configs.sh** and **unzip-bin-configs.sh**, in order to generate the executable files needed to test the formula\(s\) locally inside the [.rit folder](../../cli/.rit-folder.md).

