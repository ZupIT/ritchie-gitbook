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

Essas entradas são feitas para os seguintes campos: uma descrição e os parâmetros de entrada de uma fórmula.

Outras informações disponíveis nesse arquivo são: 

* Nome
* Tipo
* Label 
* Default \(opcional\) 
* Itens \(opcional\) 
* Cache \(opcional\)

#### 2. **`main file`**

O **main.file** é usado geralmente para extrair as entradas que são pedidas com o arquivo config.json e então são chamados um ou mais métodos para fazer uma operação \(de tarefas/automação\) usando os parâmetros de entrada.   


#### 3. `/pkg folder`

Pasta em que os arquivos podem mudar o comportamento das fórmulas.  Métodos chamados pelo main.file estão localizados dentro desta pasta.

{% hint style="info" %}
Dependendo da linguagem de programação que você escolher, pode ser necessário atualizar outros arquivos como, por exemplo, para manipular dependências.
{% endhint %}

Veja um exemplo abaixo dessa estrutura \(nesse caso, a fórmula criada em Golang\):

![](../.gitbook/assets/estrutura.png)

Assim como na imagem acima, você deve editar os arquivos:

* **pkg/\*:** alterar o comportamento da fórmula.
* **main.go:** alterar os inputs, a ordem que são requeridos e o nome da função da sua fórmula \(indicada no pkg\).
* **config.json:** alterar os inputs.
* **help.json:** alterar a mensagem de help de acordo com o nível do comando.

As pastas e suas respectivas estruturas são o que definem o comando, então não é indicado alterar os nomes ou incluir mais pastas/arquivos que não estejam dentro da pasta src.

## Qual é a composição de uma fórmula?

{% hint style="info" %}
Cada fórmula é composta por vários arquivos que permitem a sua execução pelo CLI. 
{% endhint %}

Para a fórmula ser executada no terminal, é necessário ter: 

* O arquivo **tree.json** do repositório onde a ****fórmula configurada está localizada.
* Um **arquivo executável.**
* O arquivo [**config.json**](como-implementar-uma-formula.md), como mencionado acima.

O arquivo **tree.json** permite que o CLI saiba quais comandos e subcomandos estão associados com a fórmula. Assim, é como ele identifica onde fazer o download dos arquivos da fórmula na primeira execução \(por demanda\). 

O **arquivo** **executável** contém a implementação da fórmula. O CLI irá fazer o download do arquivo de acordo com o sistema operacional do usuário e executar essa fórmula, enviando os parâmetros de entrada que foram informados. 

## Próximos passos

Nessa seção, você viu como implementar uma fórmula no Ritchie. Para continuar configurando sua fórmula: 

👉 Vá para como fazer o [**build de uma fórmula**](build-a-formula.md) ****para continuar os testes nas fórmulas que você criou. 

👉 Vá para ****[**publicar uma fórmula**](como-publicar-formula.md) para saber como transferir seu trabalho para um repositório público

