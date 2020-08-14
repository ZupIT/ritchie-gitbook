# Instalação Manual

Caso você decida seguir com a instalação manual do Ritchie, é necessário obedecer à seguinte premissa: **baixar a versão mais recente do Ritchie informando a URL abaixo no seu navegador.** 

O link: [https://commons-repo.ritchiecli.io/stable.txt](https://commons-repo.ritchiecli.io/stable.txt)​

Quando você indica a URL acima no navegador, o sistema retorna a última versão do Ritchie. Por exemplo, poderá retornar algo como **1.0.1 ou 2.0.1**

## Como instalar?

Faça o download da versão binária do Ritchie ao entrar na URL que você já digitou no seu navegadore informe a **versão {VERSION}** que você obteve no passo anterior.

### **Instalação para MACOs** <a id="installation-for-mac"></a>

```text
https://commons-repo.ritchiecli.io/{VERSION}/darwin/rit
```

### **Instalação para Linux** <a id="installation-for-linux"></a>

```text
https://commons-repo.ritchiecli.io/{VERSION}/linux/rit
```

### **Instalação para Windows**  <a id="installation-for-windows"></a>

```text
https://commons-repo.ritchiecli.io/{VERSION}/windows/rit.exe
```

\*\*\*\*

## **Configurações manuais** <a id="manual-settings"></a>

### **Como criar uma pasta** <a id="folder-creation"></a>

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

### **Como configirar o .bashrc ou /etc/profile ou .zshrc \(Linux / MacOS\)** <a id="configure-the-bashrc-ou-etc-profile-or-zshrc-linux-macos"></a>

Para o ZSH, defina o novo PATH copiando o código abaixo: 

```text
export RIT_PATH=$HOME/.rit
PATH=$RIT_PATH/bin:$PATH
rit completion zsh > ~/.rit_completion
source ~/.rit_completion
```

Para o Bash, defina o novo PATH copiando o código abaixo: 

```text
export RIT_PATH=$HOME/.rit
PATH=$RIT_PATH/bin:$PATH
rit completion bash > ~/.rit_completion
source ~/.rit_completion​
```

### Configurações de variáveis de ambiente \(Windows\) <a id="setting-environment-variables-windows"></a>

No caso do Windows, você precisa chamar o rit no terminal diretamente pelo rit.exe. Por exemplo: comando **rit.exe login.** 

É possível - e recomendado - que você crie uma variável de ambiente para o rit, tornando assim mais fácil o uso do CLI.

Abaixo, confira alguns artigos que explicam como adicionar uma variável de ambiente no Windows:

* Adicionando [através da interface](https://professor-falken.com/pt/windows/como-configurar-la-ruta-y-las-variables-de-entorno-en-windows-10/) 
* Adicionando [através do terminal](https://devcontent.com.br/artigos/windows/o-que-sao-como-alterar-criar-excluir-variaveis-de-ambiente)

