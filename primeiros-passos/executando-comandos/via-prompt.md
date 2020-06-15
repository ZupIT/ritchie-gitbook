# Via prompt

## Estrutura dos comandos 

Os comandos do core do Ritchie são executados seguindo a nomenclatura :  
  
**`RIT`** `+` **`VERBO`** `+` **`SUBSTANTIVO`**

## Estrutura das fórmulas 

Os comandos das fórmulas respeitam a seguinte nomenclatura:

**`RIT`** `+` **`GRUPO`**  `+` **`VERBO`** `+` **`SUBSTANTIVO`**

Caso queira ver mais fórmulas, conheça o [repositório Github da comunidade](https://github.com/ZupIT/ritchie-formulas). 

## Comandos Core

<table>
  <thead>
    <tr>
      <th style="text-align:left"><b>Comandos</b>
      </th>
      <th style="text-align:left">Opera&#xE7;&#xE3;o</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td style="text-align:left"><a href>rit add repo</a>
      </td>
      <td style="text-align:left">adiciona a &#xE1;rvore de um novo reposit&#xF3;rio
        <br />(para ter acesso as f&#xF3;rmulas desse reposit&#xF3;rio com Ritchie)</td>
    </tr>
    <tr>
      <td style="text-align:left"><a href>rit clean repo</a>
      </td>
      <td style="text-align:left">limpa o cache de um reposit&#xF3;rio</td>
    </tr>
    <tr>
      <td style="text-align:left">rit completion zsh</td>
      <td style="text-align:left">adiciona o <em>autocomplete</em> via zsh</td>
    </tr>
    <tr>
      <td style="text-align:left">rit completion bash</td>
      <td style="text-align:left">adiciona o <em>autocomplete</em> via bash</td>
    </tr>
    <tr>
      <td style="text-align:left"><a href="../criando-formulas/#passo-1-executar-a-formula">rit create formula</a>
      </td>
      <td style="text-align:left">
        <p>cria uma nova f&#xF3;rmula</p>
        <p>(assim que um novo reposit&#xF3;rio local para teste)</p>
      </td>
    </tr>
    <tr>
      <td style="text-align:left">rit create user</td>
      <td style="text-align:left">cria um novo usu&#xE1;rio (padr&#xE3;o) na organiza&#xE7;&#xE3;o
        <br />(s&#xF3; dispon&#xED;vel para <em>admin</em> da organiza&#xE7;&#xE3;o na <b>vers&#xE3;o</b>  <b>Team</b>)</td>
    </tr>
    <tr>
      <td style="text-align:left"><a href>rit delete repo</a>
      </td>
      <td style="text-align:left">remove a &#xE1;rvore de um reposit&#xF3;rio
        <br />(para remover o acesso as f&#xF3;rmulas desse reposit&#xF3;rio com Ritchie)</td>
    </tr>
    <tr>
      <td style="text-align:left">rit delete user</td>
      <td style="text-align:left">
        <p>remove um usu&#xE1;rio de uma organiza&#xE7;&#xE3;o</p>
        <p>(s&#xF3; dispon&#xED;vel para <em>admin</em> da organiza&#xE7;&#xE3;o na <b>vers&#xE3;o</b>  <b>Team</b>)</p>
      </td>
    </tr>
    <tr>
      <td style="text-align:left"><a href="primeiras-formulas.md#comando-context">rit delete context</a>
      </td>
      <td style="text-align:left">remove um contexto da sess&#xE3;o</td>
    </tr>
    <tr>
      <td style="text-align:left"><a href>rit list repo</a>
      </td>
      <td style="text-align:left">lista todos os reposit&#xF3;rios que o Ritchie tem acesso no computador</td>
    </tr>
    <tr>
      <td style="text-align:left"><a href="../inicializacao.md#comando-do-login">rit login</a>
      </td>
      <td style="text-align:left">efetua o login para um time (criando uma sess&#xE3;o)</td>
    </tr>
    <tr>
      <td style="text-align:left"><a href="../inicializacao.md#comando-do-login">rit logout</a>
      </td>
      <td style="text-align:left">encerra a sess&#xE3;o do usu&#xE1;rio</td>
    </tr>
    <tr>
      <td style="text-align:left"><a href="primeiras-formulas.md#comando-credenciais">rit set credential</a>
      </td>
      <td style="text-align:left">configura credenciais na sess&#xE3;o</td>
    </tr>
    <tr>
      <td style="text-align:left"><a href="primeiras-formulas.md#comando-context">rit set context</a>
      </td>
      <td style="text-align:left">configura um novo contexto na sess&#xE3;o</td>
    </tr>
    <tr>
      <td style="text-align:left">rit set server</td>
      <td style="text-align:left">configura a URL do servidor do time (<b>vers&#xE3;o Team</b>)</td>
    </tr>
    <tr>
      <td style="text-align:left"><a href="primeiras-formulas.md#comando-context">rit show context</a>
      </td>
      <td style="text-align:left">mostra o contexto usado na sess&#xE3;o atual</td>
    </tr>
    <tr>
      <td style="text-align:left"><a href>rit update repo</a>
      </td>
      <td style="text-align:left">atualiza as &#xE1;rvores de todos os reposit&#xF3;rios
        <br />(para acessar as novas f&#xF3;rmulas desses reposit&#xF3;rios com Ritchie)</td>
    </tr>
  </tbody>
</table>



| Flags | Operation |
| :--- | :--- |
| rit --help | Ajuda com os comandos do Ritchie |
| rit --version | Retorna a versão do Ritchie usada no computador |

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

