---
description: Você encontrará nessa seção como instalar o Ritchie para Windows.
---

# Windows

Para instalar a **última versão do Ritchie**, você precisa  fazer o **download do instalador** e executá-lo no seu terminal. 

### Passo 1: Instalação

Você deve fazer o [**download do instalador**](https://commons-repo.ritchiecli.io/latest/ritchiecli.msi) e fazer as configurações necessárias. Basta seguir as instruções que aparecerem no seu terminal. 

{% hint style="info" %}
Se preferir, você também pode seguir com a [**instalação manual**.](manual-installation.md)
{% endhint %}

###  Passo 2: Configurando as variáveis de ambiente

O **PATH** usado no Ritchie para Windows **não é configurado** quando você faz o download.  
  
Enquanto você não tem essa configuração, é preciso entrar na pasta em que o **arquivo** **rit.exe** foi baixado para executar o Ritchie através desse arquivo. Exemplo: **`rit.exe init`**

Você encontrará um guia sobre como definir um caminho aqui : [**Como definir ou alterar a variável de sistema PATH?**](https://www.java.com/en/download/help/path.xml)\*\*\*\*

### Passo 3: Verificando a instalação 

Você pode confirmar se a instalação funcionou rodando esse comando: 

```text
$ rit --version
```

Se tudo estiver configurado, o terminal irá retornar o número da versão atual do Ritchie.

