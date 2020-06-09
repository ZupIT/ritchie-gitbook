# Initialization

{% hint style="info" %}
**Ritchie** has 2 versions available : **Single** and **Team**. 

Before using the CLI, the user need to configure Ritchie through a specific command, **according to the installed version**.

This command is : **`$ rit init`**
{% endhint %}

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



