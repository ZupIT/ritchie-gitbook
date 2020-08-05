---
description: Você encontrará nessa seção uma lista com principais comandos do Ritchie.
---

# Lista de Comandos

### Comandos de Configuração

| Comandos | Operação |
| :--- | :--- |
| rit init  | initialize Ritchie before use |
| rit upgrade | upgrade to the last Ritchie stable version |
| rit tutorial  | enable or disable the tutorial |
| rit --version | return Ritchie currently installed version |

### Comandos de Repo 

| Comandos | Operação |
| :--- | :--- |
| rit add repo | add a new repository \(to access repository formulas with Ritchie\) |
| rit list repo |  ****show a list with all your available repositories |
| rit update repo | update all repositories  \(to access new formulas from those repositories with Ritchie\) |
| set repo-priority | set a repository priority |
| rit delete repo | delete a repository \(to remove access to the repository formulas with Ritchie\) |

### Comandos de Fórmulas

<table>
  <thead>
    <tr>
      <th style="text-align:left">Comandos</th>
      <th style="text-align:left">Opera&#xE7;&#xE3;o</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td style="text-align:left">rit create formula</td>
      <td style="text-align:left">
        <p>create a new formula from scratch</p>
        <p>(as well as a new local repository if necessary)</p>
      </td>
    </tr>
    <tr>
      <td style="text-align:left">rit build formula</td>
      <td style="text-align:left">build a formula locally for test</td>
    </tr>
    <tr>
      <td style="text-align:left">rit build formula --watch</td>
      <td style="text-align:left">build a formula monitoring the code to update real time changes</td>
    </tr>
  </tbody>
</table>

### Comandos Autocomplete

| Comandos | Operação |
| :--- | :--- |
| rit completion zsh | add autocomplete via zsh |
| rit completion bash | add autocomplete via bash |
| rit completion fish | add autocomplete via fish |
| rit completion powershell | add autocomplete via powershell |

### Comandos de Contexto

| Comandos | Operação |
| :--- | :--- |
| rit set context | set a new context into the session |
| rit show context | show the current session context |
| rit delete context | delete a context from the session |

### Comandos de Credenciais

| Comandos | Operação |
| :--- | :--- |
| rit set credential | set new credentials for the context |
| rit list credential | list all credential names and fields |

