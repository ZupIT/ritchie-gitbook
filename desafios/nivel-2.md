---
description: >-
  Você encontrará nesta seção desafios para começar a implementar fórmulas
  simples no Ritchie com uma complexidade gradual.
---

# Nível 2: Criando fórmulas que retornem credenciais do Github

## Objetivo da tarefa

Criar uma fórmula que vai **retornar um JSON contendo as credenciais do Github.**

{% hint style="info" %}
Sugestão de comando: **`rit github get credentials`**
{% endhint %}

## Parâmetros de entrada

Essa fórmula deverá conter \(pelo menos\) os two parâmetros de entrada abaixo:

* Username \(`GIT_USER`\).
* Token \( `GIT_TOKEN`\).

{% hint style="warning" %}
**Nota**: O desafio consiste em configurar esses parâmetros de entrada dentro do arquivo config.json, mas executar a fórmula sem informá-los usando **prompt** ou **stdin** \(serão extraídos automaticamente\).

Você encontrará todas as informações de que precisa na seção do tutorial sobre [como manipular credenciais](https://docs.ritchiecli.io/v/v2.0-pt/tutoriais/lista-de-comandos).
{% endhint %}

## Passo a passo

A fórmula deverá respeitar os seguintes passos:

1. Extração dos parâmetros de entrada. 
2. Criação do JSON com as credenciais do Github. 
3. Retorno do resultado no terminal.

{% hint style="success" %}
Parabéns! Você completou a tarefa de nível 2!
{% endhint %}

## Sugestões de melhorias

Se você quiser testar mais a sua fórmula, é possível configurá-la para que ela:

* Desenvolva alguma operação Github manipulando essas credenciais. 
* Codifique uma fórmula que permitirá ao usuário criar um repositório no Github. 
* Codifique uma fórmula que permitirá ao usuário fazer um **add**, **commit** e **push** usando apenas um comando. 
* Codifique uma fórmula que permitirá ao usuário gerar uma **release** do repositório Github informado.

## Próximos passos 

👉 Se você completou o segundo desafio, vamos para o [**terceiro nível**](nivel-3.md)!

