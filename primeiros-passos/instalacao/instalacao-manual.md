# Instalação Manual

## **PREMISSAS**

Obter a última versão do Ritchie, informando a URL abaixo no seu navegador :

[https://commons-repo.ritchiecli.io/stable.txt](https://commons-repo.ritchiecli.io/stable.txt)

Por exemplo, poderia retornar : **1.0.0-beta.7** ou **1.0.0**  


## **DOWNLOAD**

Baixar o binário do Ritchie da versão, informando a URL abaixo no seu navegador **alterando a versão** conforme obtido no passo 1.

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

### **WINDOW**

#### **Versão Team**

```text
https://commons-repo.ritchiecli.io/{versão}/windows/team/rit.exe
```

**Versão Single**

```text
https://commons-repo.ritchiecli.io/{versão}/windows/single/rit.exe
```

## **CONFIGURAÇÕES MANUAIS**

### **Criação da pasta**

**→** Criar a pasta `$HOME/.rit/bin`

```text
Comando Linux / MacOs

mkdir -p $HOME/.rit/bin
```

→ Copiar o binário para a pasta criada acima. 

```text
Comandos Linux / MacOs

cd $HOME/.rit/bin 
cp $HOME/Downloads/rit
```

→ Permissão de execução

```
Comando Linux / MacOs : 

chmod +x rit
```

\*\*\*\*

### **Configurar o .bashrc ou /etc/profile ou .zshrc \(Linux / MacOS\)**

Para ZSH, definir um novo PATH copiando o código a seguir :

```text
export RIT_PATH=$HOME/.rit
PATH=$RIT_PATH/bin:$PATH
rit completion zsh > ~/.rit_completion
source ~/.rit_completion
```

Para Bash, definir um novo PATH copiando o código a seguir :

```text
export RIT_PATH=$HOME/.rit
PATH=$RIT_PATH/bin:$PATH
rit completion bash > ~/.rit_completion
source ~/.rit_completion
```

\*\*\*\*

### **Configuração de variáveis de ambiente \(Windows\)**

Nesse sistema operacional, é preciso chamar o rit no terminal diretamente a partir do rit.exe \(comando **rit.exe login** por exemplo\)

É possível \(e sugerido\) criar uma variável de ambiente para o rit para facilitar o uso do CLI.

Seguem alguns artigos explicando como adicionar uma variável de ambiente no Windows.

[Via interface](https://professor-falken.com/pt/windows/como-configurar-la-ruta-y-las-variables-de-entorno-en-windows-10/)  
[Via terminal](https://devcontent.com.br/artigos/windows/o-que-sao-como-alterar-criar-excluir-variaveis-de-ambiente)  
  
****

