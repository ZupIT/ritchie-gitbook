# O que são fórmulas

{% hint style="info" %}
As **fórmulas** nada mais são do que **automações**. Ou seja, são códigos chamados através das linhas de comando para realizar alguma operação.
{% endhint %}

## Sob demanda

A primeira vez que o usuário executa o comando associado a uma fórmula no terminal, é baixado o **arquivo** **executável dessa fórmula** de acordo com o sistema operacional instalado no computador dele.

É nesse momento também que é baixado o arquivo **config.json** com os parâmetros de entradas \(inputs\) da fórmula, necessários para o código implementado no binário / script ser executado.

Esses parâmetros de entrada serão informados pelo usuário :

* após ele digitar o comando no terminal \(se for [via prompt](../usuario/guia-do-usuario/via-prompt/)\)
* antes de digitar o comando no terminal \(se for [via stdin](../usuario/guia-do-usuario/via-stdin/)\)

... antes de executar a fórmula de fato.  
****

![](../.gitbook/assets/fluxo-formulas.png)

## Exemplo de execução de uma fórmula \(via prompt\)

![Segue um exemplo de um comando do Ritchie executado pelo terminal](https://lh3.googleusercontent.com/viskNlV4iXyN63RYhBdgu9I010Rz6nXaliyFKvC9vAHDyrQm2fEPUXzF5l6QclYEoQywEeXYZq3hPQFP_DqGQYJkk38E3nuam4rJQPSdl5zHU6HzP9Q2mEfg3TJeBuacn2geRgx7)

O **`rit scaffold generate coffee`** é um comando executável associado a uma fórmula na árvore do Ritchie.

Como foi a primeira vez que o comando foi executado, foi possível observar que o Ritchie baixo um config file e a fórmula em sequência.

Após baixar os arquivos, o Ritchie pediu algumas informações para o usuário : 

* name
* type of coffee
* delivery. 

Essas informações são os 3 parâmetros de entrada da fórmula.

Uma vez informados esses parâmetros, a fórmula foi executada com sucesso \(conforme o que os logs apresentaram\).

{% page-ref page="arvores-de-comando.md" %}

