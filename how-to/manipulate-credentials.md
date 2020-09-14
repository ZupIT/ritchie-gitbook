---
description: 'In this section, you will find how to set credentials on Ritchie.'
---

# How to manipulate credentials

## How to set up?

You have to set Ritchie's credentials to avoid informing data multiples times through the terminal.

To do so, just run the following command: 

```text
rit set credential
```

The terminal will return this message: 

```text
? Select your provider  [Use arrows to move, type to filter]
> kubeconfig
  ansible
  aws
  github
  gitlab
  jenkins
  Add a new
```

After you chose one of the available providers, Ritchie will ask you to fill the following fields: 

```text
? Select your provider github
? username: user
? token: ********
✔ Github credential saved!
```

{% hint style="info" %}
You can check out on [**formula's editable files**](implement-a-formula.md#editable-files) to see how to manipulate the credentials defined in the session as formula input parameters \(inputs in the config.json file\).
{% endhint %}

## How to add a new providers?

You can also configure Ritchie to add new providers on your workspace. 

To do so, just choose "**Add a new**" option when running the **`rit set credential`** command. 

```text
? Select your provider Add a new
? Define your provider name: Provider_Name
? Define your field name: (ex.:token, secretAccessKey) token
? Select your field type: secret
? Add more credentials to this provider? no
? token: *****
✔ Provider_Name credential saved!
```

The informations that will be requested are: 

* **Provider name:** name of the new provider. You name it according to your preference.
* **Field name:** name of a credential from this provider. 
* **Field type:** value type of this credential. It can be: plain text or secret. 

Once you finished this configuration, you set up this credentials following the same instructions you saw above. 

{% hint style="warning" %}
This provider, as well as its informations, will be permanently saved on Ritchie. You can also add as much providers as you want. 
{% endhint %}

## How to use credentials as formula inputs?

Once a provider's credential has been set, it can be used as input in the formula's **`config.json`**file. To do so, it is necessary to use the reserved keyword:**`CREDENTIAL`**

When used as an input, the credential will contain 2 fields:

* The **name** is the variable used to extract the input and manipulate it inside the formula's code.
* The **type** is the specific nomenclature for the CLI to now which credential to use.

{% hint style="danger" %}
The **type** needs to respect the following pattern:**`CREDENTIAL_PROVIDER_VARIABLE`**
{% endhint %}

For example, to be able to use **`GITHUB`** credentials as input, you need to inform them as follows in the formula's **`config.json`**file:

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

If you have any doubt regarding the provider's variable names, you can check the credentials you've set using the following command:

```text
rit list credential
```

With **`GITHUB`**, it will return something like this:

```text
PROVIDER	 CONTEXT	  CREDENTIAL
github  	 default	  {"token":"***************","username":"***************"}
```

## Next steps 

On this section, you saw how to manipulate credentials on Ritchie. To keep configuring the formula: 

👉 Check out our [**list of commands**](../developer/list-of-commands.md) to see the available automations on our community repo. 

