# Via Prompt

## Commands structure

Ritchie core commands are executed following this pattern: 

**`RIT`** `+` **`VERBO`** `+` **`SUBSTANTIVO`**

## Formulas structure

Formula commands are executed following this pattern:

**`RIT`** `+` **`GRUPO`**  `+` **`VERBO`** `+` **`SUBSTANTIVO`**

If you want to see more formulas, check the [**github community repository**](https://github.com/ZupIT/ritchie-formulas)**.**

## Flags

| Flags | Operation |
| :--- | :--- |
| rit --help | Help for any Ritchie command |
| rit --version | Display Ritchie current version |

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

```text
➜ rit --version

rit version 1.0.0-beta.7 (single)
  Build date: 05/20/20_13:29
  Built with: go1.14.3
```

## Core commands

<table>
  <thead>
    <tr>
      <th style="text-align:left">Commands</th>
      <th style="text-align:left">Operation</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td style="text-align:left"><a href="https://docs.ritchiecli.io/getting-started/commands/using-first-commands/repositories#add-other-repositories">rit add repo</a>
      </td>
      <td style="text-align:left">add a new repository tree
        <br />(to access repository formulas with Ritchie)</td>
    </tr>
    <tr>
      <td style="text-align:left"><a href="https://docs.ritchiecli.io/getting-started/commands/using-first-commands/repositories#clean-a-repository">rit clean repo</a>
      </td>
      <td style="text-align:left">clean the cache of a repository</td>
    </tr>
    <tr>
      <td style="text-align:left">rit completion zsh</td>
      <td style="text-align:left">add autocomplete via zsh</td>
    </tr>
    <tr>
      <td style="text-align:left">rit completion bash</td>
      <td style="text-align:left">add autocomplete via bash</td>
    </tr>
    <tr>
      <td style="text-align:left"><a href="../creating-formulas/#step-1-execute-the-formula">rit create formula</a>
      </td>
      <td style="text-align:left">
        <p>create a new formula from scratch</p>
        <p>(as well as a new local repository for test)</p>
      </td>
    </tr>
    <tr>
      <td style="text-align:left">rit create user</td>
      <td style="text-align:left">create a new user (with <em>default</em> role) into the organisation
        <br
        />(only available for <em>admin</em> role on the <b>Team version</b>)</td>
    </tr>
    <tr>
      <td style="text-align:left"><a href="https://docs.ritchiecli.io/getting-started/commands/using-first-commands/repositories#delete-a-repository">rit delete repo</a>
      </td>
      <td style="text-align:left">delete a repository tree
        <br />(to remove access to the repository formulas with Ritchie)</td>
    </tr>
    <tr>
      <td style="text-align:left">rit delete user</td>
      <td style="text-align:left">
        <p>delete a user from the organisation</p>
        <p>(only available for <em>admin</em> role on the <b>Team version</b>)</p>
      </td>
    </tr>
    <tr>
      <td style="text-align:left"><a href="https://docs.ritchiecli.io/getting-started/commands/using-first-commands/context">rit delete context</a>
      </td>
      <td style="text-align:left">delete a context form the session</td>
    </tr>
    <tr>
      <td style="text-align:left"><a href="https://docs.ritchiecli.io/developer/formulas/repository#delete-a-repository">rit list repo</a>
      </td>
      <td style="text-align:left">list all repository that Ritchie has access on the computer</td>
    </tr>
    <tr>
      <td style="text-align:left"><a href="../initialization.md#login-command">rit login</a>
      </td>
      <td style="text-align:left">user login to a team (creating a session)</td>
    </tr>
    <tr>
      <td style="text-align:left"><a href="../initialization.md#login-command">rit logout</a>
      </td>
      <td style="text-align:left">user logout from session</td>
    </tr>
    <tr>
      <td style="text-align:left"><a href="https://docs.ritchiecli.io/getting-started/commands/using-first-commands/credentials#set-credentials">rit set credential</a>
      </td>
      <td style="text-align:left">set new credentials into the session</td>
    </tr>
    <tr>
      <td style="text-align:left"><a href="https://docs.ritchiecli.io/getting-started/commands/using-first-commands/context">rit set context</a>
      </td>
      <td style="text-align:left">set a new context into the session</td>
    </tr>
    <tr>
      <td style="text-align:left">rit set server</td>
      <td style="text-align:left">set the team server URL (<b>Team version</b>)</td>
    </tr>
    <tr>
      <td style="text-align:left"><a href="https://docs.ritchiecli.io/getting-started/commands/using-first-commands/context">rit show context</a>
      </td>
      <td style="text-align:left">show the current session context</td>
    </tr>
    <tr>
      <td style="text-align:left"><a href="https://docs.ritchiecli.io/getting-started/commands/using-first-commands/repositories#update-a-repository">rit update repo</a>
      </td>
      <td style="text-align:left">update all repositories tree
        <br />(to access new formulas from those repositories with Ritchie)</td>
    </tr>
  </tbody>
</table>

