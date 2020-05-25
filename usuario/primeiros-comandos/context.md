# Context

**Comandos :**     _`rit set context`    +    `rit show context`    +     `rit delete context`_

![](https://lh6.googleusercontent.com/nSp8JByYbWSojwR4LPk-itqC8Dt23bSmFWf6wzes-oKqRkOFspjGBqNiam8eEI3YOCBp67IQaPpPKZCqXQEiBG56rqyWIAChUdNO1thIdRA46MrNMH5McpCW0zoWOFxYMVkVx2eE)

**Explicação :** Esses comandos são dentro dos mais úteis e simples do core do Ritchie. 

* O **set context:** permite definir um contexto na sessão. Assim, informações que serão definidas dentro desse contexto poderão ser reaproveitadas executando outros comandos precisando desse input. Esse comando possui um cache caso seja necessário voltar a aplicar um contexto já usado anteriormente.

{% hint style="warning" %}
O motivo desse comando existir é possibilitar ao usuário ter várias credenciais cadastradas \(github, aws, etc…\), portanto se ele tem credencial em dev, qa e prod, por exemplo, ele pode criar esses contextos e setar suas credenciais específicas para cada um.

Quando é usado um novo context, todas as suas credenciais devem ser setadas novamente. 
{% endhint %}

O **show context** permite conferir qual contexto está definido atualmente na sessão.  


* O **delete context:** permite remover um contexto que foi definido na sessão \(pode ser tanto um que está sendo usado no momento, ou um que foi configurado no set context anteriormente e ficou salvo no cache\).



