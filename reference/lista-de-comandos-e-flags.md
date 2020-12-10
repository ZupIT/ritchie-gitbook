---
description: 'Nesta seção, você encontrará uma lista com principais comandos do Ritchie.'
---

# Lista de comandos e flags

## Comandos

### Comandos de Configuração

| Comandos | Operação |
| :--- | :--- |
| rit init  | inicia o Ritchie antes de usar |
| rit upgrade | upgrade da última versão estável do Ritchie  |
| rit tutorial  | habilita ou desabilita o tutorial  |
| rit --version | retorna qual a versão atual instalada do Ritchie |

### Comandos de Repositórios 

| Comandos | Operação |
| :--- | :--- |
| rit add repo | adiciona um novo repositório \(para ter acesso as fórmulas desse repositório com Ritchie\) |
| rit list repo | lista todos os repositórios disponíveis  |
| rit update repo | atualiza todos os repositórios \(para acessar novas fórmulas desses repositórios com o Ritchie\) |
| set repo-priority | configura a prioridade do repositório  |
| rit delete repo | apaga um repositório  \(remove o acesso ao repositório de fórmulas com o Ritchie\)  |

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
        <p>cria uma nova f&#xF3;rmula do zero</p>
        <p>(como tamb&#xE9;m um novo reposit&#xF3;rio local, se necess&#xE1;rio)</p>
      </td>
    </tr>
    <tr>
      <td style="text-align:left">rit build formula</td>
      <td style="text-align:left">compila uma f&#xF3;rmula localmente para teste</td>
    </tr>
    <tr>
      <td style="text-align:left">rit build formula --watch</td>
      <td style="text-align:left">Compila uma f&#xF3;rmula para teste, monitorando atualiza&#xE7;&#xF5;es
        do c&#xF3;digo no tempo real</td>
    </tr>
  </tbody>
</table>

{% hint style="danger" %}
O comando rit build formula foi depreciado a partir da versão 2.5.0 do Ritchie. 
{% endhint %}

### Comandos de Autocomplete

| Comandos | Operação |
| :--- | :--- |
| rit completion zsh | adiciona o autocomplete via zsh |
| rit completion bash | adiciona o autocomplete via bash |
| rit completion fish | adiciona o autocomplete via fish |
| rit completion powershell | adiciona o autocomplete via powershell |

### Comandos de Contexto

| Comandos | Operação |
| :--- | :--- |
| rit set context | configura um novo contexto na sessão |
| rit show context | mostra o contexto usado na sessão atual |
| rit delete context | remove um contexto da sessão |

### Comandos de Credenciais

| Comandos | Operação |
| :--- | :--- |
| rit set credential | configura credenciais na sessão |
| rit list credential | lista todas os nomes de credenciais e os campos |
| rit delete credential | permite apagar suas credenciais  |

### Comandos de Workspaces <a id="workspace-commands"></a>

| Comandos | Operações |
| :--- | :--- |
| rit list workspace | lista todas as fórmulas do workspace  |
| rit delete workspace | remove uma fórmula específica do workspace |

## Flags

### Principais flags 

| Flags | Operações |
| :--- | :--- |
| --default | atribui os valores **default** configurados na fórmula |
| --docker | executa a fórmula usando **Docker** |
| --help | retorna a lista dos comandos executáveis pelo usuário |
| --local | executa a fórmula **localmente** |
| --verbose | executa a fórmula sem detalhes dos logs |

