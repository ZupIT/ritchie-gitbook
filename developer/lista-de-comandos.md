# Credenciais

## Como configurar?

Você precisa configurar as credenciais do Ritchie para evitar que você informe o mesmo dado diversas vezes no terminal. 

Para fazer isso, basta rodar o comando abaixo:

```text
$ rit set credential
```

O terminal irá retornar essa mensagem terminal will return this message: 

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
? username: user
? token: ********
✔ Github credential saved!
```

{% hint style="info" %}
Você pode conferir os [**arquivos editáveis das fórmulas**](../tutoriais/como-implementar-uma-formula.md#arquivos-editaveis) para ver como manipular as credenciais definidas na sessão como parâmetros de input das fórmulas \(no caso, inputs no config.json\).
{% endhint %}

## Como adicionar novos provedores?

Você também pode configurar o Ritchie para adicionar novos provedores no seu espaço de trabalho.

Para fazer isso, basta selecionar a opção "**Add a new**" rodando o comando **`rit set credential`**. 

```text
? Select your provider Add a new
? Define your provider name: Provider_Name
? Define your field name: (ex.:token, secretAccessKey) token
? Select your field type: secret
? Add more credentials to this provider? no
? token: *****
✔ Provider_Name credential saved!
```

As informações que o Ritchie irá solicitar são:

* **Provider name:** name of the new provider. You name it according to your preference.
* **Field name:** name of a credential from this provider. 
* **Field type:** value type of this credential. It can be: plain text or secret. 

Quando você terminar essa configuração, poderá setar as credenciais seguindo as instruções passadas acima. 

{% hint style="warning" %}
Esse provedor, assim como suas informações, serão salvas permanentemente no Ritchie. Você pode ainda adicionar quantos provedores quiser. 
{% endhint %}

