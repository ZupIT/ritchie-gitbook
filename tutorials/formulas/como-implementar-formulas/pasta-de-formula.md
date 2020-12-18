---
description: >-
  Você encontra nesta seção mais informação sobre a pasta de uma fórmula no
  Ritchie.
---

# Pasta de fórmula

## O que é uma pasta de fórmula \(formula folder\)? 

Esta pasta contém arquivos com comportamento da fórmula.

{% hint style="warning" %}
A estrutura das pastas define os comandos tree, por isso **não é recomendando que você atualize o nome dessas pastas**, ou inclua mais arquivos e/ou pastas, a menos que seja uma **pasta src/\*.**
{% endhint %}

Cada linguagem de programação possui suas próprias especificidades, mas a estrutura da fórmula é quase a mesma. Não importa em qual linguagem seja usada, ela irá conter:

| Arquivo | Descrição |
| :--- | :--- |
| `config.json` | arquivo para configurar os parâmetros de entrada da fórmula. |
| `main file` | arquivo para extrair variáveis locais. |
| `pkg/formula file` | arquivo para implementar a operação da fórmula.  |
| `Dockerfile` | arquivo para "buildar" imagens no Docker.  |
| `README file` | arquivo para explicar o que faz uma fórmula. |
| `Makefile file` | arquivo para compilar o código da fórmula \(_será depreciado em 03/2021_\). |
| `build.sh file` | arquivo para compilar o código da fórmula em shell |
| `metadata.json file` | arquivo para "taguear" informações de uma fórmula  |
| `set_unmask.sh file` | arquivo usado pelo `Makefile file` |
| `help.json files` | arquivos usados para configurar mensagens de ajuda da fórmula no CLI. |

Você pode encontrar todos os [**templates de linguagens**](https://github.com/ZupIT/ritchie-formulas/tree/master/templates/create_formula/languages) no repositório ritchie-formulas.

### Exemplos de pastas de fórmulas 

{% tabs %}
{% tab title="Golang" %}
![](../../../.gitbook/assets/go%20%281%29.png)

De acordo com a imagem acima, você deve editar os arquivos:

* **config.json:** alterar os _**inputs**_ e suas configurações.
* **main.go:** extrair os inputs, e chamar os métodos da fórmula \(na pasta **formula/\***\).
* **formula/\*:** implementar a lógica da fórmula.
* **help.json:** alterar a mensagem de descrição do comando ou sub-comando.
{% endtab %}

{% tab title="Java" %}
![](../../../.gitbook/assets/java%20%282%29.png)

De acordo com a imagem acima, você deve editar os arquivos:

* **config.json:** alterar os _**inputs**_ e suas configurações.
* **main.java:** extrair os inputs, e chamar os métodos da fórmula \(na pasta **formula/\***\).
* **formula/\*:** implementar a lógica da fórmula.
* **help.json:** alterar a mensagem de descrição do comando ou sub-comando.
{% endtab %}

{% tab title="Node" %}
![](../../../.gitbook/assets/node%20%283%29.png)

De acordo com a imagem acima, você deve editar os arquivos:

* **config.json:** alterar os _**inputs**_ e suas configurações.
* **index.js:** extrair os inputs, e chamar os métodos da fórmula \(na pasta **formula/\***\).
* **formula/\*:** implementar a lógica da fórmula.
* **help.json:** alterar a mensagem de descrição do comando ou sub-comando.
{% endtab %}

{% tab title="Python" %}
![](../../../.gitbook/assets/python%20%282%29.png)

De acordo com a imagem acima, você deve editar os arquivos:

* **config.json:** alterar os _**inputs**_ e suas configurações.
* **main.py:** extrair os inputs, e chamar os métodos da fórmula \(na pasta **formula/\***\).
* **formula/\*:** implementar a lógica da fórmula.
* **help.json:** alterar a mensagem de descrição do comando ou sub-comando.
{% endtab %}

{% tab title="Shell" %}
![](../../../.gitbook/assets/shell%20%282%29.png)

De acordo com a imagem acima, você deve editar os arquivos:

* **config.json:** alterar os _**inputs**_ e suas configurações.
* **main.sh:** extrair os inputs, e chamar os métodos da fórmula \(na pasta **formula/\***\).
* **formula/\*:** implementar a lógica da fórmula.
* **help.json:** alterar a mensagem de descrição do comando ou sub-comando.
{% endtab %}
{% endtabs %}

{% hint style="warning" %}
As pastas e suas respectivas estruturas são o que definem o comando, então não é indicado alterar os nomes ou incluir mais pastas/arquivos **que não estejam dentro da pasta src/\***.
{% endhint %}

