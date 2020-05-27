# Stdin

## Definition 

{% hint style="info" %}
The second way to use Ritchie is through **stdin** \(standard input\), which means to inform the input parameters in a more traditional way, typing the values directly on the command line that will be executed.
{% endhint %}

With **stdin**, the input parameters need to be informed in a JSON format, following different patterns according to the operating system used :

### Linux & Mac

**`echo`** `"{\"key\":\"value\"}"`**`|`**`RIT (GROUP) VERB NOUN` **`--stdin`**

###  Windows \(with **PowerShell**\)

{% hint style="danger" %}
**STDIN** doesn't work with the **Windows** **Command Prompt.**
{% endhint %}

**`echo`**`'{"key":"value"}'`**`|`**`RIT (GROUP) VERB NOUN` **`--stdin`**

## Examples with STDIN

{% page-ref page="core-commands.md" %}

{% page-ref page="formulas.md" %}



