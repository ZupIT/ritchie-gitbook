# CLI

## Introdução 

O CLI, ou Command Line Interface, é o **recurso base** que permite o Ritchie funcionar.  Por padrão, o CLI manipula uma pasta à medida que executa os comandos sinalizados no terminal. 

Nesta pasta, são armazenados :

* Os arquivos **tree.json** dos repositórios de fórmulas acessíveis na máquina do usuário
* Os arquivos executáveis das **fórmulas** 
* Os arquivos **temporários** usados no Ritchie
* Os arquivos de _passphrase_ e _session_ para a versão **Single**

{% hint style="info" %}
Para conhecer mais sobre nosso repositório do CLI, acesse [**ritchie-cli**](https://github.com/ZupIT/ritchie-cli) no Github. 
{% endhint %}

## Pastas do CLI 

### Pasta Repo

A pasta **repo** contém todos os arquivos necessários para o CLI ter conhecimento dos comandos e das fórmulas que ele pode executar.

Ela é composta de outras pastas :

* uma pasta **cache** que vai conter os arquivos _tree.json_ dos repositório de fórmulas que o usuário tem acesso \(de acordo com a versão do Ritchie que estiver usando\).
* uma pasta **local** que vai conter o _tree.json_ do repositório onde o usuário está desenvolvendo e testando fórmulas localmente.

Além dessas pastas, também existe um arquivo _**repositories.json**_. Esse arquivo contém uma lista de _tree.json_ para o CLI identificar a quais árvores ele tem acesso, e quais são suas prioridades, a fim de evitar comandos duplicados, caso apareçam em mais de um repositório de fórmulas.

### Pasta Fórmulas

A pasta **fórmulas** contém todos os arquivos necessários para o CLI realizar a execução das fórmulas. 

Ela é composta de várias pastas, uma por fórmula, contendo o executável da fórmula de acordo com o sistema operacional usado, assim que o _config.json_ associado para identificar os parâmetros de entrada necessários para a fórmula ser executada corretamente.

Esses arquivos são baixados, e essas pastas são criadas quando o CLI executa o comando de uma fórmula pela [primeira vez](https://docs.ritchiecli.io/v/doc-portuguese/principais-conceitos#formulas) \(são buscados através do _repoUrl_ da fórmula informado no _tree.json_ associado\).

Quando o usuário testa uma fórmula que ele desenvolveu localmente, o arquivo _Makefile_ contido no repositório de fórmulas usado adicionará os executáveis da fórmula dentro dessa pasta, criando a mesma estrutura que seria criada caso a fórmula fosse baixada de um servidor.

### Pasta tmp

A pasta **tmp** é onde estão armazenados os arquivos temporários que podem ser criados ou manipulados durante a execução de algumas fórmulas ou comandos cores. Esses arquivos temporários podem ser templates, certificados, ou outros arquivos do tipo com uso único.

### Passphrase & Session

Os arquivos **passphrase** & **session** são arquivos criptografados usados na versão **Single** para conseguir definir dados que serão usados de forma repetitivas no Ritchie. Esses dados podem ser _credenciais_ de algumas ferramentas manipuladas nas fórmulas, ou até a definição do _contexto_ usado para realizar algumas automações.

