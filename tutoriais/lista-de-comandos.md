---
description: >-
  Nesta seção, você verá uma explicação sobre como credenciais funcionam no
  Ritchie.
---

# Como manipular credenciais

## Como configurar?

Você precisa configurar as credenciais do Ritchie para não precisar ficar informando o mesmo dado diversas vezes no terminal. 

Para fazer isso, basta rodar o comando abaixo:

```text
rit set credential
```

O terminal irá retornar essa mensagem:  

```text
? Select your provider  [Use arrows to move, type to filter]
> kubeconfig
  ansible
  aws
  github
  gitlab
  jenkins
  Add a new
```

Depois que escolher um dos provedores disponíveis, o Ritchie irá solicitar que você preencha os seguintes campos:

```text
? Select your provider github
? username: DennisRitchie
? email: dennis.ritchie@zup.com.br
? token: ********
✔ Github credential saved!
```

{% hint style="info" %}
Você pode conferir os [**arquivos editáveis das fórmulas**](como-implementar-uma-formula.md#arquivos-editaveis) para ver como **manipular as credenciais definidas na sessão como parâmetros de input** das fórmulas \(no caso, inputs no config.json\).
{% endhint %}

## Como adicionar novos provedores?

É possível também configurar o Ritchie para adicionar novos provedores no seu espaço de trabalho. Para fazer isso, basta selecionar a opção "**Add a new**" rodando o comando **`rit set credential`**. 

```text
? Select your provider Add a new
? Define your provider name: Provider_Name
? Define your field name: (ex.:token, secretAccessKey) token
? Select your field type: secret
? Add more credentials to this provider? no
? token: *****
✔ Provider_Name credential saved!
```

As informações que o Ritchie irá solicitar são:

* **Provider name:** Nome do novo provedor. Você pode nomear de acordo com sua preferência**.**
* **Field name:** Nome da credencial que está nesse provedor.
* **Field type:** Tipo de valor dessa credencial. Ele pode ser: **plain text** or **secret**. 

Ao terminar essa configuração, você poderá configurar as credenciais seguindo as instruções passadas acima. 

{% hint style="warning" %}
Esse provedor, assim como suas informações, serão salvas de forma permanente no Ritchie. No entanto, você ainda poderá adicionar quantos provedores quiser. 
{% endhint %}

## Como usar credenciais como parâmetros de entrada?

Assim que você configurar as credenciais do provedor, poderá usá-la como parâmetro de entrada para o arquivo **`config.json`** das suas fórmulas.

Para fazer isso, basta usar a palavra-chave reservada:**`CREDENTIAL`**

Quando usada como parâmetro de entrada, a credencial terá 2 campos:

1. **Name:** Variável usada para extrair o parâmetro e manipulá-lo dentro do código da fórmula.
2. **Type:** Nomenclatura específica para o CLI saber qual credencial usar. 

{% hint style="danger" %}
O **tipo** precisa respeitar o seguinte padrão:**`CREDENTIAL_PROVIDER_VARIABLE`**
{% endhint %}

Por exemplo, para usar as credenciais do **`GITHUB`** como parâmetros, você precisa informá-las no arquivo **`config.json`**da fórmula:

```text
"inputs": [ 
    { 
        "name": "git_user", 
        "type": "CREDENTIAL_GITHUB_USERNAME" 
    },
    { 
        "name": "git_email", 
        "type": "CREDENTIAL_GITHUB_EMAIL" 
    },
    { 
        "name": "git_token", 
        "type": "CREDENTIAL_GITHUB_TOKEN"
    } 
]
```

Se tiver alguma dúvida com os nomes dos provedores, você pode checar uma lista de credenciais que você já configurou usando o comando abaixo:

```text
rit list credential
```

Com **`GITHUB`**, o terminal irá retornar uma resposta como essa:

```text
PROVIDER	 CONTEXT	  CREDENTIAL
github  	 default	  {"token":"***************", "email":"***************", "username":"***************"}
```

## Próximos passos 

Nessa seção, você viu como manipular credenciais no Ritchie. 

👉 Cheque a [**lista de comandos**](https://app.gitbook.com/@zup-products/s/ritchie/~/drafts/-MDPWwvUtJ2ZZfV8Mw44/v/v2.0-pt/developer/lista-de-comandos) para ver as automações disponíveis no repo da nossa comunidade. 

