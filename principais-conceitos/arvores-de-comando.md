# Árvores de comando

{% hint style="info" %}
Para entender a estrutura do produto em si, é importante destacar que **os comandos usados no Ritchie são agrupados conforme uma árvore**. 
{% endhint %}

No caso do Ritchie, foi seguido o padrão do **Cobra** \(uma biblioteca da linguagem Golang\) usando a seguinte lógica de construção de comandos **core** :

                                                 **RIT + VERBO + SUBSTANTIVO**

E, para permitir mais opções e liberdade aos usuários, também foi permitido seguir o padrão abaixo na construção de comandos das fórmulas :

                                        **RIT + GRUPO + VERBO + SUBSTANTIVO**

O aplicativo chamando Ritchie, usamos o nome **rit** para iniciar nossa árvore de comandos.

![](../.gitbook/assets/arvore-rit.png)

O comando rit é consequentemente nosso comando pai, ou raíz. Ele não é executável \(significa que ele não vai iniciar nenhuma operação se você usa ele sozinho no terminal\). É necessário usar sub-comandos \(que são comandos filhos, ou ramos, do comando rit\) executáveis para conseguir iniciar algum processo.

Os comandos executáveis no Ritchie são os comandos localizados no último nível da árvore.  
  
****Por exemplo, na imagem acima : 

* O comando **rit set context** é executável, pois está no último nível da árvore.
* O comando **rit kafka create** não é executável pois ele tem um sub-comando **topic** executável, no último nível da árvore.

Esse conceito de árvore de comandos é o núcleo da estrutura do Ritchie. Todos os comandos e sub-comandos são mapeados dentro de um json que é atualizado ou criado quando você baixar ou atualizar o CLI no seu computador.

{% page-ref page="estrutura-do-cli.md" %}

