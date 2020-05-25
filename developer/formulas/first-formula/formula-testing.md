# Formula testing

{% hint style="info" %}
Once the formula is implemented, there are several methods of testing it.
{% endhint %}

### Through an IDE 

You can run your formula's main file \(ex : main.go\) by setting environment variables to represent your input parameters. The advantage of using an IDE is that you can debug the code.

_Suggestions: VSCode, Eclipse, IntelliJ, Golang..._

### Through the Terminal

When creating the new formula, the path where the formula is located in the repository was informed in the Makefile of the root of the repository.

In this file there is a test-local command that allows you to create the binary of one or more formulas and place it \(s\) in the temporary Ritchie folder \(.rit\) located in the home of the user's machine.

_Note: This test-local command uses 2 other files at the root of the repository: **copy-bin-configs.sh** and **unzip-bin-configs.sh** which actually allow you to extract the executable files and **config.json** associated with each formula that is tested ._

#### There are 2 ways to use this Makefile command:

To add only the formula files you want to test in the .rit folder :

```text
make test-local form={nome_formula} 
```

To add all formulas from the repository to the temporary .rit folder :

```text
make test-local
```

After adding the formula in .rit through the Makefile \(main\), it will be possible to execute the command associated with that formula through the terminal \(auto-completion will not work in this case\).

![Teste local da nova f&#xF3;rmula](https://lh3.googleusercontent.com/mdCy9EEHMClzyFaEQpmPukVSAm1ZjdkSywrafOMhNfbrZy1kEpOinkZBvnhfv9tfn0y-e4BLysKh6ZMLClnDI2CbfPfD5qMIlPQ5_KNvEfKm3hqgdXTKiAPXDqVXCgXR4s0tmWjy)

![Pasta .rit ap&#xF3;s uso do comando make test-local](https://lh6.googleusercontent.com/UlEmXyQVdvXksKE-llsWh5mv2Oe2VYwdTe4psQBp8-5_NfAd3loorzlYpRE8NsoEE-UBYcy68WdZSZEoedtuJ01zkBdEBxvdL7s6irgffMAZZV2k8N2Tu5xt30giG7-mzIVoh6pn)

{% hint style="success" %}
**Congratulations ! You created your first formula using Ritchie!**
{% endhint %}

{% hint style="info" %}
**Can your formula be useful to other people?**

→ Share it with the community by opening a PR in the [ritchie-formulas](https://github.com/ZupIT/ritchie-formulas) repository.
{% endhint %}

