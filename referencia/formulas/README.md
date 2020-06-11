# Fórmulas

## Introdução 

As fórmulas são, no contexto do Ritchie, as automações a serem executadas para que você realize uma ação em menos tempo e com mais eficiência. 

{% hint style="info" %}
Para conhecer mais fórmulas disponíveis no Ritchie, acesse o repositório [**ritchie-formulas**](https://github.com/ZupIT/ritchie-formulas) ****no Github. 
{% endhint %}

## Repositório de fórmulas

As fórmulas são armazenadas em **repositórios de fórmulas**, que ****precisam ter uma estrutura particular. 

Cada repositório deve conter os seguintes elementos:

* As pastas das fórmulas.
* Uma pasta tree
* Um arquivo Makefile
* Um arquivo copy-bin-configs.sh 
* Um arquivo unzip-bin-configs.sh

![Reposit&#xF3;rio de f&#xF3;rmulas da comunidade](../../.gitbook/assets/screenshot-2020-05-22-at-17.27.48.png)

Cada **pasta de fórmula** vai conter o código executável e os arquivos referentes a uma fórmula.

A pasta **tree** é composta de um arquivo _**tree.json**_ que vai conter a árvore dos comandos de todas as fórmulas do repositório. 

O arquivo _**Makefile**_ contem uma referência a todas as fórmulas do repositório, assim que um comando executável manipulando os arquivos **copy-bin-configs.sh** e **unzip-bin-configs.sh,** a fim de gerar os arquivos necessários para testar as fórmula\(s\) localmente na [pasta .rit]().

### Composição de fórmulas

{% hint style="info" %}
Cada fórmula é composta de vários arquivos permitindo sua execução pelo CLI.
{% endhint %}

Para uma fórmula ser executada pelo terminal, é preciso ter:

* Um arquivo config.json
* Um arquivo executável

#### Config.json

Arquivo que contém os parâmetros de entrada \(_inputs_\) da fórmula. Ele que permite que o CLI saiba quais informações ele precisará pedir para o usuário quando ele executará o comando no terminal a fim de processar a fórmula corretamente.

#### Arquivo executável 

Arquivo que contém a implementação da fórmula. O CLI vai baixar esse arquivo de acordo com o sistema operacional do computador do usuário e executar essa fórmula enviando os parâmetros de entrada que terão sido informados.

Além destes arquivos, é preciso adequar o **tree.json** para permitir que o CLI reconheça os comandos e sub-comandos associados a fórmula. É assim que ele identifica onde baixar os arquivos da fórmula na primeira execução \(sob demanda\).  


### Tree.json

{% hint style="info" %}
**Cada** repositório de fórmulas do Ritchie tem uma **árvore de comando.**

Essa árvore de comando é configurada num arquivo chamado _**tree.json.**_ 
{% endhint %}

É através desse\(s\) JSON que o CLI vai conseguir localizar os comandos que ele tem acesso, e as informações necessárias para encontrar os executáveis das fórmulas.

A estrutura de um tree.json é a seguinte:

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

Cada comando contido nessa lista pode conter até 4 parâmetros:

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


### Makefile e Shellscripts



## Acesso às fórmulas

{% hint style="info" %}
Todos os **comandos acessíveis pelo CLI** podem ser observados através do _Helper_
{% endhint %}

```text
➜ rit --help

A CLI that developers can build and operate
your applications without help from the infra staff.
Complete documentation is available at https://github.com/ZupIT/ritchie-cli

core commands:
  add         add objects
  completion  Add autocomplete for terminal
  clean       clean objects
  create      Create objects
  delete      Delete objects
  list        list objects
  set         Set objects
  show        Show objects
  update      update objects

commons commands:
  aws         Apply Aws objects
  docker      Manipulate docker objects
  github      Manipulate GitHub objects
  k8s         Manipulate k8s objects
  kafka       Kafka commands
  scaffold    Manipulate scaffold objects

Other Commands:

Options:
  -v, --version: version for rit

Usage:
  rit [flags] [options]

Use "rit <command> --help" for more information about a given command.
```

Quando um usuário vai baixar o Ritchie \([versão Single]()\) ou efetuar o comando **rit login** \([versão Team]()\) para acessar o repositório de uma organização, o **CLI** vai baixar e realizar o merge dos _tree.json_ dos repositórios de fórmulas aos quais o usuário tem acesso. 



![](../../.gitbook/assets/fluxo-cli.png)

A junção das árvores dos repositórios será a árvore de todos os comandos disponíveis via o CLI no computador do usuário, que é apresentada no _Helper_.

## Prioridade entre repositórios 

{% hint style="info" %}
Existe um conceito de **prioridade** entre as árvores de comando dos **repositórios de fórmulas.**

Isso permite **evitar** **comandos** **repetitivos** após a junção das árvores de todos os comandos pelo CLI.
{% endhint %}

Segue a prioridade padrão definida no CLI entre os repositórios :

* Prioridade 0: Core
* Prioridade 1: Local
* Prioridade 2: Outros repositórios 

Essa regra permite que cada usuário \(single\) / empresa \(team\) defina a prioridade entre os demais repositórios.

### **Exemplos de prioridade**

É possível um usuário escolher entre os 2 cenários abaixo :

![](https://lh4.googleusercontent.com/XwM1MIenWGVB45DjC1A7-t_glfsYaznphkJMe7Bcxaa6RJpmy9pRBVW9hNaNw_LFJO5iEl4Zx9uNGAgpxLkPa6awswyeb_D7JktkN6M-Wntc0ad5e26LHE4I3PjoQe3Wnh29JpES)![](https://lh5.googleusercontent.com/h-6piqq1Yl-T7veYMe5rrlVWGi22P4RMs0Y3vcYn-sITSkW2w2SCXR9NjPq0jgcRwWpZnCTmIoO7jXJgc4hm9-3y1Q9SKyQwl75PtTSow4IIEoZ53Tx71FIkNIl6QsNHOrn_nUca)  
****

#### **Cenário 1**

Seria dado prioridade aos comandos **commons** sobre os comandos do seu **time**.

#### **Cenário 2**

Seria dado prioridade aos comandos do repositório do **time** sobre os comandos **commons**. 

Isso permitiria por exemplo a um usuário, ou time, de usar um comando que está na árvore do repositório do **ritchie-formulas** para uma fórmulas no repositório dele, realizando uma operação diferente com o mesmo comando, já que teria prioridade.  
****

{% hint style="warning" %}
É possível configurar a prioridade entre os repositórios na pasta **repo** da [pasta .rit]() onde tem um arquivo **repositories.json** configurável.

Por mais informações sobre como manipular repositórios, confere a documentação aqui :[ Repositório.](https://docs.ritchiecli.io/v/doc-portuguese/primeiros-passos-1/comandos/repositorio)
{% endhint %}



