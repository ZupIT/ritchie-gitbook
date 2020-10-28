---
description: >-
  Nesta seção, você encontrará o passo a passo para usar inputs condicionais no
  Ritchie.
---

# Nível 3: Inputs condicionais

## Objetivo

Neste tutorial, a ideia é criar uma fórmula que vai **retornar a ferramenta selecionada pelo usuário de acordo com seu perfil**.

{% hint style="warning" %}
Você encontrará todas as informações necessárias na seção do tutorial [**relacionada ao arquivo config.json**](https://docs.ritchiecli.io/v/v2.0-pt/tutoriais/como-implementar-uma-formula#1-config-json).
{% endhint %}

{% hint style="info" %}
Sugestão de comando: **`rit get tools`**
{% endhint %}

## Parâmetros de entrada

Essa fórmula deverá conter \(pelo menos\) os two parâmetros de entrada abaixo:

* Profile \(`PROFILE`\). 
* Profile tool \(`TOOL`\).

Os parâmetros de entrada da fórmula deverão respeitar o diagrama abaixo:

![](../.gitbook/assets/ritchie-conditional-inputs.png)

## Passo a passo

A fórmula deverá respeitar os seguintes passos:

1. Extração dos parâmetros de entrada. 
2. Retorno do perfil selecionado no terminal. 
3. Retorna da ferramenta selecionada no terminal.

## Sugestões de melhorias

Se você quiser aprimorar sua fórmula, é possível configurá-la para que ela:

* Instale a ferramenta selecionada de acordo com o SO do computador.

## Próximos passos 

👉 Se você completou o terceiro desafio, vamos para o [**desafio nível 4**](level-4.md)!

