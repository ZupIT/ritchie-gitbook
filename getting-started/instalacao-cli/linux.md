---
description: 'Nesta seção, você verá como instalar o Ritchie para Linux.'
---

# Linux

## Passo 1: Requisitos

Para instalar e usar o Ritchie no Linux na versão **`2.0.5 ou anterior`**,  você deve ter o seguinte elemento configurado:

* O comando **make**

Feito isso, basta executar o comando abaixo no seu terminal.

## Passo 2: Rode o comando de instalação

Copie e cole o comando abaixo para executar no terminal: 

```text
curl -fsSL https://commons-repo.ritchiecli.io/install.sh | bash
```

{% hint style="info" %}
Se preferir, você também pode seguir com a [**instalação**](instalacao-manual.md)[ **manual**.](instalacao-manual.md)
{% endhint %}

### Packages

Para baixar um pacote ou uma versão específico, use as URLs abaixo no seu navegador, substituindo o campo **`{VERSION}`** de acordo com a [tag do repositório do projeto](https://github.com/ZupIT/ritchie-cli/tags).

**Red Hat Package Manager**

```text
https://commons-repo.ritchiecli.io/{VERSION}/installer/ritchie.rpm
```

**Debian**

```text
https://commons-repo.ritchiecli.io/{VERSION}/installer/ritchie.deb
```

**Arch Linux**

O pacote **`tar.gz`** é disponível nesta página: [Arch Linux user repository](https://aur.archlinux.org/packages/ritchie-cli/) \([repositório de referência](https://github.com/avelino/ritchie-cli-archpack)\).

## Passo 3: Verifique a instalação 

Você pode confirmar se a instalação funcionou rodando esse comando: 

```text
rit --version
```

Se tudo estiver configurado, o terminal irá retornar o número da versão atual do Ritchie.

