# Formula implementation

{% hint style="info" %}
The **`rit create formula`** command creates a _Hello World_ formula template that needs to be changed to perform the desired operation.
{% endhint %}

It is necessary to change 3 places to implement the desired operation: 

* The config.json of the formula for configuring the inputs. 
* The main file 
* The files in the pkg folder. 

If another language was used, it may be necessary to change more files.

{% hint style="warning" %}
❗Do not change the name of the formula's root folders \(group / verb / noun\) without updating the **tree.json** and **Makefile** \(of the repository\) with the appropriate paths. 

❗Remember that **tree.json** and **Makefile** \(of teh reposiroty\) are already created / changed by executing the rit create formula command. Consequently, you will not need to change them to be able to test the new formula, even after changing the files commented above.
{% endhint %}

_Note: Therefore, it is possible to make some adjustments to these files if you need to._

_**For example**: If you need to change the decrypted message or the command helper associated with your formula, you will need to make these changes in **tree.json**._

