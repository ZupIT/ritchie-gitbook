# Access to formulas

{% hint style="info" %}
All commands **accessible through the CLI** can be observed through the _Helper_
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

When a user will download Ritchie \([Single]() version\) or execute the `rit login` command \([Team]() version\) to access an organization's repositories, the CLI will download and merge the tree.json from the formula repositories to which the user has access.



![](../../.gitbook/assets/fluxo-cli%20%281%29.png)

The junction of the repository trees will be the tree of all commands available via the CLI on the user's computer, which is presented in the _Helper_.

{% page-ref page="config.json.md" %}

