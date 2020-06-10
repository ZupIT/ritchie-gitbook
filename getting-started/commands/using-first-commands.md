# Other commands

## Introduction

After you finish Ritchie's installing process, you are able to run the first commands on our CLI.

We put it together the first commands to help you use the tool. 

## Commands

### Context command

**Commands :**     _`rit set context`    +    `rit show context`    +     `rit delete context`_

![](https://lh6.googleusercontent.com/nSp8JByYbWSojwR4LPk-itqC8Dt23bSmFWf6wzes-oKqRkOFspjGBqNiam8eEI3YOCBp67IQaPpPKZCqXQEiBG56rqyWIAChUdNO1thIdRA46MrNMH5McpCW0zoWOFxYMVkVx2eE)

**Explanation :** These commands are among the most useful and simple of the Ritchie core.

* **set context** allows you to define a context in the session. Thus, information that will be defined within this context can be reused by executing other commands needing this input. This command has a cache in case it is necessary to re-apply a previously used context. 

{% hint style="warning" %}
The reason for this command to exist is to enable the user to have several credentials registered \(github, aws, etc ...\), so if he has credentials in dev, qa and prod, for example, he can create these contexts and set his specific credentials for each one. 

When a new context is used, all your credentials must be set again.
{% endhint %}

* **show context** allows you to check which context is currently defined in the session. 
* **delete context** allows you to remove a context that was defined in the session \(it can be either one that is currently being used, or one that was configured in the set context previously and was saved in the cache\).

### 

### Spring starter command

**Command :** _`rit scaffold generate spring-starter`_

![](https://lh3.googleusercontent.com/IeLvW38X-qEOCUtocOyHmtmCMABBXOIat9GQ6d7lH4Y7nzIcabqrIC7hTd7GfSdQe_1xijuywhgsUAvNQl8RBqsyRrVmvhTn23IlwtxUNZWgypZqtJwOFqCYYDyfBSzOOYHTbE7Q)

**Explanation :** This command allows you to create a project using the Spring framework in the directory where the formula is executed. 

The user can choose between different languages \(java, kotlin, groovy\), modules \(maven, gradle\) and their versions. 

Once the project is created, it is possible to navigate between its folders to access the different files \(as shown in the animation below\) or directly open it with an IDE \(ex: Eclipse, IntelliJ, etc ...\)

![](https://lh5.googleusercontent.com/WZULiXqsu4Ba-GWpYilBrzNFGmDE7AfGfhi-ydhymu-hroJ8GZRcjax1qbJaA5RuwHyTb_PxW1Jx5-_1tnCLGUUo_HeT7EhsHXdGqgqyjOBYiTEuzp0h34XLoObnLwfUYnJjG6bV)

### 

### Docker compose command

**Command :** _`rit docker generate compose`_

![](https://lh6.googleusercontent.com/X5kec7ahhVEKNLx8CBJZhZuX7c_yiDcRe4ZJuEcziuGYMgunrFtx82Kq56SNti6DQsB9FK0iNSOG4ALQ-qAbC6TFVllIsksWuQpeRe0jZoDO-1Bmfp2QTvyFloAyFvFG42_O0NWN)

**Explanation** : This command allows you to create a _docker-compose.yml_ file in the directory where the formula is executed. 

The user can choose which tools he wants to include in the file from the inputs requested in the terminal \(if necessary, additional informations are requested\). 

Once the file is created, it is possible to run it normally, via the **docker-compose up** command.

{% hint style="info" %}
When using docker-compose up, it is necessary to have docker installed. 
{% endhint %}

### \*\*\*\*

### **Credentials command**

The **`rit set credential`**command allows to save credentials in the session \(locally in the Single version, in the Vault in the Team version\) for the user to take advantage of this data without having to inform them again when executing their formulas.

To use these credentials as inputs to a formula, there is a keyword that needs to be entered in the formula's **config.json** file. 

{% hint style="warning" %}
This file is where the **input** **parameters** that will be requested from the user when he will execute the command in the terminal to process the formula are configured. 

That keyword is **CREDENTIAL**. 
{% endhint %}

To know how to use it, you need to have access to the `ritchie-server` repository, and observe how the credentials of each tool are registered in the `resources/file_config_local.json` file. 

For example, **Github credentials** are configured as follows:

```text
"credentials": { 
    "github": [ 
        { 
            "field": "username", 
            "type": "text" 
        },
        { 
            "field": "token", 
            "type": "password" 
        }  
    ] 
}
```

Therefore, to be able to use Github credentials as input to a formula's `config.json`, I would need to inform them as follows:

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

When the formula command will be executed, the Github credentials will be fetched directly in the session, and can be used in the formulas without the user informing them again at the terminal. 

{% hint style="warning" %}
Remembering that the user must have logged in, and set the credentials \(**rit set credential**\) for this to work.
{% endhint %}

With the **`rit set credential`** command, it is also possible for a **team admin** to set encrypted credentials into the session of specific users to allow them to execute commands without having access to any confidential informations.

