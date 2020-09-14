---
description: Você encontrará nessa seção como publicar uma fórmula no Ritchie.
---

# Como publicar fórmulas

## Como publicar?

Existe uma fórmula no Ritchie que permite você criar/atualizar o repositório de fórmulas no Github e/ou Gitblab. 

### Premissas

{% hint style="warning" %}
Para publicar a fórmula, confirme se está seguindo estas premissas: 

1. Esta fórmula só pode ser **executada localmente** para **MacOs** ou **Linux**. 
2. É necessário configurar as credenciais do Github e/ou Gitlab usando o comando **`rit set credential.`**
{% endhint %}

## Publicando seu repositório

Você pode usar uma a fórmula que foi criada no repositório da comunidade para fazer:

* A [**inicialização**](../getting-started/initialization.md#passo-1-inicializacao) ****em um repositório local do Git \(se necessário\). 
* A criação do repositório no Github e/ou Gitlab,
* A release de uma nova versão do repositório. 
* A adição de um repositório nos repositórios locais do Ritchie \(usando o comando`rit add repo`\). 

{% hint style="info" %}
Além disso, se o repositório já existir, a fórmula irá fazer o commit de um novo código e gerar uma nova release informada antes de atualizar os repositórios do Ritchie \(usando o comando `rit update repo`\)
{% endhint %}

```text
rit publish repo
```

Você deverá informar 5 tipos diferentes de parâmetros de entrada:

1. O **`provedor`** \(Github ou Gitlab\)
2. A **`privacidade do repositório`**
3. O **`nome do repositório`**
4. O **`caminho local do repositório`** you wish to publish
5. A **`versão da release`** para ser gerada

![rit publish repo command](../.gitbook/assets/rit-publish-repo.gif)

{% hint style="warning" %}
As shown on the demonstration above, you can check the publication has been successful by using the **`rit list repo`** command and observe if the published repository appears.
{% endhint %}

## Publicando manualmente

To publish a formula manually, you need to push it on a **Github / Gitlab** repository, following these steps:

1. Have an exclusive repository for formulas on Github / Gitlab.

   _It can be created from the a local repository, or based on a cloned repository._  

2. Add your formulas to the repository  _Using the**`rit create formula`** command, or **copy / paste** folders**.**_ 
3. Commit and push the new code to the Github / Gitlab repository. 
4. Generate a new release of the formulas repository.

## Next steps 

On this section, you saw how to publish a formula on Ritchie. To keep configuring the formula: 

👉 Check out 

