---
description: >-
  Você encontrará nessa seção as novidades do Ritchie 2.0 e como migrar as
  fórmulas da versão 1.0 para a nova versão.
---

# Sobre o Ritchie 2.0

## Diferenças entre as versões 1.0 e 2.0

* As versões Single e Team foram depreciadas.  _Dê uma olhada na dica abaixo se ainda quiser usar elas._ 
* A árvore de comando será gerada dinamicamente a partir dos repositórios adicionados. _Ou seja, não será mais necessário alterar o arquivo tree.json manualmente._ 
* Não terá mais armazenamento de fórmulas na nuvem.  _O usuário poderá importar os repositórios do Github ou do Gitlab ._ \(**`rit add repo`**\) __
* Suporte para autocomplete para 2 novos Shells: **Fish** e **Powershell**. \(**`rit completion fish`** \| **`rit completion powershell`**\) 
* Suporte para executar fórmulas em container. \(**`--docker flag`**\) 
* Suporte para fazer "build" de  fórmulas no Windows. 
* Tutorial incorporado no CLI. 
* Melhorias estruturais.

{% hint style="danger" %}
A versão 2.0 **não suporta o Vault** para compartilhar credenciais. Logo, caso você queira continuar usando essa funcionalidade, precisará ficar na versão 1.0. 
{% endhint %}

