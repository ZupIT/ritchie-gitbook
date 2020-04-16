# Manual Installation

## PREMISES

Get the latest version of Ritchie by entering the URL below in your browser

[http://ritchie-cli-bucket152849730126474.s3-website-sa-east-1.amazonaws.com/stable.txt](http://ritchie-cli-bucket152849730126474.s3-website-sa-east-1.amazonaws.com/stable.txt)

For example, it could return: **1.0.7** ou **2.0.0.2**  


## **DOWNLOAD**

Download the Ritchie binary version by entering the URL below in your browser by informing **the version** as obtained in step 1.

**MAC  
  
Team version :** http://ritchie-cli-bucket152849730126474.s3-website-sa-east-1.amazonaws.com/{versão}/team/mac/rit

**Single version :** http://ritchie-cli-bucket152849730126474.s3-website-sa-east-1.amazonaws.com/{versão}/single/mac/rit  
****

#### **LINUX**

**Team version :** http://ritchie-cli-bucket152849730126474.s3-website-sa-east-1.amazonaws.com/{versão}/team/linux/rit

**Single version :** http://ritchie-cli-bucket152849730126474.s3-website-sa-east-1.amazonaws.com/{versão}/single/linux/rit  
****

**WINDOW  
  
Team version :** http://ritchie-cli-bucket152849730126474.s3-website-sa-east-1.amazonaws.com/{versão}/windows/team/rit.exe

**Single version :** http://ritchie-cli-bucket152849730126474.s3-website-sa-east-1.amazonaws.com/{versão}/windows/single/rit.exe  


## MANUAL SETTINGS

### **Folder creation**

**→** Create the folder `$HOME/.rit/bin`

Linux / MacOs command : `mkdir -p $HOME/.rit/bin`

→ Copy the binary to the folder created above. 

Linux / MacOs command : `cd $HOME/.rit/bin`   
+  
Linux / MacOs command : `cp $HOME/Downloads/rit`

→ Execution permission

Linux / MacOs command : `chmod +x rit`  


### Configure .bashrc or / etc / profile or .zshrc \(Linux / MacOS\)

For ZSH, define a new PATH by copying the following code:

`export RIT_PATH=$HOME/.rit  
PATH=$RIT_PATH/bin:$PATH  
rit completion zsh > ~/.rit_completion  
source ~/.rit_completion`  


For Bash, define a new PATH by copying the following code:

`export RIT_PATH=$HOME/.rit  
PATH=$RIT_PATH/bin:$PATH  
rit completion bash > ~/.rit_completion  
source ~/.rit_completion`  


### Setting environment variables \(Windows\)

For this operating system, you need to call rit on the terminal directly from rit.exe \(**rit.exe login** command for example\) 

It is possible \(and suggested\) to create an environment variable for rit to facilitate the use of the CLI. 

Here are some articles explaining how to add an environment variable in Windows.

Through interface : [https://professor-falken.com/pt/windows/como-configurar-la-ruta-y-las-variables-de-entorno-en-windows-10/](https://professor-falken.com/pt/windows/como-configurar-la-ruta-y-las-variables-de-entorno-en-windows-10/)

Through terminal : [https://devcontent.com.br/artigos/windows/o-que-sao-como-alterar-criar-excluir-variaveis-de-ambiente](https://devcontent.com.br/artigos/windows/o-que-sao-como-alterar-criar-excluir-variaveis-de-ambiente)  
****

