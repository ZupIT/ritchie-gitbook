---
description: Step by step explaining how to create a new formula on Ritchie.
---

# First formula

## Premise

![](https://lh3.googleusercontent.com/WyVwIU8sQ9TLlngvGve5Sl4vOkcc-31ALVlJZNvMIIeQsLsvmmieCvc1M8-hxKiFI_3xKQRoBbFdQxfe6VVc9pKko2jmuwvTjz5Eq11Eg5jkmTOWFU2PowDiEHr7oHQtYEd7huyZ)

The _`rit create formula`_ command creates the necessary structure for the user to start developing a new formula on his machine.

Before going into detail in the step by step to create a formula, it is recommended to read the [documentation regarding the functioning of Ritchie.](https://docs.ritchiecli.io/get-started/understand-ritchie)

## **Formulas repositories**

In order to use a formula in the CLI, it must be in a formula repository.

This repository needs to have a particular structure, containing the following elements:

| → a tree folder, containing the repository tree.json file. |
| :--- |


This _**tree.json**_ file will contain the command tree for all formulas in the repository.

The CLI will merge the trees of all the repositories that the user has access to when executing the commands.

| → a Makefile file, located at the root of the project. |
| :--- |


This _**Makefile**_ file must contain a reference to all formulas in the repository, as it allows you to generate the files needed to test the formula\(s\) locally.

| → the folders containing the formulas. |
| :--- |


Each of these folders will contain the executable code and files needed for a formula to work.

## Formulas

For formulas to be executables, you need to have a few elements configured:

| → The repository tree.json where the formula is implemented. |
| :--- |


For the CLI to know the executable command of each formula after merging all the command trees from the different repositories.

| → The config.json in the formula folder |
| :--- |


This file contains the input parameters of the formula, so that the CLI knows what information he will need to ask the user when he will execute the command in the terminal in order to process the formula correctly.

| → The binary containing the formula code. |
| :--- |


For the CLI to download this binary according to the operating system of the user's computer and execute the formula through the input parameters that will have been informed.

![](../.gitbook/assets/fluxo-formulas%20%281%29.png)



## Formula creation command

We need to ensure that all the elements presented in the previous steps are set up correctly when creating the formula, and that is what the `rit create formula` command offers us.

![](https://lh3.googleusercontent.com/FUWXlxUDiMokwUBKrQi5FwEVEZcQBSz1B-4-TYCltyP-HB1sNVTLMNENSHSSxD-JUMN4EfwaNPZsJOY7SH5-bFdFXuhsXHtQT5cWx0cd7553sONxPgm1odu0XeCk_O73UAPvTIVy)

When this command is executed on the terminal, an input is requested from the user, the **command** that will execute the new formula \(ideally following the pattern **rit + group + verb + noun**\).

All the files and architecture discussed above will be created and configured from this command.

## **Creation of the formula repository**

The first time a formula is created locally with the rit create formula command, the formula code will check whether the formula repository, called **ritchie-formulas-local**, already exists on the user's machine home directory.

→ If this repository exists, the new formula will be added there.

→ If it does not exist, the repository will be created before adding the new formula.  
****  
Follow the repository structure with a formula \(inside the group folder\).

![](https://lh4.googleusercontent.com/PXY6o7YbMg7ZdSdSvrkzOnIA2unJVFxY9FQ5ED0lxnHMeDNo9F43VjhZUIJTkKromBmUIp_YtvprQ3_RTAdlFJaBWTUZbAxHs-jMTLlRYHXY10WTJqh0rJEwN6EOWXl1TnbETl83)

This repository will always contain at least the tree folder, the _makefile_ \(main\), as well as the new formula folder.

* The _tree.json_ of the tree folder will be updated with the new command.
* The _makefile_ \(main\) will be updated with the folder path of the new formula.

| **❗**In addition, there will be 2 shell files \(.sh\) needed to perform the tests. We will talk about them later. In the **Formula testing** section. |
| :--- |


## **Formula folder creation**

The command will creates a folder for the formula in the repository, according to the informed input. This folder will have the following structure:

![](https://lh3.googleusercontent.com/_vvHohXWgykSyKPEpWQ5WQAXuj7t1f8af39xWZcgMJxdqbFOqTeFWoJwgWHkexVkSIlrwq5UTC96-OafT9L3ppYEAEJjbm20u3yQEHV66PI3RfyhEcNdix2PSO2cGDZOYBBxyVTh)

The contents of the **SRC** folder are standardised, and are always composed of the following elements:

| → A main.go file |
| :--- |


This file is the formula executable. It starts the code that will be called by the terminal. By default, it will be created in the Go language \(but nothing prevents using another language\) and will contain a standard implementation example.

| → A Makefile \(formula\) file |
| :--- |


This file is different from the repository's _**Makefile**_ \(main\). The formula _**Makefile**_ allows the user to generate the formula binaries, while the repository's Makefile allows to either generate the binaries of all the formulas, or test the formulas locally.

| → A config.json file |
| :--- |


This file will contain 3 standard _**input parameters**_ as an example, to be used in the formula's main.go file.

| → A PKG folder |
| :--- |


This folder will be composed of the other code files that, together with the main.go file, will allow the formula to be executed. By default, they will also be created in the Go language \(but nothing prevents using another language\).

| **❗Remember that you can write your formula using any language you are familiar with \(bash, python, golang, etc.\).** |
| :--- |


If you created a formula for the first time, the repository and formula folders must follow the same structure as below:

![](https://lh3.googleusercontent.com/ETZBb8Ty37kCrh0M19Xm2-rd0cO6KGBbgXjdTqp1reOLtPc83eSfOxew04Hb798Mh5dw1NriDY95jlfEPJ6Xw4K9MoGnHaccgDvJr37Q6QdXgIs1c6vPTrv2yWDx5xtpqqBki6Lm)

## **Formula implementation**

Once the formula repository has been created at the home directory with the new formula, all that's missing is to develop the logic inside of the formula code.

To do this, it is necessary to configure at least 3 elements :

* The config.json of the formula, adding the input parameters the formula will use.
* The main.go file
* The code files into the PKG folder.

If another programming  language was used, it may be necessary to configure more files.

<table>
  <thead>
    <tr>
      <th style="text-align:left">
        <p>&#x2757;Do not change the name of the root folders of the formula (group
          / verb / noun) without updating tree.json and Makefile (main) with the
          appropriate paths.
          <br />
        </p>
        <p>&#x2757;Remember that tree.json and Makefile (main) will have already
          been updated by executing the rit create formula command. Consequently,
          you will not need to modify them to be able to test the new formula, even
          after changing the files commented above.</p>
      </th>
    </tr>
  </thead>
  <tbody></tbody>
</table>_Note: Keep in mind it is possible to make some adjustments to these files if necessary._

_For example: If you need to change the description message or helper of the command associated with your formula, you will need to make these changes in tree.json._

## **Formula testing**

| ❗**Ritchie needs to be installed on the computer to be able to test the new formulas through the terminal.** |
| :--- |


Once the formula has been implemented, there are several ways of testing it.

We will introduce 2 of them here.

| **→ Through an IDE \(if using one\).** |
| :--- |


  
****You can run your formula's main file \(main.go\) by setting environment variables to represent your input parameters. The advantage of using an IDE is that you can debug the code.

_Note: Goland can be used for Go, IntelliJ or Eclipse for Java or Kotlin for example_

| → Through the terminal |
| :--- |


When creating the new formula, the path where the formula is located in the repository was informed in the Makefile \(main\) at the root of the repository.

In this file there is a test-local command that allows you to create the binary of one or more formulas and place them in the temporary Ritchie folder \(.rit\) located on the computer home directory .

_Note: This test-local command uses 2 other files at the root of the repository: **copy-bin-configs.sh** and **unzip-bin-configs.sh** which actually allow you to extract the **binaries** and **config.json** associated with each formula that is tested._

There are 2 ways of using this Makefile command:

| `$ make test-local form={nome_formula}`  |
| :--- |


To add the specific formula you want to test in the temporary .rit folder.

| `$ make test-local` |
| :--- |


To add all formulas from the repository to the temporary .rit folder  


After adding the formula in **.rit** through the _**Makefile**_ \(main\), it will be possible to execute the command associated with that formula through the terminal \(auto-completion will not work in this case\).

![Local test of the new formula](https://lh6.googleusercontent.com/7EqW8p9HRuOvd4TIEGVe41IBuaH7XDrrIfIZ2gPjq2U0bG1qsrqGW1f_bluhy_dhqgjYhhSJq-7c6ThZrX2YQxXgWmUhNkjgVFoPKRcyHKx3g9eJjH8MKs0mddT3cm1slCf8TcSd)

![.rit directory after executing the make test-local command](https://lh5.googleusercontent.com/MIBQ6ttOxfkzACMUN2fGGyo_il0YnxcZvSW41hJRDhSiCHhwjjCWa9BOzi-PamjoAj7BYZ0NVXN0ELVp2u1ahFNeVxpNhcUm3mBK9rTCu29sxiZfHkdl8QrP_i5DP7GclAvOoh0g)

| **✅ Congratulations, you have just created your first formula on Ritchie !** |
| :--- |


**Can your formula be useful for other people ?**  
  
→ Share it with the community opening a pull request to the [ritchie-formulas repository](https://github.com/ZupIT/ritchie-formulas).

