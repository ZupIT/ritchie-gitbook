---
description: Você encontrará nessa seção como instalar o Ritchie para MacOs.
---

# MacOS

Para instalar a **última versão do Ritchie**, você precisa executar o comando abaixo no seu terminal. Porém, é importante ter em mente que existem alguns requisitos antes de iniciar a instalação no MacOS.

### Requisitos

Se você quiser usar o Ritchie no MacOs, é interessante que você já tenha configurado alguns elementos:

* O comando **make** \([**Veja como usar "make" no macOS**](https://stackoverflow.com/questions/1469994/using-make-on-os-x)\)
* Ferramentas **md5sum**

{% hint style="warning" %}
Para instalar **md5sum** com _**Homebrew**_ , use: `brew install md5sha1sum`

Para instalar **md5sum** com _**MacPorts**_ , use: `sudo port install md5sha1sum`
{% endhint %}

### Comando de instalação

Copie e cole o comando abaixo para executar no terminal: 

```text
curl -fsSL https://commons-repo.ritchiecli.io/install.sh | bash
```

{% hint style="info" %}
Se preferir, você também pode seguir com a [**instalação manual**.]()
{% endhint %}

### Verificando a instalação 

Você pode confirmar se a instalação funcionou rodando esse comando: 

```text
$ rit --version
```

Se tudo estiver configurado, o terminal irá retornar o número da versão atual do Ritchie.

