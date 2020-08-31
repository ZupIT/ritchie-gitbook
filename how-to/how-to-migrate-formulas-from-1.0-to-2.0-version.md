---
description: >-
  You will find here how you can migrate your formulas created on Ritchie 1.0
  version to 2.0 version.
---

# How to migrate formulas from 1.0 to 2.0 version?

### Context

If you use Ritchie 1.0 version and want to upgrade to the 2.0 one, **you have to update your formula's repository structure** to be compatible to the pattern used on the new version.

### How to migrate?

**Step 1**: Create  new formula repo from scratch using the **`rit create formula`** command.

* Adding the same formulas paths used on the older repository to the new one.

**Step 2:** Export your formulas implementations from the older repository to the new one.

* The structure still uses the same files: **`config.json`** , **`main.*`**, **`formula.*`**.
* Copy these files codes from the old structure to the new one, respecting the new layout.

**Step 3**: Publish the new formula repository on **github** or **gitlab** \(also, it can **public** or **private**\).

**Step 4**: Generate a release of the formula repository.

**Step 5**: Add the formula repository on Ritchie using the **`rit add repo`** command.

**Step 6**: Share your formula's repository with your team, colleagues or the community.

{% hint style="info" %}
If you have any question, feel free to contact our team at **ritchie@zup.com.br** or by opening an issue on the [**ritchie-formulas repository**](https://github.com/ZupIT/ritchie-formulas).
{% endhint %}

