---
description: You will find in this section how to install Ritchie manually.
---

# Manual Installation

If you choose to make the manual process of Ritchie's installation, you have to follow the guideline: **get the latest Ritchie's version and inform the URL below on your navigator.**

* **The link:** [https://commons-repo.ritchiecli.io/stable.txt](https://commons-repo.ritchiecli.io/stable.txt)​

Basically, when you indicate the URL above on your navigator, the system returns the latest version of Ritchie. For example, it can return **1.0.1 or 2.0.1**

## How to install?

1. Download the Ritchie binary version;
2. Enter the URL below in your browser by informing **the version** **{VERSION}** as obtained in step 1.

### **Installation for MAC** <a id="installation-for-mac"></a>

```text
https://commons-repo.ritchiecli.io/{VERSION}/darwin/rit
```

### **Installation for Linux** <a id="installation-for-linux"></a>

```text
https://commons-repo.ritchiecli.io/{VERSION}/linux/rit
```

### **Installation for Windows**  <a id="installation-for-windows"></a>

```text
https://commons-repo.ritchiecli.io/{VERSION}/windows/rit.exe
```

## **Manual settings**  <a id="manual-settings"></a>

### **How to create a folder?** <a id="folder-creation"></a>

1. First, run the command below to create a folder `$HOME/.rit/bin`

```text
mkdir -p $HOME/.rit/bin
```

    2. Then, copy and paste the binary to the folder above.

```text
​cd $HOME/.rit/bin 
cp $HOME/Downloads/rit
```

   3. Lastly, run a permission to run: 

```text
chmod +x rit
```

### \*\*\*\* <a id="configure-the-bashrc-ou-etc-profile-or-zshrc-linux-macos"></a>

### **How to configure the .bashrc ou /etc/profile or .zshrc \(Linux / MacOS\)** <a id="configure-the-bashrc-ou-etc-profile-or-zshrc-linux-macos"></a>

To ZSH, define a new PATH by copying the following code:

```text
export RIT_PATH=$HOME/.rit
PATH=$RIT_PATH/bin:$PATH
rit completion zsh > ~/.rit_completion
source ~/.rit_completion
```

To Bash, define a new PATH by copying the following code:

```text
export RIT_PATH=$HOME/.rit
PATH=$RIT_PATH/bin:$PATH
rit completion bash > ~/.rit_completion
source ~/.rit_completion​
```

### Setting environment variables \(Windows\) <a id="setting-environment-variables-windows"></a>

For this operating system, you need to call rit on the terminal directly from rit.exe \(**rit.exe login** command for example\)

It is possible \(and suggested\) to create an environment variable for rit to facilitate the use of the CLI.

Here are some articles explaining how to add an environment variable in Windows:

* Adding [through interface](https://professor-falken.com/pt/windows/como-configurar-la-ruta-y-las-variables-de-entorno-en-windows-10/) 
* Adding[ Through terminal](https://devcontent.com.br/artigos/windows/o-que-sao-como-alterar-criar-excluir-variaveis-de-ambiente)

