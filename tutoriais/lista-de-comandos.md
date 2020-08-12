---
description: >-
  Você encontrará nessa seção uma explicação sobre como credenciais funcionam no
  Ritchie.
---

# Como manipular credenciais

## Como configurar?

Você precisa configurar as credenciais do Ritchie para evitar que você informe o mesmo dado diversas vezes no terminal. 

Para fazer isso, basta rodar o comando abaixo:

```text
$ rit set credential
```

O terminal irá retornar essa mensagem terminal will return this message: 

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
? username: user
? token: ********
✔ Github credential saved!
```

{% hint style="info" %}
Você pode conferir os [**arquivos editáveis das fórmulas**](como-implementar-uma-formula.md#arquivos-editaveis) para ver como manipular as credenciais definidas na sessão como parâmetros de input das fórmulas \(no caso, inputs no config.json\).
{% endhint %}

## Como adicionar novos provedores?

Você também pode configurar o Ritchie para adicionar novos provedores no seu espaço de trabalho.

Para fazer isso, basta selecionar a opção "**Add a new**" rodando o comando **`rit set credential`**. 

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

* **Provider name:** name of the new provider. You name it according to your preference.
* **Field name:** name of a credential from this provider. 
* **Field type:** value type of this credential. It can be: plain text or secret. 

Quando você terminar essa configuração, poderá setar as credenciais seguindo as instruções passadas acima. 

{% hint style="warning" %}
Esse provedor, assim como suas informações, serão salvas permanentemente no Ritchie. Você pode ainda adicionar quantos provedores quiser. 
{% endhint %}

## Como usar credenciais como parâmetros de entrada?

Assim que você configurar as credenciais do provedor, poderá usá-la como parâmetro de entrada para o arquivo **`config.json`** das suas fórmulas.

Para fazer isso, basta usar a palavra-chave reservada:**`CREDENTIAL`**

Quando usada como parâmetro de entrada, a credencial terá **2 campos**:

1. **Name:** variável usada para extrair o parâmetro e manipulá-lo dentro do código da fórmula.
2. **Type:** nomenclatura específica para o CLI saber qual credencial usar. 

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
        "name": "git_token", 
        "type": "CREDENTIAL_GITHUB_TOKEN"
    } 
]
```

Se você tiver alguma dúvida com os nomes dos provedores, você pode checar uma lista de credenciais que você já configurou usando o comando abaixo:

```text
$ rit list credential
```

Com **`GITHUB`**, o terminal irá retornar uma resposta como essa:

```text
PROVIDER	 CONTEXT	  CREDENTIAL
github  	 default	  {"token":"***************","username":"***************"}
```

