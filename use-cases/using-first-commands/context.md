# Context

## Context command

**Commands :**     _`rit set context`    +    `rit show context`    +     `rit delete context`_

![](https://lh6.googleusercontent.com/nSp8JByYbWSojwR4LPk-itqC8Dt23bSmFWf6wzes-oKqRkOFspjGBqNiam8eEI3YOCBp67IQaPpPKZCqXQEiBG56rqyWIAChUdNO1thIdRA46MrNMH5McpCW0zoWOFxYMVkVx2eE)

**Explanation :** These commands are among the most useful and simple of the Ritchie core.

* **set context** allows you to define a context in the session. Thus, information that will be defined within this context can be reused by executing other commands needing this input. This command has a cache in case it is necessary to re-apply a previously used context. 

```text
➜  rit set context
✔ Type new context?
New context:  qa
Set context successful!
```

{% hint style="warning" %}
The reason for this command to exist is to enable the user to have several credentials registered \(github, aws, etc ...\), so if he has credentials in dev, qa and prod, for example, he can create these contexts and set his specific credentials for each one. 

When a new context is used, all your credentials must be set again.
{% endhint %}

* **show context** allows you to check which context is currently defined in the session.

```text
➜  rit show context
Current context: qa
```

* **delete context** allows you to remove a context that was defined in the session \(it can be either one that is currently being used, or one that was configured in the set context previously and was saved in the cache\).

```text
➜  rit delete context
✔ Current -> qa
✔ yes
Delete context successful!
```

