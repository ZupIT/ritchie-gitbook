---
description: Description of Ritchie current core commands
---

# Commands

Core commands are executed using **rit** + command **verb** + command **noun**

<table>
  <thead>
    <tr>
      <th style="text-align:left">Core Command</th>
      <th style="text-align:left">Operation</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td style="text-align:left"><a href="https://docs.ritchiecli.io/get-started/core-commands/repository#add-other-repositories">rit add repo</a>
      </td>
      <td style="text-align:left">add a new repository tree
        <br />(to access repository formulas with Ritchie)</td>
    </tr>
    <tr>
      <td style="text-align:left"><a href="https://docs.ritchiecli.io/get-started/core-commands/repository#clean-a-repository">rit clean repo</a>
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
      <td style="text-align:left"><a href="https://docs.ritchiecli.io/resources-1/first-formula">rit create formula</a>
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
      <td style="text-align:left"><a href="https://docs.ritchiecli.io/get-started/core-commands/repository#delete-a-repository">rit delete repo</a>
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
      <td style="text-align:left"><a href="https://docs.ritchiecli.io/get-started/core-commands/first-commands#context">rit delete context</a>
      </td>
      <td style="text-align:left">delete a context form the session</td>
    </tr>
    <tr>
      <td style="text-align:left"><a href="https://docs.ritchiecli.io/get-started/core-commands/repository#delete-a-repository">rit list repo</a>
      </td>
      <td style="text-align:left">list all repository that Ritchie has access on the computer</td>
    </tr>
    <tr>
      <td style="text-align:left"><a href="https://docs.ritchiecli.io/software-architecture-1/security#login-command">rit login</a>
      </td>
      <td style="text-align:left">user login to a team (creating a session)</td>
    </tr>
    <tr>
      <td style="text-align:left"><a href="https://docs.ritchiecli.io/software-architecture-1/security#login-command">rit logout</a>
      </td>
      <td style="text-align:left">user logout from session</td>
    </tr>
    <tr>
      <td style="text-align:left"><a href="https://docs.ritchiecli.io/software-architecture-1/security#credentials">rit set credential</a>
      </td>
      <td style="text-align:left">set new credentials into the session</td>
    </tr>
    <tr>
      <td style="text-align:left"><a href="https://docs.ritchiecli.io/get-started/core-commands/first-commands#context">rit set context</a>
      </td>
      <td style="text-align:left">set a new context into the session</td>
    </tr>
    <tr>
      <td style="text-align:left">rit set server</td>
      <td style="text-align:left">set the team server URL (<b>Team version</b>)</td>
    </tr>
    <tr>
      <td style="text-align:left"><a href="https://docs.ritchiecli.io/get-started/core-commands/first-commands#context">rit show context</a>
      </td>
      <td style="text-align:left">show the current session context</td>
    </tr>
    <tr>
      <td style="text-align:left"><a href="https://docs.ritchiecli.io/get-started/core-commands/repository#update-a-repository">rit update repo</a>
      </td>
      <td style="text-align:left">update all repositories tree
        <br />(to access new formulas from those repositories with Ritchie)</td>
    </tr>
  </tbody>
</table>

| Flags | Operation |
| :--- | :--- |
| rit --help | Help for any Ritchie command |
| rit --version | Display Ritchie current version |



![rit --help command](../../.gitbook/assets/rit-help.png)

