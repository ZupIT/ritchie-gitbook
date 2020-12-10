---
description: 'In this section, you will find how to share formulas on Ritchie.'
---

# How to share formulas

## How to share?

Once a formula repository has been published, other users can add it locally from its **URL** to access its formulas.

**Example**: [**`https://github.com/ZupIT/ritchie-formulas`**](https://github.com/ZupIT/ritchie-formulas)\*\*\*\*

To add a new repository on Ritchie, it is necessary to run the command: 

```text
rit add repo
```

Once the repository has been added, Ritchie will use the selected release on the repository to access the available formulas.

![rit add repo command demonstration](../../.gitbook/assets/rit-add-repo-3.gif)

{% hint style="warning" %}
If the formula repository is **private**, the user will have to inform his Github / Gitlab token.
{% endhint %}

## How to see the repo latest version?

{% hint style="info" %}
This feature is available from Ritchie 2.2 version. 
{% endhint %}

On Ritchie, it is possible to check out new formula commands and if there is a new version of some repository you added locally.

To do so, just follow these steps:

1. Run the help command**`rit --help`**. The system will return a list with the group of available repositories. 

```text
(new version 2.12.1) commons repo commands:
  beagle      Beagle commands
  bitbucket   Manage bitbucket objects
  clean-swift Manage clean-swift objects
  docker      Manipulate Docker objects
  git         Manipulate Git objects
  github      Manipulate GitHub objects
  gitlab      Manipulate GitLab objects
  istio       Istio Service Mesh commands
  jupyter     Manage jupyter objects
  kafka       Kafka commands
  kubernetes  Manipulate kubernetes objects
  publish     Publish command
  scaffold    Manipulate scaffold objects
  xcode       Manage xcode objects
```

   2. If you prefer, run the **`rit list repo`** command, that returns informations about the imported repositories, like the latest version and the last available version.

### How to update?

To update the version of any repository, you just have to run the command below informing the repository and the version you wish to be updated.

```text
rit update repo
```

## Next steps 

On this section, you saw how to share a formula on Ritchie. To keep configuring the formula: 

👉 Check out how to [**manipulate credentials**](https://docs.ritchiecli.io/how-to/manipulate-credentials) with your formulas.

👉 Check out our [**list of commands**](../../reference/list-of-commands-and-flags.md) to see the available automations on our community repo. 

