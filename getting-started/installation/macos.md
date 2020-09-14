---
description: 'In this section, you will find how to install Ritchie for MacOs.'
---

# MacOS

To install the **latest version of Ritchie** for MacOS, you just have to run the command below on your terminal. However, it is important to keep in mind **there are some requirements** before starting the installation on MacOS.

## Step 1: Requirements

To use Ritchie on MacOs, we recommend to install the following elements:

* The **make** command \([Using "make" on macOS](https://stackoverflow.com/questions/1469994/using-make-on-os-x)\)
* **md5sum** tools

{% hint style="warning" %}
To install **md5sum** with _**Homebrew**_ , use: `brew install md5sha1sum`

To install **md5sum** with _**MacPorts**_ , use: `sudo port install md5sha1sum`
{% endhint %}

## Step 2: Installing command

The command used to install Ritchie at your terminal is:

```text
curl -fsSL https://commons-repo.ritchiecli.io/install.sh | bash
```

{% hint style="info" %}
If you prefer, you also can follow with[ **manual installation**.](manual-installation.md)
{% endhint %}

## Step 3: Verify installation 

You can confirm if your installation went well by running this command: 

```text
rit --version
```

If everything's configured, the terminal will return Ritchie's current version.  

