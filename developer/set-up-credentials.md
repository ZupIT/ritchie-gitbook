---
description: You will find in this section how to set credentials on Ritchie.
---

# Credentials

## How to set up?

You have to set Ritchie's credentials to avoid informing datas multiples times through the terminal.

To do so, just run the following command: 

```text
$ rit set credential
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
You can check out on [**formula's editable files**](../how-to/implement-a-formula.md#editable-files) to see how to manipulate the credentials defined in the session as formula input parameters \(inputs in the config.json file\).
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
This provider, as well as its informations, will be saved permanently on Ritchie. You can also add as much providers as you want. 
{% endhint %}

