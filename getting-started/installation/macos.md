# MacOS

## How does it work? 

To install the **latest version of Ritchie** for MacOS, you just have to execute the command below on your terminal according to the version you want to work with.

However, it is important to keep in mind **there are some requirements** before starting the installation on Windows.

### Requirements

If you wanna use efficiently Ritchie on MacOs, our recommendation is to have the following elements configured:

* the **make** command \([Using "make" on macOS](https://stackoverflow.com/questions/1469994/using-make-on-os-x)\)
* **md5sum** tools

{% hint style="warning" %}
Install **md5sum** with _**Homebrew**_ : `brew install md5sha1sum`

Install **md5sum** with _**MacPorts**_ : `sudo port install md5sha1sum`
{% endhint %}

### Installing Team Version

The command used to install Ritchie Team at your terminal is: 

```bash
curl -fsSL https://commons-repo.ritchiecli.io/install_legacy.sh | bash
```

### Installing Single Version

The command used to install Ritchie Single at your terminal is: 

```text
curl -fsSL https://commons-repo.ritchiecli.io/install_single_legacy.sh | bash
```

{% hint style="info" %}
If you prefer, you also can follow with[ **manual installation**.](manual-installation.md)
{% endhint %}

