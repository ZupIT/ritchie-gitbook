---
description: 'In this section, you will find how to publish formulas on Ritchie.'
---

# How to publish formulas

## How to publish?

There is a formula on Ritchie that allows the user to create / update a formula repository on Github / Gitlab.

### Premisses

{% hint style="warning" %}
To publish your formula, make sure to set Github / Gitlab credentials using the**`rit set credential`** command.
{% endhint %}

## Publish your repository

A formula has been created on the community repository to perform:

* The initialization of a local repository on Git \(if necessary\),
* The creation of the repository on Github / Gitlab,
* The release generation of a new version of the repository,
* The addition of the repository to Ritchie local repositories \(**`rit add repo`**command\). 

{% hint style="info" %}
Moreover, if the repository already exists, it will commit the new code and generate the new release version informed, before updating Ritchie repositories \(**`rit update repo`**command\).
{% endhint %}

```text
rit publish repo
```

The user has to inform 5 different kinds of inputs:

1. The **`provider`** \(Github or Gitlab\)
2. The **`repository's privacy`**
3. The **`repository's name`**
4. The **`local repository path`** you wish to publish
5. The **`release version`** to generate

![rit publish repo command](../.gitbook/assets/rit-publish-repo.gif)

{% hint style="warning" %}
As shown on the example above, you can check if the publication has been successful by using the **`rit list repo`** command and see if the published repository appears.
{% endhint %}

## Publish manually

To publish a formula manually, you need to push it on a **Github / Gitlab** repository, following these steps:

1. Have an exclusive repository for formulas on Github / Gitlab.

   _It can be created from the a local repository, or based on a cloned repository._  

2. Add your formulas to the repository  _Using the**`rit create formula`** command, or **copy / paste** folders**.**_ 
3. Commit and push the new code to the Github / Gitlab repository. 
4. Generate a new release of the formulas repository.

## Next steps 

On this section, you saw how to publish a formula on Ritchie. To keep configuring the formula: 

👉 Check out [**how to share formulas**](how-to-share-formulas.md)**.** 

