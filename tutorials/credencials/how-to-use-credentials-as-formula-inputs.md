# Como usar credenciais como parâmetros de entrada

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

