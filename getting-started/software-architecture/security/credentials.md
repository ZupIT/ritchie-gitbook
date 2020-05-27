# Credentials

## **Credentials**

The **`rit set credential`**command allows to save credentials in the session \(locally in the Single version, in the Vault in the Team version\) for the user to take advantage of this data without having to inform them again when executing their formulas.

To use these credentials as inputs to a formula, there is a keyword that needs to be entered in the formula's **config.json** file. 

{% hint style="warning" %}
This file is where the **input** **parameters** that will be requested from the user when he will execute the command in the terminal to process the formula are configured. 

That keyword is **CREDENTIAL**. 
{% endhint %}

To know how to use it, you need to have access to the `ritchie-server` repository, and observe how the credentials of each tool are registered in the resources / file\_config\_local.json file. 

For example, Github credentials are configured as follows:

**`"credentials": { "github": [ { "field": "username", "type": "text" },  
{ "field": "token", "type": "password" }  ] }`**

Therefore, to be able to use Github credentials as input to a formula's `config.json`, I would need to inform them as follows:

**`"inputs": [ { "name": "git_user", "type": "CREDENTIAL_GITHUB_USERNAME" },  
{ "name": "git_token",  "type": "CREDENTIAL_GITHUB_TOKEN"} ]`**

When the formula command will be executed, the Github credentials will be fetched directly in the session, and can be used in the formulas without the user informing them again at the terminal. 

{% hint style="warning" %}
Remembering that the user must have logged in, and set the credentials \(**rit set credential**\) for this to work.
{% endhint %}

With the `rit set credential` command, it is also possible for a **team admin** to set encrypted credentials into the session of specific users to allow them to execute commands without having access to any confidential informations.

