# Credenciais

O comando **`rit set credential`** permitir salvar credenciais na sessão \(localmente na versão Single, no Vault na versão Team\) para o usuário aproveitar esses dados sem precisar informá-los novamente ao executar suas fórmulas.

Para usar essas credenciais como inputs numa fórmula, existe uma palavra chave que precisa ser informado no arquivo config.json da fórmula. 

{% hint style="warning" %}
Esse arquivo é onde são configurados os parâmetros de entrada que serão pedidos ao usuário quando ele executará o comando no terminal para processar a fórmula.

Essa palavra-chave é **CREDENTIAL.**
{% endhint %}

Para saber como usá-la, é preciso ter acesso ao repositório do `ritchie-server`, e observar como as credenciais de cada ferramenta são registrada no arquivo `resources/file_config_local.json`

Por exemplo, as **credenciais do Github** são configuradas da seguinte forma :

```text
"credentials": { 
    "github": [ 
        { 
            "field": "username", 
            "type": "text" 
        },
        { 
            "field": "token", 
            "type": "password" 
        }  
    ] 
}
```

Consequentemente, para conseguir usar as credenciais do Github como input no `config.json` de uma fórmula, precisaria informar eles da seguinte forma :

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

Assim, quando o comando da fórmula será executado, as credenciais do Github serão buscadas diretamente na sessão, e poderão ser usadas na fórmulas sem o usuário informar-las novamente no terminal.

{% hint style="warning" %}
Lembrando que para isso funcionar, é preciso o usuário ter efetuado o login \(rit login\), e ter setado as credenciais referentes a ferramenta \(rit set credential\).
{% endhint %}

Com o comando **`rit set credential`**, também é possível para um **administrador da equipe** definir credenciais criptografadas na sessão de um usuário específico para permitir que ele execute comandos sem ter acesso a informações confidenciais.

