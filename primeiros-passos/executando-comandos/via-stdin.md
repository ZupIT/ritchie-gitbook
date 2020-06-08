# Via stdin

## Estrutura dos comandos 

Quando usamos o **stdin**, os parâmetros de entrada precisam ser informados no formato JSON, seguindo a seguinte nomenclatura de acordo com o sistema operacional usado:

### Linux & MacOS

**`echo`** `"{\"key\":\"value\"}"`**`|`**`RIT (GROUPO) VERBO SUBSTANTIVO` **`--stdin`**

###  ****Windows \(usando **PowerShell**\)

{% hint style="danger" %}
**STDIN** não funciona com o **Prompt de comandos** nativo do Windows.
{% endhint %}

**`echo`**`'{"key":"value"}'`**`|`**`RIT (GROUPO) VERBO SUBSTANTIVO` **`--stdin`**

## Estrutura das fórmulas 

O JSON é construído de acordo com o _config.json_ usado na implementação da fórmula. Por isso que, para o comando de uma fórmula funcionar pelo **stdin**, é necessário que ela funcione informe os _inputs_ **exclusivamente através do arquivo config.json.**   
  
Se, por exemplo, o código da fórmula pedir dados via prompt, não será possível usar somente o stdin para a fórmula ser executada com sucesso.

{% hint style="warning" %}
Vale lembrar que será necessário alterar os valores das **variáveis** nos JSON dos exemplos abaixo, para realizaras operações desejadas.
{% endhint %}

Seguem alguns exemplos de JSON usados para executar **fórmulas** do Ritchie através do **stdin:** 

### Fórmulas 

### RIT SCAFFOLD GENERATE COFFEE-GO

Linux / Mac

```
echo "{\"name\":\"Dennis Ritchie\",\"coffee_type\":\"espresso\",\"delivery\":\"true\"}" | rit scaffold generate coffee-go --stdin
```

Windows \(PowerShell\)

```
echo '{"name":"Dennis Ritchie","coffee_type":"espresso","delivery":"true"}' | rit scaffold generate coffee-go --stdin
```

#### 

### RIT SCAFFOLD GENERATE SPRING-STARTER

Linux / Mac

```text
echo "{\"type\":\"maven-project\",\"language\":\"java\",\"boot_version\":\"2.2.5.BUILD-SNAPSHOT\",\"group_id\":\"br.com.zup\",\"artifact_id\":\"ritchie-project\",\"description\":\"ritchie\",\"packaging\":\"jar\",\"java_version\":\"11\",\"dependencies\":\"web\"}" | rit scaffold generate spring-starter --stdin
```

Windows \(PowerShell\)

```text
echo '{"type":"maven-project","language":"java","boot_version":"2.2.5.BUILD-SNAPSHOT","group_id":"br.com.zup","artifact_id":"ritchie-project","description":"ritchie","packaging":"jar","java_version":"11","dependencies":"web"}' | rit scaffold generate spring-starter --stdin
```



### RIT GITHUB FAST-MERGE

Linux / Mac

```text
echo "{\"branch\":\"qa\",\"push\":\"false\"}" | rit github fast-merge --stdin
```

Windows \(PowerShell\)

```text
echo '{"branch":"qa","push":\"false\"}' | rit github fast-merge --stdin
```



### RIT AWS APPLY TERRAFORM

{% hint style="warning" %}
**Premissa** : Ter as credenciais do GITHUB e da AWS definidas na sessão.
{% endhint %}

Linux / Mac

```text
echo "{\"repository\":\"https://github.com/group/project\",\"terraform_path\":\"src\",\"environment\":\"qa\"}" | rit aws apply terraform --stdin
```



## Comandos Core 

{% hint style="warning" %}
Vale lembrar que será necessário alterar os valores das **variáveis** nos JSON dos exemplos abaixo, para realizar as operações desejadas.
{% endhint %}

Seguem alguns exemplos de JSON usados para executar **fórmulas** do Ritchie através do **stdin:** 

### RIT ADD REPO

Linux / Mac

```text
echo "{\"treePath\":\"https://commons-repo.ritchiecli.io/tree/tree.json\",\"name\":\"repoName\",\"priority\":1}" | rit add repo --stdin
```

Windows \(PowerShell\)

```text
echo '{"treePath":"https://commons-repo.ritchiecli.io/tree/tree.json","name":"repoName","priority":1}' | rit add repo --stdin
```

### 

### RIT CLEAN REPO

Linux / Mac

```text
echo "{\"name\":\"repoName\"}" | rit clean repo --stdin
```

Windows \(PowerShell\)

```text
echo '{"name":"repoName"}' | rit clean repo --stdin
```

#### 

### RIT CREATE FORMULA

Linux / Mac

```text
echo "{\"formulaCmd\":\"rit formula test command\", \"lang\":\"Go\"}" | rit create formula --stdin
```

Windows \(PowerShell\)

```text
echo '{"formulaCmd":"rit formula test command", "lang":"Go"}' | rit create formula --stdin
```

#### 

### RIT CREATE USER \(TEAM\)

Linux / Mac

```text
echo "{\"organization\":\"teamName\", \"firstName\":\"Dennis\", \"lastName\":\"Ritchie\", \"email\":\"dennis.ritchie@team.com\", \"username\":\"Dennis Ritchie\", \"password\":\"123456\"}" | rit create user --stdin
```

Windows \(PowerShell\)

```text
echo '{"organization":"teamName", "firstName":"Dennis", "lastName":"Ritchie", "email":"dennis.ritchie@team.com", "username":"Dennis Ritchie", "password":"123456"}' | rit create user --stdin
```

#### 

### RIT DELETE REPO

Linux / Mac

```text
echo "{\"name\":\"repoName\"}" | rit delete repo --stdin
```

Windows \(PowerShell\)

```text
echo '{"name":"repoName"}' | rit delete repo --stdin
```



### RIT DELETE USER \(TEAM\)

Linux / Mac

```text
echo "{\"username\":\"username\"}" | rit delete user --stdin
```

Windows \(PowerShell\)

```text
echo '{"username":"username"}' | rit delete user --stdin
```

#### 

### RIT DELETE CONTEXT

Linux / Mac

```text
echo "{\"context\":\"contextName\"}" | rit delete context --stdin
```

Windows \(PowerShell\)

```text
echo '{"context":"contextName"}' | rit delete context --stdin
```

#### 

### RIT SET CREDENTIAL \(SINGLE\)

Linux / Mac

```text
echo "{\"service\":\"credentialService\",\"credential\": {\"username\":\"credentialUsername\",\"token\": \"credentialToken\"}}" | rit set credential --stdin
```

Windows \(PowerShell\)

```text
echo '{"service":"credentialService","credential": {"username":"credentialUsername","token": "credentialToken"}}' | rit set credential --stdin
```

#### 

### RIT SET CREDENTIAL \(TEAM\)

Linux / Mac

```text
echo "{\"username\":\"me\",\"service\":\"credentialService\",\"credential\": {\"username\":\"credentialUsername\",\"token\": \"credentialToken\"}}" | rit set credential --stdin
```

Windows \(PowerShell\)

```text
echo '{"username":"me","service":"credentialService","credential": {"username":"credentialUsername","token": "credentialToken"}}' | rit set credential --stdin
```

#### 

### RIT SET CONTEXT

Linux / Mac

```text
echo "{\"context\":\"contextName\"}" | rit set context --stdin
```

Windows \(PowerShell\)

```text
echo '{"context":"contextName"}' | rit set context --stdin
```

#### 

### RIT SET SERVER

Linux / Mac

```text
echo "{\"url\":\"serverUrl\"}" | rit set server --stdin
```

Windows \(PowerShell\)

```text
echo '{"url":"serverUrl"}' | rit set server --stdin
```



### RIT LOGIN \(TEAM\)

{% hint style="warning" %}
O **stdin** ainda não foi implementado no comando **`rit login`**
{% endhint %}





