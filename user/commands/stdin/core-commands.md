# Core Commands

Here are the JSON used to run Ritchie's core commands through stdin.

{% hint style="warning" %}
It will be necessary to adapt the variable values of each JSON to perform the desired operations as expected.
{% endhint %}

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
**stdin** hasn't been implemented yet for the **`rit login`**command.
{% endhint %}

