# Acesso as fórmulas

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



![](../../../.gitbook/assets/fluxo-cli.png)

A junção das árvores dos repositórios será a árvore de todos os comandos disponíveis via o CLI no computador do usuário, que é apresentada no _Helper_.

{% page-ref page="config.json.md" %}

