# Composição das fórmulas

{% hint style="info" %}
Cada fórmula é composta de vários arquivos permitindo sua execução pelo CLI.
{% endhint %}

Para uma fórmula poder ser executada pelo terminal, é preciso ter :

* O arquivo tree.json do repositório onde se encontra a fórmula configurado
* Um arquivo config.json
* Um arquivo executável

O arquivo **tree.json** permite ao CLI de conhecer os comandos e sub-comandos associados a fórmula. É assim que ele identifica onde baixar os arquivos da fórmula na primeira execução \(sob demanda\).

O arquivo **config.json** contém os parâmetros de entrada \(_inputs_\) da fórmula. Ele que permite que o CLI saiba quais informações ele precisará pedir para o usuário quando ele executará o comando no terminal a fim de processar a fórmula corretamente.

O **arquivo executável** contém a implementação da fórmula. O CLI vai baixar esse arquivo de acordo com o sistema operacional do computador do usuário e executar essa fórmula enviando os parâmetros de entrada que terão sido informados.

