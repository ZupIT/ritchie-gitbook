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

## Login Command

Using the **`rit login`** command, it is possible to create a session to store data that can be reused in different formulas. 

Therefore, this does not work in the same way in each version:

###  Team Version

In this version, this command creates a session using the _Keycloak_ after the user has informed his organization with his data \(email & password\). In this session, the user can, for example, define his credentials for various tools \(github, aws, etc ...\). 

In this case, the credentials are stored in the _Vault_. This allows that if the user logs in to Ritchie with his data, on someone else's machine, he will be able to fetch these credentials from the _Vault_, despite having configured them on his local machine.

### Single Version

In this version, the previous scenario is not possible, as this **`rit login`** command is not even available. 

This version does not use _Keycloak_, instead an encrypted session is created on the user's machine through a _pathphrase_ that he will need to inform when executing the first Ritchie command. Here, the credentials will no longer be saved in the _Vault_, but will be encrypted locally via the informed _pathphrase_.

![Example of the login formula being executed in Ritchie](https://lh5.googleusercontent.com/Nnh0Otg0Re0ogLbSa3qCkJ44LFzl4cRhima-3szJ4SarmQ24OFwH6ii-Y35qcbhBtbL9j6KILGOIz5jKEfT0o2KjFZbjjnbMOjELYO25tMPIPrtdlxDVPIGneGTNbThYIEtvNdH6)

In the sample above, we can observe that the user got access to new commands after logging into the Zup organisation \(**Team** version\).

{% hint style="warning" %}
The command **`rit logout`** allows the user to end the current session.
{% endhint %}

