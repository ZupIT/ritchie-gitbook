---
description: >-
  Nesta seção, você verá como compartilhar suas fórmulas em um repositório já
  criado no Ritchie.
---

# Como compartilhar fórmulas

## Como compartilhar?

Depois que o repositório de fórmulas for publicado, outros usuários podem adicionar suas fórmulas localmente a partir da URL de acesso a elas. 

**Exemplo**: [`https://github.com/ZupIT/ritchie-formulas`](https://github.com/ZupIT/ritchie-formulas)

Para adicionar um novo repositório no Ritchie, é necessário rodar o comando abaixo: 

```text
rit add repo
```

Uma vez que o repositório for adicionado, o Ritchie irá automaticamente usar a última versão da release do  seu repositório para acessar as fórmulas disponíveis.

![rit add repo command demonstration](../.gitbook/assets/rit-add-repo-3.gif)

{% hint style="warning" %}
Note que se o repositório de fórmulas for p**rivado**, será necessário informar o token do seu Github/Gitlab. 
{% endhint %}

Para **checar** **os novos comandos de fórmulas adicionados**, você pode executar o comando **`rit list repo`** para checar seu novo repositório e, então, executar o comando **`rit --help`** para olhar o novo grupo de fórmulas que irá aparecer.

## Próximos passos 

Nesta seção, você viu como compartilhar uma fórmula no Ritchie. Para continuar configurando sua fórmula:

👉 Vá para página [**manipular credenciais**](lista-de-comandos.md) e veja como rodar esse comando com suas fórmulas.

👉 Vá para página de [**lista de comandos**](../developer/lista-de-comandos-1.md) para ver as automações disponíveis no repositório da nossa comunidade. 

