---
description: >-
  Você encontrará nessa seção os conceitos dos principais termos e expressões
  usados na doc e/ou no Ritchie.
---

# Principais conceitos

## Fórmulas

As **fórmulas** são **automações**, ou seja, são códigos chamados através das linhas de comando para realizar alguma operação.

## **Fórmulas sob** demanda

A primeira vez que o usuário executa o comando associado a uma fórmula no terminal, é baixado o **arquivo** **executável dessa fórmula** de acordo com o sistema operacional instalado no computador dele.

É nesse momento também que é baixado o arquivo **config.json** com os parâmetros de entradas \(inputs\) da fórmula, necessários para o código implementado no binário / script ser executado.

Esses parâmetros de entrada serão informados pelo usuário :

* após ele digitar o comando no terminal \(se for via prompt\)
* antes de digitar o comando no terminal \(se for via stdin\)

Ou antes de executar a fórmula de fato.  
****

![](.gitbook/assets/fluxo-formulas%20%283%29.png)

### Exemplo de execução de uma fórmula \(via prompt\)

![](.gitbook/assets/rit-scaffold-generate-coffee-go.gif)

O **`rit scaffold generate coffee-go`** é um comando executável associado a uma fórmula na árvore do Ritchie.

Como foi a primeira vez que o comando foi executado, foi possível observar que o Ritchie baixou um config file e a fórmula em sequência.

Após baixar os arquivos, o Ritchie pediu algumas informações para o usuário: 

* name
* type of coffee
* delivery. 

Essas informações são os 3 parâmetros de entrada da fórmula.

Uma vez informados esses parâmetros, a fórmula foi executada com sucesso \(conforme o que os logs apresentaram\).

## Árvore de comando

{% hint style="info" %}
Para entender a estrutura do produto em si, é importante destacar que **os comandos usados no Ritchie são agrupados conforme uma árvore**. 
{% endhint %}

No caso do Ritchie, foi seguido o padrão do **Cobra** \(uma biblioteca da linguagem Golang\) usando a seguinte lógica de construção de comandos **core**:

                                                 **RIT + VERBO + SUBSTANTIVO**

E, para permitir mais opções e liberdade aos usuários, também foi permitido seguir o padrão abaixo na construção de comandos das fórmulas :

                                        **RIT + GRUPO + VERBO + SUBSTANTIVO**

O aplicativo chamando Ritchie, usamos o nome **rit** para iniciar nossa árvore de comandos.

![](.gitbook/assets/arvore-rit%20%281%29.png)

O comando rit é nosso comando pai, ou raíz. Ele não é executável \(significa que ele não vai iniciar nenhuma operação se você usa ele sozinho no terminal\). É necessário usar sub-comandos \(que são comandos filhos, ou ramos, do comando rit\) executáveis para conseguir iniciar algum processo.

Os comandos executáveis no Ritchie são os comandos localizados no último nível da árvore.  
  
****Por exemplo, na imagem acima temos: 

* O comando **rit set context** é executável, pois está no último nível da árvore.
* O comando **rit kafka create** não é executável pois ele tem um sub-comando **topic** executável, no último nível da árvore.

Esse conceito de árvore de comandos é o núcleo da estrutura do Ritchie. Todos os comandos e sub-comandos são mapeados dentro de um json que é atualizado ou criado quando você baixar ou atualizar o CLI no seu computador.

