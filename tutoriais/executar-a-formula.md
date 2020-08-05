---
description: Você encontrará nessa seção como executar uma fórmula no Ritchie.
---

# Como executar uma fórmula

## Como executar?

{% hint style="warning" %}
Por padrão, as fórmulas são executadas de forma local, o que significa que você deve ter instalado as dependências da linguagem que você utiliza para rodar os códigos da fórmula. 

Na prática isso indica que, se você rodar uma fórmula escrita em Node, deve ter o Node instalado na sua máquina. 
{% endhint %}

Isso significa que todas as fórmulas podem ser executadas independente da linguagem usada, a partir do momento que você tenha o Docker instalado. 

Para rodar uma fórmula, use o comando abaixo: 

```text
$ rit github update repository
```

![](../.gitbook/assets/rit-update-repo-3.gif)

Caso você quiser rodar a fórmula usando Docker, apenas execute o comando adicionando **flag --docker**.

```text
$ rit github update repository --docker
```

## Próximos passos 

Nessa seção, você viu como executar uma fórmula no Ritchie. Para continuar aprendendo sobre o Ritchie: 

👉 Cheque a [**lista de comandos**](https://app.gitbook.com/@zup-products/s/ritchie/~/drafts/-MDPWwvUtJ2ZZfV8Mw44/v/v2.0-pt/developer/lista-de-comandos) para ver as automações disponíveis no repo da nossa comunidade. 

