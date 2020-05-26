# Configurações

{% hint style="info" %}
**Na versão Team**, o repositório do ritchie-server prove as configurações para o CLI. 

A inteligência está toda no CLI, e as informações que o CLI precisa para funcionar são fornecidas pelo servidor através desse repositório.

**Cada time** precisa ter um arquivo de configuração para iniciar o seu servidor quando usar o Ritchie. Esse arquivo é o **file\_config.json**. 
{% endhint %}

## Configurar o servidor

O arquivo **file\_config.json** vai conter a parte de configuração e de autorização aos trees e comandos, isso envolve os seguintes campos :

* tenant/time
* keycloak
* cliVersionPath
* repositories
* oauth
* credentials

O **tenant/time** representa o nome da organização que deverá ser informada pelo usuário na hora de fazer o login com o Ritchie na versão Team.

O campo _**keycloak**_ se refere as configurações do client [Keycloak](https://www.keycloak.org/) utilizado pelo server para validar o token e gerenciar o keycloak \(url, realm, clientId e clientSecret\)

O campo _**cliVersionPath**_ informa a URL para o provider afim de identificar a versão do CLI sendo usada.

O campo _**repositories**_ indica as configurações dos repositórios de fórmulas acessíveis pelo time \(com nome, prioridade, treePath, urls\) que o CLI vai usar para baixar os tree.json que ficarão na [pasta .rit](../cli/pasta-.rit.md)

O campo _**oauth**_ contém a URL que será usada para realizar o login via a ferramenta SSO \(Single Sign On\) usada pelo time.

O campo _**credentials**_ contém uma lista das credenciais que podem ser usadas dentro do ambiente da organização, que podem ser definidas tanto pelos usuários, quanto pelos administradores do servidor \(para usuários específicos, ou para o time inteiro\) através do comando **`rit set credential`**.

### Exemplo de um **file\_config.json**

```text
{
  "zup": {
    "keycloak": {
      "url": "http://localhost:8080",
      "realm": "ritchie",
      "clientId": "user-login",
      "clientSecret": "user-login"
    },
    "cliVersionPath": {
      "provider": "s3",
      "url": "http://localhost:8882/s3-version-mock"
    },
    "repositories":
     [
       {
         "name": "commons",
         "priority": 0,
         "treePath": "/tree/tree.json",
         "remote" : "http://localhost:8882",
         "serverUrl" : "http://localhost:3000",
         "replaceRepoUrl" : "http://localhost:3000/formulas"
       },
       {
         "name": "zup",
         "priority": 1,
         "treePath": "/tree/tree-zup.json",
         "remote" : "http://localhost:8882",
         "serverUrl" : "http://localhost:3000",
         "replaceRepoUrl" : "http://localhost:3000/formulas"
       }
     ],

    "oauth" :{
      "url" : "http://localhost:8080/auth/realms/ritchie",
      "clientId" : "oauth"
    },
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
      ],
      "gitlab": [
        {
          "field": "username",
          "type": "text"
        },
        {
          "field": "token",
          "type": "password"
        }
      ],
      "email-zup": [
        {
          "field": "email",
          "type": "text"
        },
        {
          "field": "token",
          "type": "password"
        }
      ]
    }
  }
}
```

## Testar o servidor

Para a versão **Team** funcionar no CLI, a organização vai precisar subir :

* um servidor
* uma conta no [Keycloak](https://www.keycloak.org/) \(ferramenta open source\)
* uma conta no [Vault](https://www.vaultproject.io/) \(ferramenta open source\)

É possível testar essas configurações localmente, observando através de arquivos do Postman \(disponibilizados na pasta **/testdata**\) como os endpoints do servidor são manipulados pelo CLI para funcionar.

Para iniciar esse teste é preciso executar o arquivo **run-local.sh** : `$ sh run-local.sh`

```text
#!/bin/bash

./create-vault-approle.sh . http://0.0.0.0:8200

export VAULT_ADDR=http://localhost:8200
export VAULT_AUTHENTICATION=APPROLE
export VAULT_ROLE_ID=$(cat /tmp/vault/role-id.txt)
export VAULT_SECRET_ID=$(cat /tmp/vault/secret-id.txt)
export FILE_CONFIG="$(pwd)/server/resources/file_config_local.json"

go run server/cmd/server/main.go
```

Em conjunto com o arquivo **docker-compose** : `$ docker-compose up`

```text
version: '3'

services:
  vault:
    image: vault:1.3.0
    ports:
      - "8200:8200"
    volumes:
      - ./resources/vault.hcl:/vault/config/vault.hcl
    environment:
      - VAULT_DEV_ROOT_TOKEN_ID=87e7784b-d598-44fe-8962-c7c345a11eed
      - VAULT_DEV_LISTEN_ADDRESS=0.0.0.0:8200
      - SKIP_SETCAP=true
      - disable_mlock=true

  keycloak:
    image: jboss/keycloak:7.0.0
    environment:
      DB_VENDOR: H2
      KEYCLOAK_IMPORT: /tmp/keycloak/ritchie.json
      KEYCLOAK_USER: admin
      KEYCLOAK_PASSWORD: admin
    ports:
      - "8080:8080"
    volumes:
      - ./testdata/security/keycloak:/tmp/keycloak

  stubby4j:
    image: sandokandias/stubby4j-docker
    ports:
      - "8787:8787"
      - "8882:8882"
    environment:
      STUBBY_PORT: 8882
    volumes:
      - ./testdata/stubby4j/integrations.yml:/usr/local/stubby.yml
      - ./testdata/stubby4j/response.zip:/usr/local/response.zip
```

Esses 2 arquivos funcionam em conjunto com o **file\_config-local.json** localizado na pasta **/server/resources** do repositório do ritchie-server.

Uma que tudo estiver subido será possível executar as requisições via Postman que o CLI envia para o servidor para buscar as informações necessárias ao seu funcionamento.

{% hint style="warning" %}
Um **comando core** está sendo desenvolvido para permitir que um time consiga criar os arquivos de configurações assim que o realm no kubectl, para conseguir gerar um servidor já funcionando com o Ritchie de forma simplificada.
{% endhint %}

