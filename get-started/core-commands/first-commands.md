---
description: Presentation of some commands showing what can be done with Ritchie
---

# First Commands

## **CONTEXT**

**Commands :**     _`rit set context`    +    `rit show context`    +     `rit delete context`_

![](https://lh6.googleusercontent.com/nSp8JByYbWSojwR4LPk-itqC8Dt23bSmFWf6wzes-oKqRkOFspjGBqNiam8eEI3YOCBp67IQaPpPKZCqXQEiBG56rqyWIAChUdNO1thIdRA46MrNMH5McpCW0zoWOFxYMVkVx2eE)

**Explanation :** These commands are among the most useful and simple of the Ritchie core.

* **set context** allows you to define a context in the session. Thus, information that will be defined within this context can be reused by executing other commands needing this input. This command has a cache in case it is necessary to re-apply a previously used context. 

{% hint style="warning" %}
The reason for this command to exist is to enable the user to have several credentials registered \(github, aws, etc ...\), so if he has credentials in dev, qa and prod, for example, he can create these contexts and set his specific credentials for each one. 

When a new context is used, all your credentials must be set again.
{% endhint %}

* **show context** allows you to check which context is currently defined in the session. 
* **delete context** allows you to remove a context that was defined in the session \(it can be either one that is currently being used, or one that was configured in the set context previously and was saved in the cache\). ****

## **DOCKER COMPOSE**

**Command :** _`rit docker generate compose`_

![](https://lh6.googleusercontent.com/X5kec7ahhVEKNLx8CBJZhZuX7c_yiDcRe4ZJuEcziuGYMgunrFtx82Kq56SNti6DQsB9FK0iNSOG4ALQ-qAbC6TFVllIsksWuQpeRe0jZoDO-1Bmfp2QTvyFloAyFvFG42_O0NWN)

**Explanation** : This command allows you to create a _docker-compose.yml_ file in the directory where the formula is executed. 

The user can choose which tools he wants to include in the file from the inputs requested in the terminal \(if necessary, additional informations are requested\). 

Once the file is created, it is possible to run it normally, via the **docker-compose up** command.

## **SPRING-STARTER**

**Command :** _`rit scaffold generate spring-starter`_

![](https://lh3.googleusercontent.com/IeLvW38X-qEOCUtocOyHmtmCMABBXOIat9GQ6d7lH4Y7nzIcabqrIC7hTd7GfSdQe_1xijuywhgsUAvNQl8RBqsyRrVmvhTn23IlwtxUNZWgypZqtJwOFqCYYDyfBSzOOYHTbE7Q)

**Explanation :** This command allows you to create a project using the Spring framework in the directory where the formula is executed. 

The user can choose between different languages \(java, kotlin, groovy\), modules \(maven, gradle\) and their versions. 

Once the project is created, it is possible to navigate between its folders to access the different files \(as shown in the animation below\) or directly open it with an IDE \(ex: Eclipse, IntelliJ, etc ...\)

![](https://lh5.googleusercontent.com/WZULiXqsu4Ba-GWpYilBrzNFGmDE7AfGfhi-ydhymu-hroJ8GZRcjax1qbJaA5RuwHyTb_PxW1Jx5-_1tnCLGUUo_HeT7EhsHXdGqgqyjOBYiTEuzp0h34XLoObnLwfUYnJjG6bV)

