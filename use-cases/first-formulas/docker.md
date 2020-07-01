# Docker compose

## Docker compose

**Command :** _`rit docker generate compose`_

![](https://lh6.googleusercontent.com/X5kec7ahhVEKNLx8CBJZhZuX7c_yiDcRe4ZJuEcziuGYMgunrFtx82Kq56SNti6DQsB9FK0iNSOG4ALQ-qAbC6TFVllIsksWuQpeRe0jZoDO-1Bmfp2QTvyFloAyFvFG42_O0NWN)

**Explanation** : This command allows you to create a _docker-compose.yml_ file in the directory where the formula is executed. 

The user can choose which tools he wants to include in the file from the inputs requested in the terminal \(if necessary, additional informations are requested\). 

```text
➜    rit docker generate compose
Use the arrow keys to navigate: ↓ ↑ → ←
Select docker image:
  ▸ awsclivl
    consul
    dynamoDB
    jaeger
    kafka
    mongo
    postgres
    redis
    stubby4j
    rabbitmq
    finish!
```

```text
➜  rit docker generate compose
✔ kafka
✔ finish!
Generated files in the current directory
Run:
docker-compose up
```

Once the file is created, it is possible to run it normally, via the **docker-compose up** command.

{% hint style="info" %}
When using docker-compose up, it is necessary to have docker installed. 
{% endhint %}

