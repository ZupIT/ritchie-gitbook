# Manual Installation

## How does it work? 

**In case you decide to make the manual process of Ritchie installation**, it's necessary to obey the following premise: get the latest version of Ritchie, informing the URL below your navigator. 

The link: [https://commons-repo.ritchiecli.io/stable.txt](https://commons-repo.ritchiecli.io/stable.txt)

Basically, when you indicate the URL above on your navigator, the system returns the latest version of Ritchie. For example, it can return **1.0.0-beta.7** or **1.0.0**  


### Step by step 

Download the Ritchie binary version by entering the URL below in your browser by informing **the version** **{VERSION}** as obtained in step 1.

### **Installation for MAC**

#### **Team Version URL**

```text
https://commons-repo.ritchiecli.io/{VERSION}/team/mac/rit
```

#### Single Version URL

```text
https://commons-repo.ritchiecli.io/{VERSION}/single/mac/rit
```



### **Installation for Linux**

#### **Team Version URL**

```text
https://commons-repo.ritchiecli.io/{VERSION}/team/linux/rit
```

**Single Version URL**

```text
https://commons-repo.ritchiecli.io/{VERSION}/single/linux/rit
```

### \*\*\*\*

### **Installation for Windows** 

#### **Team Version URL**

```text
https://commons-repo.ritchiecli.io/{VERSION}/windows/team/rit.exe
```

**Single Version URL**

```text
https://commons-repo.ritchiecli.io/{VERSION}/windows/single/rit.exe
```

## **Manual settings** 

### **Folder creation**

**→** Create a folder  `$HOME/.rit/bin`

```text
Comando Linux / MacOs

mkdir -p $HOME/.rit/bin
```

→ Copy the binary to the folder above.

```text
Comandos Linux / MacOs

cd $HOME/.rit/bin 
cp $HOME/Downloads/rit
```

→ Permission to execute. 

```
Comando Linux / MacOs : 

chmod +x rit
```

\*\*\*\*

### **Configure the .bashrc ou /etc/profile or .zshrc \(Linux / MacOS\)**

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
source ~/.rit_completion
```

\*\*\*\*

### Setting environment variables \(Windows\)

For this operating system, you need to call rit on the terminal directly from rit.exe \(**rit.exe login** command for example\) 

It is possible \(and suggested\) to create an environment variable for rit to facilitate the use of the CLI. 

Here are some articles explaining how to add an environment variable in Windows.

[Through interface](https://professor-falken.com/pt/windows/como-configurar-la-ruta-y-las-variables-de-entorno-en-windows-10/)  
[Through terminal](https://devcontent.com.br/artigos/windows/o-que-sao-como-alterar-criar-excluir-variaveis-de-ambiente)\*\*\*\*

