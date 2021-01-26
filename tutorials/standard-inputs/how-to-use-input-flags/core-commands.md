---
description: >-
  In this section, you will find more details about commands that can be used
  though input flags.
---

# Core Commands

## Core Commands with input flags

{% hint style="info" %}
This flags are supported since Ritchie's 2.8 release.
{% endhint %}

### Available flags

### Credentials commands

rit set credential 

```text
rit set credential --provider=github --fields=username,token --values=Dennis,123456
```

rit delete credential

```text
rit delete credential --provider=github
```

### Environment commands

rit set env

```text
rit set env --env=prod
```

rit delete env

```text
rit delete env --env=prod
```

### Repo commands

rit add repo 

```text
rit add repo --name=Zup --provider=Github --repoUrl=https://github.com/ZupIT/ritchie-formulas-zup --tag=2.8.9 --token=1324efg
```

