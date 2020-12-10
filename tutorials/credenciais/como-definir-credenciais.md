# Como definir credenciais

Você pode definir as credenciais do Ritchie para não precisar ficar informando os mesmos dados diversas vezes no terminal. 

Para fazer isso, basta rodar o comando abaixo:

```text
rit set credential
```

O terminal irá retornar essa mensagem:  

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

Depois que escolher um dos provedores disponíveis, o Ritchie irá solicitar que você preencha os seguintes campos:

```text
? Select your provider github
? username: DennisRitchie
? email: dennis.ritchie@zup.com.br
? token: ********
✔ Github credential saved!
```

{% hint style="info" %}
Você pode conferir os [**arquivos editáveis das fórmulas**](../formulas/como-implementar-formulas/#arquivos-editaveis) para ver como **manipular as credenciais definidas na sessão como parâmetros de input** das fórmulas \(no caso, inputs no config.json\).
{% endhint %}

