# What are formulas ?

{% hint style="info" %}
**Formulas** are nothing more than **automations**. That is, they are codes called through the command lines to perform some operation. 
{% endhint %}

## On demand

The first time the user executes the command associated with a formula on the terminal, the executable file for that formula is downloaded according to the operating system installed on his computer. 

The config.json file is downloaded at the same time, with the **formula input parameters**, necessary for the code implemented in the executable file to be executed. 

These input parameters will be informed by the user: 

* after he types the command in the terminal \(if via [prompt](../user/commands/prompt.md)\) 
* before typing the command in the terminal \(if via [stdin](../user/commands/stdin/)\) 

... before actually executing the formula.  
****

![](../.gitbook/assets/fluxo-formulas%20%283%29.png)

## Execution of a formula \(with prompt\)

![Example of a Ritchie command executed by the terminal](https://lh3.googleusercontent.com/viskNlV4iXyN63RYhBdgu9I010Rz6nXaliyFKvC9vAHDyrQm2fEPUXzF5l6QclYEoQywEeXYZq3hPQFP_DqGQYJkk38E3nuam4rJQPSdl5zHU6HzP9Q2mEfg3TJeBuacn2geRgx7)

**`rit scaffold generate coffee`** is an executable command associated with a formula in the CLI's tree.

As it was the first time that the command was executed, it is possible to observe that Ritchie downloaded a config file and the formula's binary in sequence.

After downloading the files, Ritchie asked the user for some datas: 

* name
* type of coffee 
* delivery

Those datas are the **input** **parameters** of the formula.

Once these parameters were informed, the formula was successfully executed \(according to what the logs presented\).

