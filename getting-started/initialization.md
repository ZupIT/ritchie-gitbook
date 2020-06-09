# Initialization

## **Introduction** 

When you finish your [**installing process**](https://docs.ritchiecli.io/v/doc-portuguese/primeiros-passos/instalando-ritchie), it's necessary make the Ritchie's initialization and this procedure varies according to the [**version**](https://docs.ritchiecli.io/v/doc-portuguese/primeiros-passos/escolhendo-versao) you're using. 

The command to execute the initialization is:**`$ rit init`**

## Single Version

On this version, it will be necessary to inform :

* a **passphrase** that will be used to encrypt datas locally with Ritchie.

```text
➜ rit init
Define a passphrase for your machine: ******
```

## Team Version

On this version, it will be necessary to inform  :

* the **organization** which the user plan to access.
* the **server URL** used by this organization.

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



