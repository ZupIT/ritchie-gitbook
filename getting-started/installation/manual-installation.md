# Manual Installation

## How does it work? 

The 1.0.0 version is deprecated, it is still possible to use it, but the team is now focussing on new features starting on the version 2.0.0. 

{% hint style="info" %}
The latest and most stable release of this Ritchie version is the **`1.0.0-legacy`**
{% endhint %}

### \*\*\*\*

### **Installation for MAC**

#### **Team Version URL**

```text
https://commons-repo.ritchiecli.io/1.0.0-legacy/darwin/team/rit
```

#### Single Version URL

```text
https://commons-repo.ritchiecli.io/1.0.0-legacy/darwin/single/rit
```



### **Installation for Linux**

#### **Team Version URL**

```text
https://commons-repo.ritchiecli.io/1.0.0-legacy/linux/team/rit
```

**Single Version URL**

```text
https://commons-repo.ritchiecli.io/1.0.0-legacy/linux/single/rit
```

### \*\*\*\*

### **Installation for Windows** 

#### **Team Version URL**

```text
https://commons-repo.ritchiecli.io/1.0.0-legacy/windows/team/rit.exe
```

**Single Version URL**

```text
https://commons-repo.ritchiecli.io/1.0.0-legacy/windows/single/rit.exe
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



