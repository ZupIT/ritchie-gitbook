---
description: >-
  Apresentação de alguns comandos mostrando o que é possível realizar com
  Ritchie
---

# Primeiros Comandos

## **CONTEXT**

**Comandos :**     _`rit set context`    +    `rit show context`    +     `rit delete context`_

![](https://lh6.googleusercontent.com/nSp8JByYbWSojwR4LPk-itqC8Dt23bSmFWf6wzes-oKqRkOFspjGBqNiam8eEI3YOCBp67IQaPpPKZCqXQEiBG56rqyWIAChUdNO1thIdRA46MrNMH5McpCW0zoWOFxYMVkVx2eE)

**Explicação :** Esses comandos são dentro dos mais úteis e simples do core do Ritchie. 

* O **set context:** permite definir um contexto na sessão. Assim, informações que serão definidas dentro desse contexto poderão ser reaproveitadas executando outros comandos precisando desse input. Esse comando possui um cache caso seja necessário voltar a aplicar um contexto já usado anteriormente.

{% hint style="warning" %}
O motivo desse comando existir é possibilitar ao usuário ter várias credenciais cadastradas \(github, aws, etc…\), portanto se ele tem credencial em dev, qa e prod, por exemplo, ele pode criar esses contextos e setar suas credenciais específicas para cada um.

Quando é usado um novo context, todas as suas credenciais devem ser setadas novamente. 
{% endhint %}

O **show context** permite conferir qual contexto está definido atualmente na sessão.  


* O **delete context:** permite remover um contexto que foi definido na sessão \(pode ser tanto um que está sendo usado no momento, ou um que foi configurado no set context anteriormente e ficou salvo no cache\). ****

## **DOCKER COMPOSE**

**Comando :** _`rit docker generate compose`_

![](https://lh6.googleusercontent.com/X5kec7ahhVEKNLx8CBJZhZuX7c_yiDcRe4ZJuEcziuGYMgunrFtx82Kq56SNti6DQsB9FK0iNSOG4ALQ-qAbC6TFVllIsksWuQpeRe0jZoDO-1Bmfp2QTvyFloAyFvFG42_O0NWN)

**Explicação** : Esse comando permite criar um arquivo _docker-compose.yml_ na pasta onde a fórmula é executada. 

O usuário pode escolher quais ferramentas ele quer incluir no arquivo a partir dos inputs pedidos no terminal \(se necessário, são pedidos informações adicionais\).

Uma vez o arquivo criado, é possível executar ele através normalmente, via o comando **docker-compose up**.  
****

## **SPRING-STARTER**

**Comando :** _`rit scaffold generate spring-starter`_

![](https://lh3.googleusercontent.com/IeLvW38X-qEOCUtocOyHmtmCMABBXOIat9GQ6d7lH4Y7nzIcabqrIC7hTd7GfSdQe_1xijuywhgsUAvNQl8RBqsyRrVmvhTn23IlwtxUNZWgypZqtJwOFqCYYDyfBSzOOYHTbE7Q)

**Explicação :** Esse comando permite criar um projeto usando o framework Spring no diretório onde é executado a fórmula. 

O usuário poder escolher entre diversas linguagens \(java, kotlin, groovy\), módulos \(maven, gradle\) e suas versões.

Uma vez o projeto criado, é possível navegar entre suas pastas para acessar os diversos arquivos \(conforme animação abaixo\) ou diretamente abrir ele com uma IDE \(ex : Eclipse, IntelliJ, etc...\)  
****

![](https://lh5.googleusercontent.com/WZULiXqsu4Ba-GWpYilBrzNFGmDE7AfGfhi-ydhymu-hroJ8GZRcjax1qbJaA5RuwHyTb_PxW1Jx5-_1tnCLGUUo_HeT7EhsHXdGqgqyjOBYiTEuzp0h34XLoObnLwfUYnJjG6bV)

