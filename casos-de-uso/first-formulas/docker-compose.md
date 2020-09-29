# Docker compose

## Docker compose <a id="docker-compose"></a>

**Comando:** _`rit docker generate compose`_

![](https://lh6.googleusercontent.com/X5kec7ahhVEKNLx8CBJZhZuX7c_yiDcRe4ZJuEcziuGYMgunrFtx82Kq56SNti6DQsB9FK0iNSOG4ALQ-qAbC6TFVllIsksWuQpeRe0jZoDO-1Bmfp2QTvyFloAyFvFG42_O0NWN)

Este comando permite criar um arquivo **`docker-compose.yml`** na pasta onde a fórmula é executada. 

O usuário pode escolher quais ferramentas ele quer incluir no arquivo a partir dos inputs pedidos no terminal \(se necessário, são pedidos informações adicionais\).

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

Uma vez o arquivo criado, é possível executar ele através normalmente, via o comando **docker-compose up**.

{% hint style="info" %}
No caso do comando **docker-compose up**, é necessário ter o docker instalado na sua máquina.
{% endhint %}

