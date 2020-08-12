---
description: >-
  Você encontrará nessa seção os conceitos dos principais termos e expressões
  usados na doc e/ou no Ritchie.
---

# Principais conceitos

## Fórmulas

As **fórmulas** são **automações**, ou seja, são códigos chamados através das linhas de comando para realizar alguma operação.

## **Execução de fórmulas**

{% hint style="info" %}
As fórmulas são executadas após executar linhas de comando no terminal.
{% endhint %}

Dependendo da fórmula, o usuário pode precisar informar alguns parâmetros de entrada.

Esses parâmetros de entrada podem ser informados de diversas maneiras:

* Depois de executar o comando no terminal \(via **prompt**\)
* Quando digitar a linha de comando no terminal \(via **stdin**\)
* Durante a execução da fórmula \(se o código usou o **prompt**\)

![](.gitbook/assets/start-end-ritchie.jpg)

### Exemplo de execução de uma fórmula \(via prompt\)

![](.gitbook/assets/large-gif-1054x366-.gif)

O **`rit demo hello-world`** é um comando executável associado a uma fórmula na árvore do Ritchie.

Como o comando foi executado pela primeira vez, é possível observar que o Ritchie baixou um _config file_ e a fórmula em sequência.

Após baixar os arquivos, o Ritchie pediu algumas informações para o usuário: 

* Name
* Se você já usou Ritchie  
* O que você quer automatizar 

Essas informações são os **3 parâmetros de entrada** da fórmula.

Uma vez informados esses parâmetros, a fórmula foi executada com sucesso \(conforme logs apresentados\).

## Árvore de comando

{% hint style="info" %}
Para entender a estrutura do produto em si, é importante destacar que **os comandos usados no Ritchie são agrupados como uma árvore**. 
{% endhint %}

No caso do Ritchie, foi seguido o padrão do **Cobra** \(uma biblioteca da linguagem Golang\) usando a seguinte lógica de construção de comandos **core**:

                                                 **RIT + VERBO + SUBSTANTIVO**

E, para permitir mais opções e liberdade aos usuários, também é possível seguir o padrão abaixo na construção de comandos das fórmulas :

                                        **RIT + GRUPO + VERBO + SUBSTANTIVO**

Usamos o prefixo **`rit`** para iniciar nossa árvore de comandos.

![](.gitbook/assets/arvore-rit%20%281%29.png)

{% hint style="warning" %}
O comando **`rit`** é nosso comando pai, ou raíz. Ele não é executável \(significa que ele não vai iniciar nenhuma operação se você usar ele sozinho no terminal\).   
  
É necessário utilizar sub-comandos \(que são comandos filhos, ou ramos, do comando **`rit`**\) executáveis para conseguir iniciar algum processo.
{% endhint %}

Os comandos executáveis no Ritchie são os comandos localizados no último nível da árvore.  
  
****Por exemplo, na imagem acima temos: 

* O comando **rit set context** é executável, pois está no último nível da árvore.
* O comando **rit kafka create** não é executável, pois ele tem um sub-comando **topic** executável no último nível da árvore.

Esse conceito de árvore de comandos é o **núcleo** da estrutura do Ritchie. 

{% hint style="info" %}
Essa árvore é gerada **dinamicamente** pelo CLI baseado nos repositório de fórmulas adicionados localmente  pelo comando**`rit add repo`**.
{% endhint %}

