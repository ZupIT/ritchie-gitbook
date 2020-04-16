# Login

## Login Command

Using the `rit login` command, it is possible to create a session to store data that can be reused in different formulas. 

Therefore, this does not work in the same way in each version:

###  Team Version

In this version, this command creates a session using the _Keycloak_ after the user has informed his organization with his data \(email & password\). In this session, the user can, for example, define his credentials for various tools \(github, aws, etc ...\). 

In this case, the credentials are stored in the _Vault_. This allows that if the user logs in to Ritchie with his data, on someone else's machine, he will be able to fetch these credentials from the _Vault_, despite having configured them on his local machine.

### Single Version

In this version, the previous scenario is not possible, as this rit login command is not even available. 

This version does not use _Keycloak_, instead an encrypted session is created on the user's machine through a _pathphrase_ that he will need to inform when executing the first Ritchie command. Here, the credentials will no longer be saved in the _Vault_, but will be encrypted locally via the informed _pathphrase_.

![Example of the login formula being executed in Ritchie](https://lh5.googleusercontent.com/Nnh0Otg0Re0ogLbSa3qCkJ44LFzl4cRhima-3szJ4SarmQ24OFwH6ii-Y35qcbhBtbL9j6KILGOIz5jKEfT0o2KjFZbjjnbMOjELYO25tMPIPrtdlxDVPIGneGTNbThYIEtvNdH6)

In the sample above, we can observe that the user got access to new commands after logging into the Zup organisation \(**Team** version\).

{% hint style="warning" %}
The command `rit logout` allows the user to end the current session.
{% endhint %}

## **Credentials**

The **rit set credential** command allows to save credentials in the session \(locally in the Single version, in the Vault in the Team version\) for the user to take advantage of this data without having to inform them again when executing their formulas.

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

