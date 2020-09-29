# Spring starter

## Spring starter

**Comando:** _`rit scaffold generate spring-starter`_

![](https://lh3.googleusercontent.com/IeLvW38X-qEOCUtocOyHmtmCMABBXOIat9GQ6d7lH4Y7nzIcabqrIC7hTd7GfSdQe_1xijuywhgsUAvNQl8RBqsyRrVmvhTn23IlwtxUNZWgypZqtJwOFqCYYDyfBSzOOYHTbE7Q)

Este comando permite criar um projeto usando o framework Spring no diretório onde a fórmula é executada. 

O usuário pode escolher quais entre linguagens diferentes \(java, kotlin, groovy\), módulos \(maven, gradle\) e suas versões.

```text
➜  rit scaffold generate spring-starter
✔ maven-project
✔ java
✔ 2.2.5.BUILD-SNAPSHOT
Type your groupId[ex.: br.com.zup]:  br.com.zup
Type your artifactId[ex.: demo]:  dennis
Type the project`s description [ex.: project demo]:  dennis description
✔ jar
✔ 11
Enter the dependencies ids [ex.: web,postgresql]. For list dependencies: 'rit scaffold show spring-starter-dependencies' :  web

16:03:37 Starting scaffold generation...
[ ... ] 
16:03:39 Finished scaffold generation
```

Uma vez que o projeto foi criado, é possível navegar entre os suas pastas para acessar diferentes arquivos \(como mostrado no gif abaixo\) ou abrir diretamente com algum IDE \(Eclipse, IntelliJ, etc\). 

![](https://lh5.googleusercontent.com/WZULiXqsu4Ba-GWpYilBrzNFGmDE7AfGfhi-ydhymu-hroJ8GZRcjax1qbJaA5RuwHyTb_PxW1Jx5-_1tnCLGUUo_HeT7EhsHXdGqgqyjOBYiTEuzp0h34XLoObnLwfUYnJjG6bV)

