# Via stdin

## Definição 

{% hint style="info" %}
A segunda maneira de usar o Ritchie é usando **stdin** \(standard input\), o que significa **** informar os _inputs_ \(parâmetros de entrada\) de forma tradicional, digitando os valores diretamente na linha de comando que vai ser executada.
{% endhint %}

Com **stdin**, os parâmetros de entrada precisam ser informados no formato JSON, seguindo a seguinte nomenclatura de acordo com o sistema operacional usado :

### Linux & Mac

**`echo`** `"{\"key\":\"value\"}"`**`|`**`RIT (GROUPO) VERBO SUBSTANTIVO` **`--stdin`**

###  Windows \(usando **PowerShell**\)

{% hint style="danger" %}
**STDIN** não funciona com o **Prompt de comandos** nativo do Windows.
{% endhint %}

**`echo`**`'{"key":"value"}'`**`|`**`RIT (GROUPO) VERBO SUBSTANTIVO` **`--stdin`**



### Exemplos de uso do STDIN

{% page-ref page="comandos-core.md" %}

{% page-ref page="formulas.md" %}



