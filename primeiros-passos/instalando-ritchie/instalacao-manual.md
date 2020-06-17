# Instalação Manual

## Como funciona? 

**Caso opte por realizar o processo manual de instalação do Ritchie**, é necessário obedecer à seguinte premissa: ****obtenha a última versão do Ritchie, informando a URL abaixo no seu navegador. 

O link é este: [https://commons-repo.ritchiecli.io/stable.txt](https://commons-repo.ritchiecli.io/stable.txt)

Basicamente, ao indicar a URL acima para o navegador, o sistema retorna a versão do Ritchie mais atual. Logo, poderia retornar **1.0.0-beta.7** ou **1.0.0**  


## Passo 1: informar a URL 

O primeiro passo é baixar o binário do Ritchie da versão, informando a URL abaixo no seu navegador **de acordo com a versão {VERSION}.**

### \*\*\*\*

### **Instalando para MAC**

#### URL para Versão Team 

```text
https://commons-repo.ritchiecli.io/{VERSION}/darwin/team/rit
```

#### URL para Versão Single

```text
https://commons-repo.ritchiecli.io/{VERSION}/darwin/single/rit
```

### \*\*\*\*

### **Instalando para Linux**

#### URL para Versão Team 

```text
https://commons-repo.ritchiecli.io/{VERSION}/linux/team/rit
```

#### URL para Versão Single

```text
https://commons-repo.ritchiecli.io/{VERSION}/linux/single/rit
```

### \*\*\*\*

### **Instalando para Windows** 

#### URL para Versão Team 

```text
https://commons-repo.ritchiecli.io/{versão}/windows/team/rit.exe
```

#### URL para Versão Single

```text
https://commons-repo.ritchiecli.io/{versão}/windows/single/rit.exe
```

### \*\*\*\*

## **Passo 2: Configurações manuais**

Uma vez feita a instalação por meio da URL, você precisa realizar algumas configurações antes de utilizar o Ritchie. São elas: 

### **Criação da pasta**

**Passo 1:** Criar a pasta `$HOME/.rit/bin`

```text
Comando Linux / MacOs

mkdir -p $HOME/.rit/bin
```

**Passo 2:** Copiar o binário para a pasta criada acima. 

```text
Comandos Linux / MacOs

cd $HOME/.rit/bin 
cp $HOME/Downloads/rit
```

**Passo 3:** Permissão de execução

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

Nesse sistema operacional, é preciso chamar o rit no terminal diretamente a partir do `rit.exe` \(comando **rit.exe login**, ****por exemplo\). 

É possível e, inclusive, recomendável que você crie uma variável de ambiente para o rit, de modo que se torne mais fácil usar o CLI.

Seguem alguns **artigos** explicando como adicionar uma variável de ambiente no Windows.

📖 Como adicionar uma variável [via interface](https://professor-falken.com/pt/windows/como-configurar-la-ruta-y-las-variables-de-entorno-en-windows-10/)  
📖Como adicionar uma variável[ via terminal](https://devcontent.com.br/artigos/windows/o-que-sao-como-alterar-criar-excluir-variaveis-de-ambiente)

