---
description: >-
  Você encontrará nessa seção as novidades do Ritchie 2.0 e como migrar as
  fórmulas da versão 1.0 para a nova versão.
---

# Ritchie V1.0 ➡ V2.0

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



## Como migrar fórmulas da versão 1.0 para a 2.0

### **Contexto**

Se você usa a versão 1.0 do Ritchie e deseja migrar para a versão 2.0, **será necessário atualizar a estrutura dos seus repositórios de fórmulas** para ser compatível com a nova versão.

### Como migrar?

Abaixo, segue um **passo a passo** de como você pode fazer isso:

**Passo 1**: Crie um novo repositório do zero usando o comando rit create formula

* Adicionando as mesmas fórmulas usadas no repositório antigo, no repositório novo.

**Passo 2**: Exporte a implementação das  fórmula do repositório antigo para o novo.

* A estrutura continua usando os mesmos arquivos: **`config.json`** , **`main.*`**, **`formula.*`**.
* Copie o código da estrutura antiga para a nova, respeitando o novo layout.

**Passo3**: Publique o novo repositório de fórmulas no **github** ou no **gitlab** \(pode ser **público** ou **privado**\).

**Passo 4**: Gere uma release desse repositório de fórmulas.

**Passo 5**: Adicione o repositório de fórmulas no Ritchie usando o comando **`rit add repo`**.

**Passo 6**: Compartilhe seu repositório de fórmula com sua equipe, seus colegas ou a comunidade.

{% hint style="info" %}
Em case de dúvida, fique à vontade para entrar em contato com a nossa equipe no e-mail **ritchie@zup.com.br** ou **abrindo uma issue** no repositório [**ritchie-formulas**](https://github.com/ZupIT/ritchie-formulas).
{% endhint %}

