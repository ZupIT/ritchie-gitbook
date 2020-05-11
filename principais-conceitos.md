# Principais Conceitos

{% hint style="info" %}
Vamos supor que você esteja familiarizado com os conceitos de CLI, DevOps, NoOps e automações.
{% endhint %}

## Sistemas Operacionais

{% hint style="info" %}
Ritchie é um CLI que funciona para **todos os sistemas operacionais**
{% endhint %}

![](https://gblobscdn.gitbook.com/assets%2F-M-QT0ly86uQ2URUFYGO%2F-M6ptPEhAXXh4CHIC1XB%2F-M6q3nXhcN2HCWbXKY6N%2FScreenshot%202020-05-08%20at%2017.55.00.png?alt=media&token=64970202-83e5-49a1-b453-8a3e80e47015)

## **Linguagens de programação**

{% hint style="info" %}
Ritchie foi desenvolvido usando a linguagem do Google : **Golang**
{% endhint %}

No entanto, as fórmulas podem ser escritas usando qualquer linguagem de programação.

![](.gitbook/assets/screenshot-2020-05-08-at-17.54.34.png)

## Tools

{% hint style="info" %}
Ritchie works with **any tool** you could use for automations.
{% endhint %}

![](.gitbook/assets/screenshot-2020-05-08-at-17.54.49%20%281%29.png)

## **Árvore de comandos**

{% hint style="info" %}
Primeiro, é importante conhecer esse conceito para de fato poder entender a estrutura do produto em si : Os comandos usados no Ritchie são agrupados conforme uma árvore. 
{% endhint %}

No caso do Ritchie, foi seguido o padrão do **Cobra** \(uma biblioteca da linguagem Golang\) usando a seguinte lógica de construção de comandos **core** :

                                                 **RIT + VERBO + SUBSTANTIVO**

E, para permitir mais opções e liberdade aos usuários, também foi permitido seguir o padrão abaixo na construção de comandos das fórmulas :

                                        **RIT + GRUPO + VERBO + SUBSTANTIVO**

O aplicativo chamando Ritchie, usamos o nome **rit** para iniciar nossa árvore de comandos.

![](.gitbook/assets/arvore-rit.png)

O comando rit é consequentemente nosso comando pai, ou raíz. Ele não é executável \(significa que ele não vai iniciar nenhuma operação se você usa ele sozinho no terminal\). É necessário usar sub-comandos \(que são comandos filhos, ou ramos, do comando rit\) executáveis para conseguir iniciar algum processo.

Os comandos executáveis no Ritchie são os comandos localizados no último nível da árvore.  
  
****Por exemplo, na imagem acima : 

* O comando **rit set context** é executável, pois está no último nível da árvore.
* O comando **rit kafka create** não é executável pois ele tem um sub-comando **topic** executável, no último nível da árvore.

Esse conceito de árvore de comandos é o núcleo da estrutura do Ritchie. Todos os comandos e sub-comandos são mapeados dentro de um json que é atualizado ou criado quando você baixar ou atualizar o CLI no seu computador.  
****

## **Repositórios**

Hoje, o Ritchie é composto por 3 repositórios no Github.

* O repositório **ritchie-cli** \(_open source_\) que contém os comandos core do CLI que tem prioridade sobre os comandos das demais operações. 
* O repositório **ritchie-formulas** \(_open source_\) que contém os comandos das fórmulas \(commons\) que são compartilhados com todos os usuários do Ritchie. 
* O repositório **ritchie-server** \(_open source_\) que contém as integrações com o Vault e o Keycloak necessários para o funcionamento da versão Team do CLI. 

Os repositórios organizacionais \(usados na versão **Team**\) devem seguir idealmente a seguinte nomenclatura : **ritchie-formulas-empresa** \(_private / open source_\) que contém os comandos específicos das fórmulas da empresa.  


{% hint style="warning" %}
Cada repositório de fórmulas vai ter a sua própria árvore de comando, num arquivo chamado tree.json
{% endhint %}

Quando um usuário vai baixar o Ritchie, ou efetuar o comando rit login para acessar o repositório de uma organização, o CLI realiza o merge dos tree.json dos repositórios de fórmulas aos quais ele tem acesso. 

![](.gitbook/assets/fluxo-cli.png)

A junção das árvores dos repositórios será a árvore de todos os comandos disponíveis via o CLI no computador do usuário.

Existe também um conceito de prioridade entre as árvores dos repositórios, para evitar comandos repetitivos após a junção na árvore de todos os comandos.

Segue a prioridade padrão definida no CLI entre os repositórios :

* Prioridade 0 : Core
* Prioridade 1 : Local
* Prioridade 2 : Outros repositórios 

Essa regra permite que cada usuário \(single\) / empresa \(team\) defina a prioridade entre os demais repositórios.

**Por exemplo, é possível um usuário escolher entre os 2 cenários abaixo :**

![](https://lh4.googleusercontent.com/XwM1MIenWGVB45DjC1A7-t_glfsYaznphkJMe7Bcxaa6RJpmy9pRBVW9hNaNw_LFJO5iEl4Zx9uNGAgpxLkPa6awswyeb_D7JktkN6M-Wntc0ad5e26LHE4I3PjoQe3Wnh29JpES)![](https://lh5.googleusercontent.com/h-6piqq1Yl-T7veYMe5rrlVWGi22P4RMs0Y3vcYn-sITSkW2w2SCXR9NjPq0jgcRwWpZnCTmIoO7jXJgc4hm9-3y1Q9SKyQwl75PtTSow4IIEoZ53Tx71FIkNIl6QsNHOrn_nUca)  
****

**No cenário 1,** seria dado prioridade aos comandos commons sobre os comandos do seu time.

**Já, no cenário 2,** seria dado prioridade aos comandos do repositório sobre os comandos commons. Isso permitiria por exemplo a um usuário ou time de usar um comando que está na árvore do repositório do **ritchie-formulas** para uma fórmulas no repositório dele, realizando uma operação diferente com o mesmo comando, já que teria prioridade.  
****

Por mais informações, confere a documentação sobre[ repositórios.](https://docs.ritchiecli.io/v/doc-portuguese/arquitetura-do-sistema/repositorios)

## **Fórmulas**

{% hint style="info" %}
Conforme explicado anteriormente, as **fórmulas nada mais são do que automações**. Ou seja, são códigos chamados através das linhas de comando para realizar alguma operação.
{% endhint %}

Após implementar uma fórmula, é gerado um binário ou script para cada sistema operacional \(Linux, MacOs ou Windows\). Esse binário / script contém o código necessário para executar a fórmula.

A primeira vez que o usuário executa o comando associado a uma fórmula no terminal, é baixado o binário / script dessa fórmula de acordo com o sistema operacional instalado no computador dele.

Além desse binário / script, é preciso baixar um arquivo json associado a fórmula, que contém os parâmetros de entradas \(inputs\) necessários para o código implementado no binário / script ser executado.

Esses parâmetros de entrada serão informados pelo usuário após ele digitar o comando no terminal, antes de executar a fórmula de fato.  
****

![](.gitbook/assets/fluxo-formulas.png)



![Segue um exemplo de um comando do Ritchie executado pelo terminal](https://lh3.googleusercontent.com/viskNlV4iXyN63RYhBdgu9I010Rz6nXaliyFKvC9vAHDyrQm2fEPUXzF5l6QclYEoQywEeXYZq3hPQFP_DqGQYJkk38E3nuam4rJQPSdl5zHU6HzP9Q2mEfg3TJeBuacn2geRgx7)

O **rit scaffold generate coffee** é um comando executável associado a uma fórmula na árvore do Ritchie.

Como foi a primeira vez que o comando foi executado, foi possível observar que o Ritchie baixo um config file e a fórmula em sequência.

Após baixar os arquivos, o Ritchie pediu algumas informações para o usuário : name, type of coffee & delivery. 

Essas informações são os parâmetros de entrada da fórmula.

Uma vez informados esses parâmetros, a fórmula foi executada com sucesso \(conforme o que os logs apresentaram\).

