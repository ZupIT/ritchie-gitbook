# Implementação da fórmula

{% hint style="info" %}
O comando `rit create fórmula` cria um **template de fórmula** _**Hello World**_ que precisa ser alterado para executar a operação desejada.
{% endhint %}

É necessário alterar 3 lugares para implementar a operação desejada :

* O _**config.json**_ da fórmula para configurar os inputs.
* O arquivo _**main**_
* Os arquivos da **pasta** **pkg**.

Caso foi usado uma outra linguagem, poderá ser necessário alterar mais arquivos.

{% hint style="warning" %}
❗Não altere o nome das pastas raízes da fórmula \(group/verb/noun\) sem atualizar o **tree.json** e o **Makefile \(principal\)** com os paths adequados.

❗Lembre que o **tree.json** e o **Makefile \(principal\)** já são criados / alterados com a execução do comando `rit create formula`. Consequentemente, não precisará alterar-los para conseguir testar a nova fórmula, mesmo após ter alterados os arquivos comentados acima.
{% endhint %}

_Obs : Portanto, é possível realizar alguns ajustes nesses arquivos se tiver necessidade.   
  
****_**Por exemplo** : Se precisar alterar a mensagem _descriptíva_ ou o _helper_ do comando associado a sua fórmula, será necessário realizar essas modificações no **tree.json**.

{% page-ref page="teste-da-formula.md" %}

