---
description: 'Nesta seção, você verá como implementar as fórmulas no Ritchie.'
---

# Como implementar fórmulas

## Como implementar? 

Uma vez que você [**criou e testou sua fórmula**](como-criar-formulas.md), o Ritchie irá gerar um workspace para você trabalhar localmente. Com isso, você pode começar a implementar sua automação ao atualizar o template **Hello World**_**.**_ 

### Arquivos editáveis  

Para fazer essa configuração, você terá que atualizar **3 arquivos** localizados dentro do **/src package**  da pasta root da sua nova fórmula. 

#### 1.  **`config.json`**

O arquivo config.json contém os parâmetros de entrada da fórmula. Ele permite que o CLI saiba quais dados devem ser pedidos ao usuário quando ele executa o comando no terminal, a fim de que processe a fórmula corretamente. 

Essas entradas são feitas para os seguintes campos: 

* uma imagem para _buildar_ o docker
* os parâmetros de entrada de uma fórmula.

Outras informações disponíveis nesse arquivo são: 

* `name`: nome de variável para extração. 
* `type`: _**text**_ \(string\), _**bool**_ \(boolean\), _**password**_ \(hidden string\), [_**credenciais**_](https://docs.ritchiecli.io/v/v2.0-pt/tutoriais/lista-de-comandos#como-usar-credenciais-como-parametros-de-entrada) _ou **dynamic** \(funciona com o campo `request_info` abaixo\)_ 
* `label`: texto que aparecerá no CLI para pedir o input ao usuário. 
* `default` \(_opcional_\): valor padrão do parâmetro \(se nulo\).

{% hint style="info" %}
Você também pode fazer essa configuração "padrão" pela flag default, que te permite atribuir valores default configurados na fórmula. 

Caso haja campos sem valor default, a flag continuará pedindo por esses parâmetros que devem estar configurados no seu arquivo config.json.
{% endhint %}

* `required` \(_opcional_\): boolean que indica se um campo é obrigatório ou opcional. 
* `tutorial` \(_opcional_\): campo de ajuda para o parâmetro de entrada _\[? for help\]_ 
* `items` \(_opcional_\) : lista de opções para o parâmetro. 
* `cache` \(_opcional_\) : 
  * `active`: se o cache é habilitado ou não.
  * `qty`: quantidade de valor armazenadas no cache.
  * `newLabel`: texto que aparecerá no CLI para pedir um novo input ao usuário. 
* `condition` \(_opcional_\): Apenas mostra esse parâmetro se a condicional funcionar.
  * `variable`: O nome da variável usada em um parâmetro anterior para comparação.
  * `operator`: O operador lógico usado para comparar. Suporta `==`, `!=`, `<`, `>`, `<=`, and `>=`
  * `value`: O valor que se deseja usar para comparação. 
* `pattern` \(_opcional_\): 
  * `regex`: O  modelo regex para validar o parâmetro.
  * `mismatchText`: A mensagem de erro caso o parâmetro de entrada seja invalidado pelo regex. 
* `requestInfo` _\(opcional\):_
  * `url`: A URL que consome o serviço GET, responsável por retornar a lista de objetos.
  * `jsonPath`: Caminho da variável para extrair da lista retornada uma variável de cada objeto. \(Veja sobre ****[**como funciona o json path**](https://goessner.net/articles/JsonPath/)\).

**Exemplo de uso do input condicional com Regex:**

```text
"inputs": [
    {
      "label": "Select a system:",
      "name": "system",
      "type": "text",
      "required": true,
      "items": [
        "LINUX",
        "MACOS",
        "WINDOWS"
      ]
    },
    {
      "condition": {
        "variable":"system",
        "operator":"==",
        "value":"LINUX"
      },
      "label": "Select a LINUX OS:",
      "name": "linux-os",
      "required": false,
      "type": "text",
      "items": [
        "UBUNTU",
        "FEDORA",
        "CENTOS"
      ],
      "pattern": {
        "regex": "UBUNTU|FEDORA|CENTOS",
        "mismatchText": "Invalid option"
      }
    }
  ]
```

{% hint style="warning" %}
Quando um parâmetro de entrada é informado no Ritchie CLI, ele é salvo como **variável de ambiente** durante a execução da fórmula.
{% endhint %}

#### 2. **`main file`**

* Esse arquivo é usado para extrair os parâmetros de entrada informados no arquivo _**config.json**_. _Os parâmetros de entrada são extraídos a partir do campo **name** definido no arquivo **config.json**._ 
* É nesse arquivo também que são chamados um ou mais métodos para realizar a tarefa / automação da fórmula, manipulando os parâmetros de entrada.  

#### 3. `formula/* folder`

Pasta em que os arquivos podem mudar o comportamento das fórmulas.  Métodos chamados pelo main.file estão localizados dentro desta pasta.

{% hint style="info" %}
Dependendo da linguagem de programação que você escolher, pode ser necessário atualizar outros arquivos como, por exemplo, para manipular dependências.
{% endhint %}

### Exemplos

{% tabs %}
{% tab title="Golang" %}
![](../../.gitbook/assets/go%20%281%29.png)

De acordo com a imagem acima, você deve editar os arquivos:

* **config.json:** alterar os _**inputs**_ e suas configurações.
* **main.go:** extrair os inputs, e chamar os métodos da fórmula \(na pasta **formula/\***\).
* **formula/\*:** implementar a lógica da fórmula.
* **help.json:** alterar a mensagem de descrição do comando ou sub-comando.
{% endtab %}

{% tab title="Java" %}
![](../../.gitbook/assets/java%20%282%29.png)

De acordo com a imagem acima, você deve editar os arquivos:

* **config.json:** alterar os _**inputs**_ e suas configurações.
* **main.java:** extrair os inputs, e chamar os métodos da fórmula \(na pasta **formula/\***\).
* **formula/\*:** implementar a lógica da fórmula.
* **help.json:** alterar a mensagem de descrição do comando ou sub-comando.
{% endtab %}

{% tab title="Node" %}
![](../../.gitbook/assets/node%20%283%29.png)

De acordo com a imagem acima, você deve editar os arquivos:

* **config.json:** alterar os _**inputs**_ e suas configurações.
* **index.js:** extrair os inputs, e chamar os métodos da fórmula \(na pasta **formula/\***\).
* **formula/\*:** implementar a lógica da fórmula.
* **help.json:** alterar a mensagem de descrição do comando ou sub-comando.
{% endtab %}

{% tab title="Python" %}
![](../../.gitbook/assets/python%20%282%29.png)

De acordo com a imagem acima, você deve editar os arquivos:

* **config.json:** alterar os _**inputs**_ e suas configurações.
* **main.py:** extrair os inputs, e chamar os métodos da fórmula \(na pasta **formula/\***\).
* **formula/\*:** implementar a lógica da fórmula.
* **help.json:** alterar a mensagem de descrição do comando ou sub-comando.
{% endtab %}

{% tab title="Shell" %}
![](../../.gitbook/assets/shell%20%282%29.png)

De acordo com a imagem acima, você deve editar os arquivos:

* **config.json:** alterar os _**inputs**_ e suas configurações.
* **main.sh:** extrair os inputs, e chamar os métodos da fórmula \(na pasta **formula/\***\).
* **formula/\*:** implementar a lógica da fórmula.
* **help.json:** alterar a mensagem de descrição do comando ou sub-comando.
{% endtab %}
{% endtabs %}

{% hint style="warning" %}
As pastas e suas respectivas estruturas são o que definem o comando, então não é indicado alterar os nomes ou incluir mais pastas/arquivos **que não estejam dentro da pasta src/\***.
{% endhint %}

## Próximos passos

Nessa seção, você viu como implementar uma fórmula no Ritchie. Para continuar configurando sua fórmula: 

👉 Vá para como fazer o [**build de uma fórmula**](build-a-formula.md) ****para continuar os testes nas fórmulas que você criou. 

👉 Vá para ****[**publicar uma fórmula**](como-publicar-formula.md) para saber como transferir seu trabalho para um repositório público
