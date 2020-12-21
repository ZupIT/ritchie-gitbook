# Upgrade CLI

{% hint style="info" %}
When a new Ritchie CLI version is released, a warning will appear when executing one of the following commands:

- **`rit`**_\(helper\)  
-_ **`rit -v`** _\(version\)_
{% endhint %}

To upgrade the Ritchie CLI version when this warning appears, run the following command: 

```text
rit upgrade
```

#### Example of the command output for the 2.6.0 version

```text
➜ rit upgrade

Rit upgraded with success
Release 2.6.0 description:
* Added multiselect input for formulas
* User is notified when adding the same repo and version
* Release notes are displayed on every upgrade
* Rit add repo will only add valid repos
* Context commands substituted by env commands
* Deprecated stdin
```

This output is based on the description of the release tag on the [**ritchie-cli releases page on Github**](https://github.com/ZupIT/ritchie-cli/releases).

