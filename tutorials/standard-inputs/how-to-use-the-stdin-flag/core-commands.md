---
description: >-
  In this section, you will find more details about commands that can be used
  though stidn.
---

# Core Commands

## Core commands with STDIN

Here are the JSON used to run Ritchie's core commands through **stdin**.

{% hint style="warning" %}
You will have to adapt the variable values of each JSON to perform the desired operations as expected.
{% endhint %}

### General commands

rit init

```text
echo '{"addCommons":true, "sendMetrics":true, "runType":"local"}' | rit init --stdin
```

rit tutorial

```text
echo '{"tutorial":"enabled"}' | rit tutorial --stdin
```

### Repo commands 

rit add repo

```text
echo '{"provider":"Github", "name":"repoName", "version":"2.2.0", "url":"https://github.com/ZupIT/ritchie-formulas", "token": null, "priority":1}' | rit add repo --stdin
```

rit update repo

```text
echo '{"name":"repoName", "version":"2.2.0"}' | rit update repo --stdin
```

rit delete repo

```text
echo '{"name":"repoName"}' | rit delete repo --stdin
```

### Formula commands 

rit create formula

```text
echo '{"formulaCmd":"rit demo create formula", "lang":"shell", "workspacePath":"/users/dennis/home/ritchie-formulas", "formulaPath":"/demo/create/formula"}' | rit create formula --stdin
```

rit build formula 

{% hint style="danger" %}
Not supported yet
{% endhint %}

### Context commands

rit set context

```text
echo '{"context":"contextName"}' | rit set context --stdin
```

rit delete context

```text
echo '{"context":"contextName"}' | rit delete context --stdin
```

rit set credential

```text
echo '{"service":"provider", "type":"type", "credential": {"username":"credentialUsername","token": "credentialToken"}}' | rit set credential --stdin
```

## Core commands without STDIN

Some core commands don't need the stdin flag to be executed as they don't have any input parameter to inform:

* **`rit upgrade`**
* **`rit --version`**
* **`rit completion`**
* **`rit list repo`**
* **`rit list credential`**

