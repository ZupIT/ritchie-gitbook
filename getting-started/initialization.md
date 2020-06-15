# Initialization

## **Introduction** 

When you finish your[ **installing process**](https://docs.ritchiecli.io/getting-started/installation), it's necessary make the Ritchie's initialization and this procedure varies according to the [**version** ](https://docs.ritchiecli.io/getting-started/choosing-a-version)you're using. 

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

* **if the user want to perform login** to the organization now, or later using the**`rit login`** command.

```text
➜ rit init
Enter your organization:  zup
URL of the server [http(s)://host]:  https://ritchie-server.zup.io
Use the arrow keys to navigate: ↓ ↑ → ←
You can perform login to your organization now, or later using [rit login] command. Perform now?
  ▸ no
    yes
```

### Login Command

On the **Team version**, the **`rit login`** command allows to create a session to store datas that can be reused in different formulas.

```text
➜ rit login
Enter your username:  dennis.ritchie
Enter your password:  **************
Organization: org
Login successfully!
```

This command creates a session using _Keycloak_ after the user has informed his organization with his datas \(email & password\). In this session, the user can, for example, define his credentials for various tools \(github, aws, etc ...\). 

In this case, the credentials are stored in the _Vault_. This allows that if the user logs in to Ritchie with his data, on someone else's machine, he will be able to fetch these credentials from the _Vault_, despite having configured them on his local machine.

{% hint style="warning" %}
The command **`rit logout`** allows the user to end the current session.
{% endhint %}

