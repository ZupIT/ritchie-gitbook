# Tree.json

{% hint style="info" %}
**Cada** repositório de fórmulas do Ritchie tem uma **árvore de comando.**

Essa árvore de comando é configurada num arquivo chamado _**tree.json**_
{% endhint %}

## Estrutura

É através desse\(s\) JSON que o CLI vai conseguir localizar os comandos que ele tem acesso, e as informações necessárias para encontrar os executáveis das fórmulas.

A estrutura de um tree.json é a seguinte :

```text
{
  "commands": [
    {
      "usage": "aws",
      "help": "Apply Aws objects",
      "parent": "root"
    },
    {
      "usage": "apply",
      "help": "Apply Aws objects",
      "parent": "root_aws"
    },
    {
      "usage": "terraform",
      "help": "Apply Aws terraform objects",
      "formula": {
        "path": "aws/terraform",
        "bin": "terraform-cli-${so}",
        "bundle": "${so}.zip",
        "repoUrl": "https://commons-repo.ritchiecli.io/formulas"
      },
      "parent": "root_aws_apply"
    }
  ]
}
```

Vamos seguir com o exemplo do comando **`RIT AWS APPLY TERRAFORM`**

Cada comando contido nessa lista pode conter até 4 parâmetros :

* usage
* help
* parent
* formula

O campo **usage** se refere a palavra usada no comando \(**aws**, **apply** e **terraforma** no exemplo\).

O campo **help** representa a mensagem de ajuda que aparecerá ao usuário caso ele digite esse comando.

O campo **parent** indica os comandos anteriores na árvore, usando eventualmente um underline \( \_ \) para separar os comandos. ROOT sendo uma palavra reservada fazendo referência ao comando RIT.

Quando um comando contém apenas esses 3 campos \(**usage, help, parent**\) significa que ele não é executável, e que ele faz apenas parte de um conjunto de comandos que juntos executarão uma fórmula.

O campo **formula** vai conter as informações necessárias para o CLI identificar onde buscar os executáveis necessários para executar a fórmula. Ele é composto de 3 campos :

* repoUrl
* path
* bin

O campo **repoUrl** se refere ao endereço onde estão localizados os arquivos executáveis da fórmula.

{% hint style="warning" %}
É importante anotar que o Ritchie não baixa todas as fórmulas na sua instalação. O CLI só baixa os executáveis das fórmulas _on demands_, ou seja, quando ele executa os comandos das fórmulas pela primeira vez. 
{% endhint %}

O campo **path** indica a pasta que será criada localmente no computador do usuário para adicionar esses arquivos executáveis.

O campo **bin** informa qual é o nome do arquivo executável que o CLI deverá baixar, de acordo com o sistema operacional \(SO\) da máquina do usuário.

Executando os comandos da fórmula da AWS acima, existem os seguintes cenários :

* `rit aws` 

```text
Apply Aws objects

Available Commands:
  apply       Apply Aws objects

Use "rit <command> --help" for more information about a given command.
```

* `rit aws apply`

```text
Apply Aws objects

Available Commands:
  terraform   Apply Aws terraform objects

Use "rit <command> --help" for more information about a given command.
```

* `rit aws apply terraform`

```text
Downloading config file...
Done.
Download formula...
Done.
Installing formula...
Directory Created: /Users/Dennis/.rit/formulas/aws/terraform/bin
File extracted: bin/terraform-cli-darwin
Done.
Use the arrow keys to navigate: ↓ ↑ → ←
Select your repository URL:
  ▸ https://github.com/zupit/iti-stack-core
    https://github.com/zupit/iti-stack-tools
```

Os primeiros comandos \(**`rit aws`** e **`rit aws apply`**\) retornaram o campo **help** associado ao comando no _tree.json_, assim que os sub-comandos disponíveis para o usuário conseguir executar uma fórmula.

Já, o comando **`rit aws apply terraform`** baixou os executáveis da fórmula e começou a pedir os parâmetros de entrada ao usuário.

{% page-ref page="acesso-as-formulas.md" %}

