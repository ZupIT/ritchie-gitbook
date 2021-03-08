---
description: Você encontra nesta seção mais informações sobre o arquivo config.json.
---

# Arquivo Config

## O que é um arquivo config \(config.json file\)?

O arquivo config.json contém os parâmetros de entrada da fórmula. Ele permite que o CLI saiba quais dados devem ser pedidos ao usuário quando ele executa o comando no terminal, a fim de que processe a fórmula corretamente. 

Essas entradas são feitas para os seguintes campos: 

* Uma **imagem para buildar o docker** \(de acordo com a linguagem de programação escolhida para criar a fórmula\)
* A lista com os parâmetros de entrada de uma fórmula.

```text
{
  "dockerImageBuilder": "dockerImage",
  "inputs": []
}
```

## Configuração dos parâmetros de entrada

Cada parâmetro de entrada é composto pelos seguintes campos:

### Campos obrigatórios

* `name`: nome da variável para extração.

{% hint style="warning" %}
Uma vez que o valor de um parâmetro de entrada é informado no Ritchie CLI, ele é salvo como uma **variável local** durante a execução da fórmula.  
  
O nome da variável será convertida em maiúscula como o nome da variável local. 
{% endhint %}

> Uma boa prática é adicionar o sufixo _**`RIT_`**_ para cada **`input name`** para evitar conflitos com variáveis locais.  
>   
> Exemplo_: `rit_file_name` --&gt; `RIT_FILE_NAME`_

* `type`: 
  * **text** \(string\), 
  * **list** \(string, associado a uma lista de **items**\)
  * **bool** \(boolean, associado a uma lista de **items\*\***\), 
  * **multiselect** \(string, associado a uma lista de **items**\)
  * **password** \(string escondida no CLI\), 
  * **credentials** _****_\(tipo específico, veja mais sobre [**aqui**](https://docs.ritchiecli.io/tutorials/credentials#how-to-use-credentials-as-formula-inputs)\)
  * **dynamic** \(associado  ao campo opcional`request_info`\)
  * **path:** habilita o `autocomplete` para o usuário informar o passo para uma pasta ou um arquivo \(string\). 
* `label`: texto que aparecerá no CLI para pedir o input ao usuário.

_\*\* os valores da **lista de items** para **booleano** podem ser `true`, `false`, `"yes"` \(string\) ou `"no"` \(string\), onde `"yes"` será convertido para `true` e `"no"` para `false`._

#### Exemplo de parâmetro de entrada com campos obrigatórios:

```text
{
      "label": "Type your name:",
      "name": "rit_name",
      "type": "text",
}
```

#### Exemplo de parâmetro de entrada com o tipo bool:

```text
{
      "label": "I'm of legal age:",
      "name": "rit_legal_age",
      "type": "bool",
      "items": [
           true,
           false
      ]
}
```

#### Exemplo de parâmetro de entrada com o tipo multiselect:

```text
{
      "label": "Choose one or more days: ",
      "name": "rit_days",
      "type": "multiselect",
      "required": true,
      "items": [
           "Monday",
           "Tuesday",
           "Wednesday",
           "Thursday",
           "Friday",
           "Saturday",
           "Friday"
      ]
}
```

#### Algumas observações a respeito o tipo **`multiselect`** 

* Para selecionar uma das opções com tipo `multiselect`, você deve apertar a chave `space` \(a chave`enter` irá mover para o próximo parâmetro de entrada, se houver\)
* As opções selecionadas no campo do tipo `multiselect` irão retornar uma string com as opções separadas por barra \(`|`\) e sem espaço, por exemplo: `Monday | Wednesday | Friday`
* É sugerido que você use o campo `obrigatório` como`true`, caso contrário, se não houver uma opção selecionada, a variável local será salva como `undefined` .

#### Exemplo de parâmetro de entrada usando o tipo autocomplete: 

```text
{
      "label": "Type the path to the folder with your file:",
      "name": "rit_path",
      "type": "path",
}
```

### Campos opcionais

* `default`: valor padrão do parâmetro \(se nulo\).

```text
{
      "label": "Type your name:",
      "name": "rit_name",
      "type": "text",
      "default": "Dennis"
}
```

{% hint style="info" %}
Você pode ainda fazer essa configuração default com a flag default, que te permite atribuir valores default configurados na fórmula.

Caso não haja campos com valor default, a flag continuará perguntando por parâmetros de entrada que devem ser configurados no seu arquivo config.json.
{% endhint %}

* `required`: boolean que indica se um campo é obrigatório ou opcional.

```text
{
      "label": "Type your name:",
      "name": "rit_name",
      "type": "text",
      "required": true
}
```

* `tutorial`: campo de ajuda para o parâmetro de entrada _\[? for help\]_

```text
{
      "label": "Type your name:",
      "name": "rit_name",
      "type": "text",
      "tutorial": "We are expecting you to write your name (ex: John)"
}
```

* `items`: lista de opções para o parâmetro.

```text
{
      "label": "Type your name:",
      "name": "rit_name",
      "type": "text",
      "items": [
            "Dennis",
            "John",
            "Bill"
      ]
}
```

* `cache`:  salva valores de parâmetros de entrada anteriores.
  * `active`: se o cache é habilitado ou não.
  * `qty`: quantidade de valor armazenadas no cache.
  * `newLabel`: texto que aparecerá no CLI para pedir um novo input ao usuário.

```text
{
      "label": "Type your name:",
      "name": "rit_name",
      "type": "text",
      "cache": {
            "active": true,
            "qty": 5,
            "newLabel": "Type another name:"
      }
}

```

* `condition`: esse parâmetro só aparece se condicional funcionar
  * `variable`: o nome da variável usada em um parâmetro anterior para comparação.
  * `operator`: o operador lógico usado para comparar. Suporta `==`, `!=`, `<`, `>`, `<=`, and `>=`
  * `value`: o valor que se deseja usar para comparação.

```text
{
      "label": "Type your name:",
      "name": "rit_name",
      "type": "text",
      "default": "Dennis"
},
{
      "condition": {
            "variable": "rit_name",
            "operator": "!=",
            "value": "Dennis"
      }
      "label": "What is your date of birth?",
      "name": "rit_date_of_birth",
      "type": "text",
}
```

* `pattern`: configura a validação de um parâmetro de entrada.
  * `regex`: o  modelo regex para validar o parâmetro.
  * `mismatchText`: a mensagem de erro caso o parâmetro de entrada seja invalidado pelo regex.

```text
{
      "label": "What is your age",
      "name": "rit_age",
      "type": "text",
      "pattern": {
            "regex": "[0-9]",
            "mismatchText": "Only a numerical value is allowed here (ex: 20)"
      }
}
```

* `requestInfo`: configuração para ter o parâmetro de entrada de tipo dinâmico. 
  * `url`: URL que consome o serviço GET, responsável por retornar a lista de objetos.
  * `jsonPath`: caminho da variável para extrair da lista retornada uma variável de cada objeto. \(Veja mais sobre [**como funciona esse path json**](https://goessner.net/articles/JsonPath/)\).

```text
{
      "label": "Type your name:",
      "name": "rit_name",
      "type": "dynamic",
      "requestInfo": {
            "url": "https://my-url.com",
            "jsonPath": $..users
      }
}
```

{% hint style="info" %}
Cada fórmula contém quantos parâmetros de entrada forem necessários, assim como qualquer associação nos campos acima.
{% endhint %}

**Exemplo de parâmetros de entrada com campo condicional e padrão Regex:**

```text
"inputs": [
    {
      "label": "Select a system:",
      "name": "rit_system",
      "type": "text",
      "items": [
        "LINUX",
        "MACOS",
        "WINDOWS"
      ],
      "required": true,
      "tutorial": "Select a System from the list."   
    },
    {
      "condition": {
        "variable":"rit_system",
        "operator":"==",
        "value":"LINUX"
      },
      "label": "Select a LINUX OS:",
      "name": "rit_linux_os",
      "type": "text",
      "items": [
        "UBUNTU",
        "FEDORA",
        "CENTOS"
      ],
      "pattern": {
        "regex": "UBUNTU|FEDORA|CENTOS",
        "mismatchText": "Invalid option"
      },
      "required": false,
      "tutorial": "Select an Linux Operating System from the list."   
    }
  ]
```

{% hint style="warning" %}
Uma vez que o valor de um parâmetro de entrada é informado no Ritchie CLI, ele é salvo como uma **variável local** durante a execução da fórmula. 
{% endhint %}

