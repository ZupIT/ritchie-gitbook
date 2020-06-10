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

### **Comando Credenciais** 

Comando: **`$ rit set credential`**

Este comando permite que você configure credenciais no Ritchie, de maneira que você não precisa informar o mesmo dado diversas vezes no terminal.   
  
****Lembrando que, na [**Versão Single**](../escolhendo-versao.md#versao-single), as credenciais são criptografadas localmente na sessão por meio da passphrase informada no[ **processo de inicialização**](../inicializacao.md#versao-single). Já na [**Versão Team**](../escolhendo-versao.md#versao-team), as credenciais são criptografadas na sessão online do **Keycloak** através do **Vault**. 

```text
➜   rit set credential
Use the arrow keys to navigate: ↓ ↑ → ←
Profile to add credential:
  ▸ ME (for you)
     OTHER (for another user)
     ORG (for the organization)
```

Cada um pode configurar suas próprias credenciais**.** No caso da Versão Team, o admin do servidor pode também configurar credenciais para específicos usuários ou para toda a equipe. 

```text
➜  rit set credential
✔ ME (for you)
Use the arrow keys to navigate: ↓ ↑ → ←
Provider:
 ▸ darwin
     email-org
     github
     gitlab
     jenkins
     kubeconfig
     aws
```

Depois que você selecionar as opções para cada perfil, será necessário selecionar para qual provedor deseja adicioná-los. Esta lista será organizada dentro da pasta de configuração do servidor. 

```text
➜  rit set credential
✔ ME (for you)
✔ github
Github username:  user
Github token:  *****
```

  
Uma vez que você selecionar o provider, ele irá solicitar as informações das credenciais selecionadas:

![](https://lh4.googleusercontent.com/_U93uVcs1Tu9TIUy59wuVfDCKgHbqO-lt5pPPSmlmDqwaFG1oew-nG_ntixSNFVRvmknMNca0X2G5WhYAowGS84V3Bf1OCZmurcCnK-Xkn9HZkf67ZWe6Jy6Wi2f9BNL6ggdO4sI)

