# Formulas

Here are some examples of JSON used to run Ritchie **formulas** through **stdin**.

{% hint style="danger" %}
The JSON is built according to the config.json used to implement the formula.

For the formula's command to work through **stdin**, it is necessary that this formula works informing **exclusively** the input parameters through the config.json file.

If, for example, the formula's code asks for data via prompt, it will not be possible to use only stdin for the formula to run successfully.
{% endhint %}

{% hint style="warning" %}
It will be necessary to adapt the variable values of each JSON to perform the desired operations as expected.
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
**Premise**: Have the GITHUB and AWS credentials configured inside the session.
{% endhint %}

Linux / Mac

```text
echo "{\"repository\":\"https://github.com/group/project\",\"terraform_path\":\"src\",\"environment\":\"qa\"}" | rit aws apply terraform --stdin
```



