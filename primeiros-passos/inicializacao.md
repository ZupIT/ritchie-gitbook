# Inicialização

## **Introdução** 

Quando você finalizar o [**processo de instalação**](https://docs.ritchiecli.io/v/doc-portuguese/primeiros-passos/instalando-ritchie), é preciso realizar a inicialização da ferramenta e este procedimento varia conforme a [**versão**](https://docs.ritchiecli.io/v/doc-portuguese/primeiros-passos/escolhendo-versao) que você estiver utilizando. 

O comando necessário para rodar a inicialização é:**`$ rit init`**

## Versão Single

Para inicializar o Ritchie nesta versão, é necessário executar o comando abaixo, no caso, a **passphrase** que será usada para criptografar as informações localmente. 

```text
➜ rit init
Define a passphrase for your machine: ******
```

## Versão Team

Para inicializar o Ritchie nesta versão, é necessário informar: 

* A **organização** na qual você quer acessar; 
* A **URL do servidor** usada pela organização.

{% hint style="warning" %}
You can't use the **Team** version **without having a configured server**.
{% endhint %}

* **if the user want to perform login** to the organization now, or later using the**`$ rit login`** command.

```text
➜ rit init
Enter your organization:  zup
URL of the server [http(s)://host]:  https://ritchie-server.zup.io
Use the arrow keys to navigate: ↓ ↑ → ←
You can perform login to your organization now, or later using [rit login] command. Perform now?
    no
  ▸ yes
```



