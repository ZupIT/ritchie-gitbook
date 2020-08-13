---
description: Você irá encontrar nessa seção como implementar as fórmulas no Ritchie.
---

# Como implementar fórmulas

## Como implementar? 

Uma vez que você [**criou e testou sua fórmula**](como-criar-formulas.md), o Ritchie irá gerar uma estrutura de arquivos dentro do seu workspace. Com isso, você pode começar a implementar a nova automação ao atualizar o template do "Hello World". 

### Arquivos editáveis  

Para fazer essa configuração, você terá que atualizar **2 arquivos** localizados dentro do **/src package**  da pasta root da sua nova fórmula. 

#### 1.  **`config.json`**

O arquivo config.json contém os parâmetros de entrada da fórmula. Ele permite que o CLI saiba quais dados devem ser pedidos ao usuário quando ele executa o comando no terminal, a fim de que processe a fórmula corretamente. 

Essas entradas são feitas para os seguintes campos: 

* uma imagem para _buildar_ o docker
* os parâmetros de entrada de uma fórmula.

Outras informações disponíveis nesse arquivo são: 

* `name` : nome de variável para extração.
* `type` : _**text**_ \(string\), _**bool**_ \(boolean\) or _**password**_ \(hidden string\).
* `label`  : texto que aparecerá no CLI para pedir o input ao usuário.
* `default` \(_optional_\) : valor padrão do parâmetro \(se nulo\).
* `items` \(_optional_\) : lista de opções para o parâmetro.
* `cache` \(_optional_\) : 
  * `active`: se o cache é habilitado ou não.
  * `qty`: quantidade de valor armazenadas no cache.
  * `newLabel`: texto que aparecerá no CLI para pedir um novo input ao usuário.

#### 2. **`main file`**

O **main.file** é usado geralmente para extrair as entradas que são pedidas com o arquivo config.json e então são chamados um ou mais métodos para fazer uma operação \(de tarefas/automação\) usando os parâmetros de entrada.   


#### 3. `/pkg folder`

Pasta em que os arquivos podem mudar o comportamento das fórmulas.  Métodos chamados pelo main.file estão localizados dentro desta pasta.

{% hint style="info" %}
Dependendo da linguagem de programação que você escolher, pode ser necessário atualizar outros arquivos como, por exemplo, para manipular dependências.
{% endhint %}

Veja um exemplo abaixo dessa estrutura \(nesse caso, a fórmula criada em Golang\):

{% tabs %}
{% tab title="Golang" %}
![](../.gitbook/assets/estrutura.png)

Assim como na imagem acima, você deve editar os arquivos:

* **config.json:** alterar os inputs.
* **main.go:** extrair os inputs, e chame os métodos da fórmula \(indicada no **pkg/\***\).
* **pkg/\*:** implementar a fórmula.
* **help.json:** alterar a mensagem de descrição.
{% endtab %}
{% endtabs %}

{% hint style="warning" %}
As pastas e suas respectivas estruturas são o que definem o comando, então não é indicado alterar os nomes ou incluir mais pastas/arquivos **que não estejam dentro da pasta src/\***.
{% endhint %}

## Próximos passos

Nessa seção, você viu como implementar uma fórmula no Ritchie. Para continuar configurando sua fórmula: 

👉 Vá para como fazer o [**build de uma fórmula**](build-a-formula.md) ****para continuar os testes nas fórmulas que você criou. 

👉 Vá para ****[**publicar uma fórmula**](como-publicar-formula.md) para saber como transferir seu trabalho para um repositório público

