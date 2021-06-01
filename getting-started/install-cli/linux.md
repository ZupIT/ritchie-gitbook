---
description: 'In this section, you will find how to install Ritchie for Linux.'
---

# Linux

## Step 1: Requirements

If you want to efficiently use Ritchie on Linux with version **`2.0.5 and earlier`**, we recommend to install the following element configured:

* The **make** command

Once you have it, just run the command below at your terminal. 

## Step 2: Installing command

Copy and paste the command below to run on your terminal: 

```text
curl -fsSL https://commons-repo.ritchiecli.io/install.sh | bash
```

{% hint style="info" %}
If you prefer, you also can follow with the[ **manual installation**.](manual-installation.md)
{% endhint %}

### Packages

To download a specific package or version, you can use the **URLs** below on your navigator,  substituting the **`{VERSION}`** field according to the [project repository tags](https://github.com/ZupIT/ritchie-cli/tags):

**Red Hat Package Manager**

```text
https://commons-repo.ritchiecli.io/{VERSION}/installer/ritchie.rpm
```

**Debian**

```text
https://commons-repo.ritchiecli.io/{VERSION}/installer/ritchie.deb
```

**Arch Linux**

The **`tar.gz`** package is available on this [Arch Linux user repository](https://github.com/avelino/ritchie-cli-archpack) page \([repository reference](https://github.com/avelino/ritchie-cli-archpack)\).

## Step 3: Verify installation 

You can confirm if your installation went well by running this command: 

```text
rit --version
```

If everything's configured, the terminal will return Ritchie's current version.  

