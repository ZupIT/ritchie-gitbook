# Formula folder

{% hint style="info" %}
The **`rit create formula`** command automatically creates a folder for the formula in the repository, according to the input provided.
{% endhint %}

The formula folder has the following structure :

![](https://lh4.googleusercontent.com/lu-BipM4Ym4qc3EeGXLNoEyvDknCZ1ZUtAvUxWra0v4uyyKi71gZiUAJzwi2n4UlwqPwdhKROps945TJ6g6i_kfi_TmlqC-nC-JOVl7T3Oy6Ks5Fnoy8Ok1lwVViRn36JAV-JAg0)



The contents of the **SRC** folder are standardized according to the chosen language, and are always composed of the following elements: 

* the main file 
* the Makefile file \(of the formula\) 
* the config.json file 
* the pkg folder 

The **main** file is the formula's executable. It that starts the code that will be called by the terminal. It will be created according to the language entered as input to the command, and will contain a standard implementation example. 

The **Makefile** \(formula\) file is different from the Makefile file in the repository. The Makefile \(formula\) allows to generate the executables of the formula, while the Makefile of the repository allows both to generate the executables of all formulas, as well as to test the formulas locally by adding these executables in the .rit folder. 

The **config.json** file contains **3 standard inputs** as an example, which are extracted and manipulated in the main file of the formula. 

The **pkg** folder will be composed of the other code files that, together with the main file, will allow the formula to be executed. They will be created in the chosen language. 

If you first created a formula by creating the local repository, the formula repository and folder will follow the structure below :

![](https://lh5.googleusercontent.com/6oPMzmvLxb9PGmC9a6U7KfLt4oCpEnFhOHXXOoGkgMgmaQi4kKHDo5epvU27HbWbBvM1mC1K2aruXfGPQrtWJMibeXmXmN19NbI7S81Djz11Axc0fCG2GtTNCAYivuI2iMMxMLZK)

{% page-ref page="formula-implementation.md" %}

