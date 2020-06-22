# Via Stdin

## Commands structure

With **stdin**, the input parameters need to be informed in a JSON format, following different patterns according to the operating system used :

### Linux & Mac

**`echo`** `"{\"key\":\"value\"}"`**`|`**`RIT (GROUP) VERB NOUN` **`--stdin`**

###  Windows \(with **PowerShell**\)

{% hint style="danger" %}
**STDIN** doesn't work with the **Windows** **Command Prompt.**
{% endhint %}

**`echo`**`'{"key":"value"}'`**`|`**`RIT (GROUP) VERB NOUN` **`--stdin`**

## Core Commands

{% hint style="warning" %}
It will be necessary to adapt the variable values of each JSON to perform the desired operations as expected.
{% endhint %}

Here are the JSON used to run Ritchie's core commands through **stdin**.

### RIT INIT

Linux / Mac

```text
echo "{\"organization\":\"team\", \"url\":\"https://ritchie-server.team.io\"}" | rit init --stdin
```

Windows \(PowerShell\)

```text
echo '{"organization":"team", "url":"https://ritchie-server.team.io"}' | rit init --stdin
```



### RIT LOGIN

Linux / Mac

```text
echo "{\"username\":\"dennis.ritchie\", \"password\":\"123456\"}" | rit login --stdin
```

Windows \(PowerShell\)

```text

```

### 

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
**stdin** hasn't been implemented yet for the **`rit login`**command.
{% endhint %}

## Formula Commands 

JSON is build according to the config.json used to implement the formula. Because of that, for the formula's commands to work through **stdin**, it is necessary that this formula works informing **exclusively the input parameters through the config.json file**.

If, for example, the formula's code asks for data via prompt, it will not be possible to use only stdin for the formula to run successfully. 

{% hint style="warning" %}
It will be necessary to adapt the variable values of each JSON to perform the desired operations as expected.
{% endhint %}

Here are some examples of JSON used to run Ritchie **formulas** through **stdin**.

### 

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
**Premise**: Have the GITHUB and AWS credentials configured inside the session.
{% endhint %}

Linux / Mac

```text
echo "{\"repository\":\"https://github.com/group/project\",\"terraform_path\":\"src\",\"environment\":\"qa\"}" | rit aws apply terraform --stdin
```

