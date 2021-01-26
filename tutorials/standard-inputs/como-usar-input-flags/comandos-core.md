---
description: >-
  Nesta seção, você encontrará mais detalhes sobre comandos que podem ser usados
  via input flags.
---

# Comandos Core

## Core Commands com input flags

{% hint style="info" %}
Estas flags estão disponíveis a partir da versão 2.8 do Ritchie.
{% endhint %}

### Flags disponíveis

### Comandos de Credenciais

rit set credential 

```text
rit set credential --provider=github --fields=username,token --values=Dennis,123456
```

rit delete credential

```text
rit delete credential --provider=github
```

### Comandos de Ambiente

rit set env

```text
rit set env --env=prod
```

rit delete env

```text
rit delete env --env=prod
```

### Comandos de Repo

rit add repo 

```text
rit add repo --name=Zup --provider=Github --repoUrl=https://github.com/ZupIT/ritchie-formulas-zup --tag=2.8.9 --token=1324efg
```

