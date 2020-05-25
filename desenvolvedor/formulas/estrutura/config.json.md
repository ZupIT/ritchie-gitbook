# Config.json

{% hint style="info" %}
Os parâmetros de entradas das fórmulas são configurados dentro do arquivo **config.json** contido na pasta da fórmula.
{% endhint %}

Esse arquivo contém as seguintes informações :

* uma descrição
* os parâmetros de entrada da fórmula

Esses parâmetros de entrada são compostos dos seguintes campos :

* nome
* tipo
* label
* default \(facultativo\)
* items \(facultativo\)
* cache \(facultativo\)

```text
{
  "description": "Sample inputs in Ritchie.",
  "inputs" : [
    {
      "name" : "sample_text",
      "type" : "text",
      "label" : "Type : ",
      "cache" : {
        "active": true,
        "qtd" : 6,
        "newLabel" : "Type new value. "
      }
    },
    {
      "name" : "sample_list",
      "type" : "text",
      "default" : "in1",
      "items" : ["in_list1", "in_list2", "in_list3", "in_listN"],
      "label" : "Pick your : "
    },
    {
      "name" : "sample_bool",
      "type" : "bool",
      "default" : "false",
      "items" : ["false", "true"],
      "label" : "Pick: "
    }
  ]
}
```



O campo **nome** se refere ao nome da variável que será extraído na implementação da fórmula.

O campo **tipo** representa o tipo da variável \(no momento só existe **TEXT** e **BOOL**\)

O campo **label** é o texto que vai aparecer para o usuário via PROMPT para informar essa variável.

O campo **default** é o valor da variável que virá por padrão caso a escolha seja uma lista de opões.

O campo **items** é a lista de opções possíveis para a variável.

O campo **cache** permite configurar se será necessário armazenar as escolhas do usuário para essa variável. Ele é composto de 3 campos : 

* active
* qtd 
* newLabel.

O campo **active** indica se o cache está habilitado ou não.

O campo **qtd** se refere a quantidade de escolhas que podem ser armazenadas no cache.  
  
O campo **newLabel** é para o usuário informar um outro valor para a variável caso aquelas salvas no cache não atendem sua necessidade.

{% page-ref page="prioridade.md" %}

