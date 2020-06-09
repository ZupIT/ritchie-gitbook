# Testando fórmulas

{% hint style="info" %}
Uma vez a fórmula implementada, existem vários métodos de testar ela. 
{% endhint %}

### Através de uma IDE

Você pode executar o arquivo principal da sua fórmula \(ex : main.go\) configurando variáveis do ambiente para representar seus parâmetros de entrada. A vantagem de usar uma IDE é de ter a possibilidade de debugar o código.  
  
_Sugestões : VSCode, Eclipse, IntelliJ, Golang..._

### Através do Terminal

Na criação da nova fórmula, foi informado no arquivo Makefile da raíz do repositório o path onde está localizada a fórmula, dentro do repositório.

Neste arquivo existe um comando test-local que permite criar o binário de uma ou mais fórmulas e colocar ela\(s\) na pasta temporária do Ritchie \(.rit\) localizada na home da máquina do usuário.

_Observação : Esse comando test-local usa 2 outros arquivos na raíz do repositório : **copy-bin-configs.sh** e **unzip-bin-configs.sh** que permitem de fato extrair os **binários** e os **config.json** associados a cada fórmula que é testada._

#### **Existe 2 maneiras de usar esse comando do Makefile** : 

Para adicionar na pasta .rit somente os arquivos da fórmula que deseja testar :

```text
make test-local form={nome_formula} 
```

Para adicionar todas as fórmulas do repositório na pasta temporária .rit :

```text
make test-local
```

Após ter adicionado a fórmula no **.rit** através do _**Makefile**_ \(principal\), será possível executar o comando associado a essa fórmula pelo terminal \(o auto-completion não funcionará nesse caso\).

![Teste local da nova f&#xF3;rmula](https://lh3.googleusercontent.com/mdCy9EEHMClzyFaEQpmPukVSAm1ZjdkSywrafOMhNfbrZy1kEpOinkZBvnhfv9tfn0y-e4BLysKh6ZMLClnDI2CbfPfD5qMIlPQ5_KNvEfKm3hqgdXTKiAPXDqVXCgXR4s0tmWjy)

![Pasta .rit ap&#xF3;s uso do comando make test-local](https://lh6.googleusercontent.com/UlEmXyQVdvXksKE-llsWh5mv2Oe2VYwdTe4psQBp8-5_NfAd3loorzlYpRE8NsoEE-UBYcy68WdZSZEoedtuJ01zkBdEBxvdL7s6irgffMAZZV2k8N2Tu5xt30giG7-mzIVoh6pn)

{% hint style="success" %}
**Parabéns ! Você criou sua primeira fórmula usando o Ritchie !**
{% endhint %}

{% hint style="info" %}
**Sua fórmula pode ser útil para outras pessoas?**  
_****_  
****→ Compartilhe ela com a comunidade, abrindo uma PR no repositório [ritchie-formulas](https://github.com/ZupIT/ritchie-formulas).
{% endhint %}

