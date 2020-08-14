---
description: You will find in this section how to install Ritchie manually.
---

# Manual Installation

In case you decide to make the manual process of Ritchie installation, it's necessary to obey the following premise: **get the latest version of Ritchie, informing the URL below on your navigator.**

The link: [https://commons-repo.ritchiecli.io/stable.txt](https://commons-repo.ritchiecli.io/stable.txt)​

Basically, when you indicate the URL above on your navigator, the system returns the latest version of Ritchie. For example, it can return something like **1.0.1 or 2.0.1**

## How to install?

Download the Ritchie binary version by entering the URL below in your browser by informing **the version** **{VERSION}** as obtained in step 1.

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

\*\*\*\*

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

   3. Lastly, run a permission to execute.

```text
chmod +x rit
```

**​**

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

