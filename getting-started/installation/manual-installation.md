# Manual Installation

## Premises

Get the latest version of Ritchie by entering the URL below in your browser

[https://commons-repo.ritchiecli.io/stable.txt](https://commons-repo.ritchiecli.io/stable.txt)

For example, it could return: **1.0.0-beta.7** or **1.0.0**  


## **Download**

Download the Ritchie binary version by entering the URL below in your browser by informing **the version** as obtained in step 1.

### **MAC**

#### **Versão Team** 

```text
https://commons-repo.ritchiecli.io/{versão}/team/mac/rit
```

**Versão Single**

```text
https://commons-repo.ritchiecli.io/{versão}/single/mac/rit
```

### **LINUX**

#### **Versão Team**

```text
https://commons-repo.ritchiecli.io/{versão}/team/linux/rit
```

**Versão Single**

```text
https://commons-repo.ritchiecli.io/{versão}/single/linux/rit
```

### **WINDOWS**

#### **Versão Team**

```text
https://commons-repo.ritchiecli.io/{versão}/windows/team/rit.exe
```

**Versão Single**

```text
https://commons-repo.ritchiecli.io/{versão}/windows/single/rit.exe
```

## Manual settings

### **Folder creation**

**→** Create the folder `$HOME/.rit/bin`

```text
Linux / MacOs command

mkdir -p $HOME/.rit/bin
```

→ Copy the binary to the folder created above. 

```text
Linux / MacOs commands

cd $HOME/.rit/bin 
cp $HOME/Downloads/rit
```

→ Execution permission

```
Linux / MacOs command

chmod +x rit
```



### Configure .bashrc or / etc / profile or .zshrc \(Linux / MacOS\)

For ZSH, define a new PATH by copying the following code:

```text
export RIT_PATH=$HOME/.rit
PATH=$RIT_PATH/bin:$PATH
rit completion zsh > ~/.rit_completion
source ~/.rit_completion
```

For Bash, define a new PATH by copying the following code:

```text
export RIT_PATH=$HOME/.rit
PATH=$RIT_PATH/bin:$PATH
rit completion bash > ~/.rit_completion
source ~/.rit_completion
```

### Setting environment variables \(Windows\)

For this operating system, you need to call rit on the terminal directly from rit.exe \(**rit.exe login** command for example\) 

It is possible \(and suggested\) to create an environment variable for rit to facilitate the use of the CLI. 

Here are some articles explaining how to add an environment variable in Windows.

[Through interface](https://professor-falken.com/pt/windows/como-configurar-la-ruta-y-las-variables-de-entorno-en-windows-10/)  
[Through terminal](https://devcontent.com.br/artigos/windows/o-que-sao-como-alterar-criar-excluir-variaveis-de-ambiente)  
****

