---
description: >-
  Nesta seção, você encontrará um passo a passo para usar o conceito de
  encapsulamento de fórmula.
---

# Nível 4: Encapsulamento

## Objetivo

Neste tutorial, a ideia é criar uma fórmula que vai **encapsular outra fórmula dentro dela**.

{% hint style="warning" %}
Você encontrará todas as informações necessárias na seção do tutorial sobre[ **como encapsular fórmulas**](../tutorials/formulas/como-encapsular-formulas.md).
{% endhint %}

A ideia é encapsular pelo menos 2 fórmulas dentro de uma outra:

* **`rit math sum numbers`** \(Nível 1\)
* **`rit math multiply numbers`** \(TODO\)

{% hint style="info" %}
Sugestão de comando: **`rit math calculate`**
{% endhint %}

## Parâmetros de entrada

Essa fórmula deverá conter \(pelo menos\) os três parâmetros de entrada. Veja como abaixo:

1. Number one \(`NUMBER_ONE`\). 
2. Number two \(`NUMBER_TWO`\). 
3. Operation \(`OPERATION`\).

## Passo a passo

Para implementar esta fórmula, será necessário seguir os passos abaixo:   
  
**Premissa**: Criação da fórmula **`rit math multiply numbers`** \(igual ao nível 1\). 

1. Extraia todos os parâmetros de entrada. 
2. Execute a fórmula rit de acordo com a operação selecionada: 
   * **multiply** deve chamar a fórmula **`rit math multiply numbers`**
   * **sum** deve chamar a fórmula **`rit math sum numbers`** 
3. Retorne o resultado no terminal.

## Sugestões de melhorias

Se você quiser testar mais a sua fórmula, é possível configurá-la para que ela:

* Adicione mais operações.
* Adicione a opção de informar qualquer quantidade de números como entradas.

