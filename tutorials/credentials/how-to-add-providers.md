# How to add providers

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
* **Field type:** value type of this credential. It can be: **plain text** or **secret**. 

Once you finished this configuration, you set up this credentials following the same instructions you saw above. 

{% hint style="warning" %}
This provider, as well as its informations, will be permanently saved on Ritchie. You can also add as much providers as you want. 
{% endhint %}

