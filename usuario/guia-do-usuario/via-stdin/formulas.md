# Fórmulas

Seguem alguns exemplos de JSON usados para executar **fórmulas** do Ritchie através do **stdin**. 

{% hint style="danger" %}
O JSON é construído de acordo com o _config.json_ usado na implementação da fórmula.

Para o comando de uma fórmula funcionar através do **stdin**, é preciso que essa fórmula funcione informando os _inputs_ \(parâmetros de entrada\) **exclusivamente através do arquivo config.json.**   
  
Se, por exemplo, o código da fórmula pedir dados via prompt, não será possível usar somente o stdin para a fórmula ser executada com sucesso.
{% endhint %}

{% hint style="warning" %}
Será necessário alterar os valores das **variáveis** nos JSON dos exemplos abaixo, para realizaras operações desejadas.
{% endhint %}

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
**Premissa** : Ter as credenciais do GITHUB e da AWS definidas na sessão.
{% endhint %}

Linux / Mac

```text
echo "{\"repository\":\"https://github.com/group/project\",\"terraform_path\":\"src\",\"environment\":\"qa\"}" | rit aws apply terraform --stdin
```





