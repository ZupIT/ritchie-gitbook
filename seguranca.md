# Segurança

## **Comando do Login**

A partir do comando **`rit login`**, é possível criar uma sessão para armazenar dados que podem ser reaproveitadas em diversas fórmulas.

Portanto, isso não funciona da mesma forma para cada versão:

### Versão Team

Nessa versão, esse comando cria uma sessão usando o _Keycloak_ após o usuário ter informado sua organização com seus dados \(email & senha\). Nessa sessão, o usuário pode, por exemplo, definir suas credenciais para diversas ferramentas \(github, aws, etc…\). 

Nesse caso, as credenciais ficam armazenadas no _Vault_. Isso permite que se o usuário executar o login no Ritchie com seus dados, na máquina de uma outra pessoa, ele conseguirá buscar essas credenciais no _Vault_, apesar de ter configuradas elas na sua máquina local.

### Versão Single 

Já, na versão **Single**, o cenário anterior não é possível, pois esse comando **`rit login`** nem está disponível. 

Essa versão não usa o _Keycloak_, no lugar é criada uma sessão criptografada na máquina do usuário através de um _pathphrase_ que ele precisará informar quando executar o primeiro comando do Ritchie. Aqui, as credenciais não serão mais salvas no _Vault_, mas ficarão criptografadas localmente através do _passphrase_ informado**.**

![Exemplo da formula do login no Ritchie](https://lh5.googleusercontent.com/Nnh0Otg0Re0ogLbSa3qCkJ44LFzl4cRhima-3szJ4SarmQ24OFwH6ii-Y35qcbhBtbL9j6KILGOIz5jKEfT0o2KjFZbjjnbMOjELYO25tMPIPrtdlxDVPIGneGTNbThYIEtvNdH6)

No exemplo acima, podemos observar que o usuário teve acesso a novos comandos após efetuar o login na organização Zup \(versão **Team**\).

{% hint style="warning" %}
O comando**`rit logout`** permite ao usuário finalizar a sessão atual.
{% endhint %}



## Credenciais

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

