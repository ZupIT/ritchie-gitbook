# Repositórios de fórmulas

{% hint style="info" %}
As fórmulas são armazenadas em **repositórios de fórmulas**.

Esses repositórios precisam ter uma estrutura particular. 
{% endhint %}

Cada repositório deve conter os seguintes elementos :

* as pastas das fórmulas.
* uma pasta tree
* um arquivo Makefile
* um arquivo copy-bin-configs.sh 
* um arquivo unzip-bin-configs.sh

![Reposit&#xF3;rio de f&#xF3;rmulas da comunidade](../../../.gitbook/assets/screenshot-2020-05-22-at-17.27.48.png)

Cada **pasta de fórmula** vai conter o código executável e os arquivos referentes a uma fórmula.

A pasta **tree** é composta de um arquivo _**tree.json**_ que vai conter a árvore dos comandos de todas as fórmulas do repositório. 

O arquivo _**Makefile**_ contem uma referência a todas as fórmulas do repositório, assim que um comando executável manipulando os arquivos **copy-bin-configs.sh** e **unzip-bin-configs.sh,** a fim de gerar os arquivos necessários para testar as fórmula\(s\) localmente na [pasta .rit](../../cli/pasta-.rit.md).

