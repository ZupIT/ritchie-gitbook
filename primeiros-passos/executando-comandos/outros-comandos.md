---
description: >-
  Nesta seção, você encontra alguns comandos mostrando o que é possível realizar
  com Ritchie.
---

# Outros comandos

## **Introdução** 

Depois que você finalizar o processo de instalação do Ritchie, você está apto a realizar os primeiros comandos no nosso CLI. 

Por isso, reunimos aqui comandos iniciais para você ganhar confiança no uso da ferramenta. 

## **Comandos** 

### **Comando Context**

**Comandos:**     _`rit set context`    +    `rit show context`    +     `rit delete context`_

![](https://lh6.googleusercontent.com/nSp8JByYbWSojwR4LPk-itqC8Dt23bSmFWf6wzes-oKqRkOFspjGBqNiam8eEI3YOCBp67IQaPpPKZCqXQEiBG56rqyWIAChUdNO1thIdRA46MrNMH5McpCW0zoWOFxYMVkVx2eE)

Estes comandos são dentro dos mais úteis e simples do core do Ritchie. 

* O **set context:** permite definir um contexto na sessão. Assim, informações que serão definidas dentro desse contexto poderão ser reaproveitadas executando outros comandos precisando desse input. Esse comando possui um cache caso seja necessário voltar a aplicar um contexto já usado anteriormente.

{% hint style="warning" %}
O motivo desse comando existir é possibilitar ao usuário ter várias credenciais cadastradas \(github, aws, etc…\), portanto se ele tem credencial em dev, qa e prod, por exemplo, ele pode criar esses contextos e setar suas credenciais específicas para cada um.

Quando é usado um novo context, todas as suas credenciais devem ser setadas novamente. 
{% endhint %}

O **show context** permite conferir qual contexto está definido atualmente na sessão.  


* O **delete context:** permite remover um contexto que foi definido na sessão \(pode ser tanto um que está sendo usado no momento, ou um que foi configurado no set context anteriormente e ficou salvo no cache\).



### **Comando Spring Starter**

**Comando:** _`rit docker generate compose`_

![](https://lh6.googleusercontent.com/X5kec7ahhVEKNLx8CBJZhZuX7c_yiDcRe4ZJuEcziuGYMgunrFtx82Kq56SNti6DQsB9FK0iNSOG4ALQ-qAbC6TFVllIsksWuQpeRe0jZoDO-1Bmfp2QTvyFloAyFvFG42_O0NWN)

Este comando permite criar um arquivo _docker-compose.yml_ na pasta onde a fórmula é executada. 

O usuário pode escolher quais ferramentas ele quer incluir no arquivo a partir dos inputs pedidos no terminal \(se necessário, são pedidos informações adicionais\).

Uma vez o arquivo criado, é possível executar ele através normalmente, via o comando **docker-compose up**.



### Comando Docker Compose 

**Comando:** _`rit docker generate compose`_

Este comando permite criar um arquivo _docker-compose.yml_ na pasta onde a fórmula é executada. 

O usuário pode escolher quais ferramentas ele quer incluir no arquivo a partir dos inputs pedidos no terminal \(se necessário, são pedidos informações adicionais\).

Uma vez o arquivo criado, é possível executar ele através normalmente, via o comando **docker-compose up**.

{% hint style="info" %}
No caso do comando **docker-compose up**, é necessário ter o docker instalado na sua máquina.
{% endhint %}

### **Credentials command**

Comando: **`rit set credential`**

Este comando permite salvar credenciais na sessão \(de maneira local na Versão Single ou pelo Vault, no caso da Versão Team\) para que você tenha a vantagem de usar essa informação sem precisar informá-la de novo quando for executar suas fórmulas.  

Para usar as credenciais como inputs para fórmula, é precisa ter uma **palavra-chave** que será usada dentro do **arquivo config.json**.

{% hint style="warning" %}
No caso do Ritchie, esta palavra-chave é **CREDENTIAL**. 

Vale reforçar também que este é o arquivo no qual os **parâmetros de entrada** serão requisitados quando você for executar o comando no terminal para configurar a fórmula.  
{% endhint %}

Seguindo o processo, você vai precisar acessar o repositório `ritchie-server` e observar como as credenciais de cada ferramentas são registradas no arquivo `resources/file_config_local.json`. 

Por exemplo, as **credenciais do Github** são configuradas da seguinte forma:

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

Uma vez feito isso, você precisará preencher os seguintes campos. Desta forma, você garante que o Ritchie te habilitará para usar as credenciais como inputs para o `config.json` da fórmula.

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

Quando o comando da fórmula for executado, as credenciais do Github irão buscá-la diretamente na sessão e poderão ser usadas nas fórmulas sem precisar informá-la de novo no terminal.

{% hint style="warning" %}
Vale lembrar que você deve estar logado e ter configurado as credenciais pelo **rit set credential** para seguir este processo. 
{% endhint %}

Com o comando **`rit set credential`**, é possível ainda que o **admin do time** configure credenciais criptografadas para serem usadas em uma sessão com usuários específicos, permitindo que eles executem comandos sem precisarem de acesso a informações confidenciais. 

