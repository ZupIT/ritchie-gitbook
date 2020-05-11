---
description: Passo a passo explicando como criar uma nova fórmula no Ritchie
---

# Primeira fórmula

## Premissa

![](https://lh5.googleusercontent.com/Exul-n1NHAUw6xO269CWlgaxc7Zmym92YGDxcSoapIqbviziEJFzjNYSNnC0Gupd6NtqRMoe-e3dBpYjI-z_iqyqpI8slSiu2rRy9xZw-IpF6x_jF5IA3dP-Qg9b-U19_l2nT4uz)

O comando _`rit create formula`_ cria a estrutura necessária para o usuário iniciar o desenvolvimento de uma nova fórmula na sua máquina.  
****  
Antes de entrar em detalhes no passo a passo para criação de fórmula, é recomendado ler a [documentação referente aos principais conceitos do Ritchie.](https://docs.ritchiecli.io/v/doc-portuguese/principais-conceitos)

## **Repositório de fórmulas**

Para poder usar uma fórmula no CLI, é necessário ela se encontrar num repositório de fórmulas. 

Esse repositório precisa ter uma estrutura particular, contendo os seguintes elementos :

| → uma pasta tree, contendo o arquivo tree.json do repositório. |
| :--- |


Esse arquivo _**tree.json**_ vai conter a árvore dos comandos de todas as fórmulas do repositório. 

O CLI juntará as árvores de todo os repositórios que o usuário tem acesso na hora de executar os comandos.

| → um arquivo Makefile, localizado na raíz do projeto. |
| :--- |


Esse arquivo _**Makefile**_ precisa conter uma referência a todas as fórmulas do repositório, pois ele que permite gerar os arquivos necessários para testar a\(s\) fórmula\(s\) localmente.

| → as pastas contendo as fórmulas. |
| :--- |


Cada uma dessas pastas vai conter o código executável e os arquivos referentes a uma fórmula.

## **Fórmulas**

Para as fórmulas serem executáveis, é preciso ter alguns elementos configurados :

| → O tree.json do repositório onde a fórmula é implementada. |
| :--- |


Para o CLI conhecer o comando executável da sua fórmula após juntar todas as árvores de comandos dos diversos repositórios.

| → O config.json na pasta da fórmula |
| :--- |


Esse arquivo corresponde aos parâmetros de entrada \(_inputs_\) da fórmula, para o CLI saber quais informações ele precisará pedir para o usuário quando ele executará o comando no terminal a fim de processar a fórmula corretamente.

| → O binário contendo o código da fórmula. |
| :--- |


Para o CLI baixar esse binário de acordo com o sistema operacional do computador do usuário e executar a fórmula através dos parâmetros de entrada que terão sido informados.

![](../.gitbook/assets/fluxo-formulas%20%282%29.png)

## Comando de criação

Precisamos garantir que todos os elementos apresentados nos passos anteriores sejam configurados corretamente na criação da fórmula, e é isso que o comando `rit create formula` oferece para nós.

![](https://lh3.googleusercontent.com/Y84yqDkDGHpMS-LKxep44fo6HDDDD8N7P1ZLzNfiOrZpF-yYvnRbL4PRdNc5EthU-eeaENwpKiQQ3PRiDs0KsZCQWVeMHim2lZDshPiAr-mHSgG0cb-NLZZzzEBYUbM9V1dQtkrJ)

Quando esse comando é executado no terminal, um input é pedido para o usuário, o **comando** que executará a nova fórmula \(idealmente seguindo o padrão **rit + group + verb + noun**\).

A partir desse comando, serão criados e configurados todos os arquivos e a arquitetura comentados anteriormente.

## **Criação do repositório de fórmulas**

A primeira vez que é criado uma fórmula localmente com o comando rit create formula, o código da fórmula avalia se já existe o repositório de formula, chamado **ritchie-formulas-local** na home da máquina do usuário.

→ Caso exista esse repositório, a nova fórmula será adicionada la.

→ Caso não exista, o repositório será criado antes de adicionar a nova fórmula.

Segue a estrutura do repositório com uma fórmula \(dentro da pasta _group_\).  
****

![](https://lh3.googleusercontent.com/Tz7C28jLzbXdqABAVo1BUWXr_uMkBcIxwsEXvze8OYVOU3Gs6mLoMhIF5EFYp6bq7bQjE8wvyuFxLWR5Qx2xBLSCnLorRc9kc6DWZVHQu09P_WV4BL4TkQ4SsWrCez0nEmqCSiD4)

Esse repositório vai sempre conter pelo menos a pasta tree, o makefile \(principal\), assim que a pasta da fórmula adicionada.

* O _tree.json_ da pasta tree será atualizado com a árvore do novo comando.
* O _makefile_ \(principal\) será atualizado com o caminho da pasta da nova fórmula

| **❗**Além disso, existirá 2 arquivos shell \(.sh\) necessário para realizar os testes. Voltaremos a falar sobre eles mais para frente. Na parte Teste da fórmula. |
| :--- |


## **Criação da pasta da fórmula**

O comando também cria uma pasta referente a fórmula no repositório, de acordo com o _input_ informado. Essa pasta terá a seguinte estrutura :  


![](https://lh4.googleusercontent.com/lu-BipM4Ym4qc3EeGXLNoEyvDknCZ1ZUtAvUxWra0v4uyyKi71gZiUAJzwi2n4UlwqPwdhKROps945TJ6g6i_kfi_TmlqC-nC-JOVl7T3Oy6Ks5Fnoy8Ok1lwVViRn36JAV-JAg0)



O conteúdo da pasta **SRC** é padronizado, e é sempre composto dos seguintes elementos :

| → O arquivo main.go |
| :--- |


Esse arquivo é o executável da fórmula. Ele que inicia o código que será chamado pelo terminal. Por padrão, ele será criado na linguagem Go \(mas nada impede usar uma outra linguagem\) e conterá um exemplo padrão de implementação.

| → O arquivo Makefile \(formula\) |
| :--- |


Esse arquivo é diferente do _**Makefile**_ do repositório. O _**Makefile**_ da fórmula permite gerar os binários da fórmula, enquanto o Makefile do repositório permite tanto gerar os binários de todas as formulas, quanto testar as formulas localmente.

| → O arquivo config.json |
| :--- |


Esse arquivo conterá 3 _**inputs**_ padrões como exemplo, para serem usados no arquivo main.go da fórmula.

| → A pasta PKG |
| :--- |


Essa pasta será composta dos demais arquivos do código que, junto com o arquivo main.go permitirão a execução da fórmula. Por padrão, eles também serão criados na linguagem Go \(mas nada impede usar uma outra linguagem\).

| **❗**Lembre-se de que você pode escrever sua fórmula usando qualquer linguagem que você esteja familiarizado \(bash, python, golang, etc.\). |
| :--- |


Se você criou uma fórmula pela primeira vez, o repositório e a pasta da fórmula deverão seguir a mesma estrutura que abaixo :

![](https://lh5.googleusercontent.com/6oPMzmvLxb9PGmC9a6U7KfLt4oCpEnFhOHXXOoGkgMgmaQi4kKHDo5epvU27HbWbBvM1mC1K2aruXfGPQrtWJMibeXmXmN19NbI7S81Djz11Axc0fCG2GtTNCAYivuI2iMMxMLZK)

## **Implementação da fórmula**

Com o repositório de fórmulas criado na Home com a nova fórmula, é preciso de fato desenvolver a sua lógica.

É necessário alterar 3 lugares :

* * O _**config.json**_ da fórmula para configurar os inputs.
* * O arquivo _**main.go**_
* * Os arquivos \(códigos\) da pasta PKG.

Caso foi usado uma outra linguagem, poderá ser necessário alterar mais arquivos.

<table>
  <thead>
    <tr>
      <th style="text-align:left">
        <p>&#x2757;N&#xE3;o altere o nome das pastas ra&#xED;zes da f&#xF3;rmula
          (group/verb/noun) sem atualizar o tree.json e o Makefile (principal) com
          os paths adequados.
          <br />
        </p>
        <p>&#x2757;Lembre que o tree.json e o Makefile (principal) j&#xE1; ter&#xE3;o
          sido alterados com a execu&#xE7;&#xE3;o do comando rit create formula.
          Consequentemente, n&#xE3;o precisar&#xE1; alterar-los para conseguir testar
          a nova f&#xF3;rmula, mesmo ap&#xF3;s ter alterados os arquivos comentados
          acima.</p>
      </th>
    </tr>
  </thead>
  <tbody></tbody>
</table>_Obs : Portanto, é possível realizar alguns ajustes nesses arquivos se tiver necessidade.   
  
****Por exemplo : Se precisar alterar a mensagem descriptiva ou o helper do comando associado a sua fórmula, será necessário realizar essas modificações no **tree.json**._

## **Teste da fórmula**

| Note: O Ritchie precisa estar instalado no computador para poder testar as novas fórmulas pelo terminal. |
| :--- |


Uma vez que a fórmula terá sido implementada, existem vários métodos de testar ela. 

Vamos apresentar 2 deles aqui.

| → Através de uma IDE \(se estiver usando uma\). |
| :--- |


Você pode executar o arquivo principal da sua fórmula \(ex : main.go\) configurando variáveis do ambiente para representar seus parâmetros de entrada. A vantagem de usar uma IDE é de ter a possibilidade de debugar o código.  
  
_Obs : Pode se usar Goland para Go, IntelliJ ou Eclipse para Java ou Kotlin por exemplo_

| → Através do terminal |
| :--- |


Na criação da nova fórmula, foi informado no arquivo Makefile da raíz do repositório o path onde está localizada a fórmula, dentro do repositório.

Neste arquivo existe um comando test-local que permite criar o binário de uma ou mais fórmulas e colocar ela\(s\) na pasta temporária do Ritchie \(.rit\) localizada na home da máquina do usuário.

_Observação : Esse comando test-local usa 2 outros arquivos na raíz do repositório : c**opy-bin-configs.sh** e **unzip-bin-configs.sh** que permitem de fato extrair os **binários** e os **config.json** associados a cada fórmula que é testada._

Existe 2 maneiras de usar esse comando do Makefile : 

| `$ make test-local form={nome_formula}`  |
| :--- |


Para adicionar na pasta temporária .rit a fórmula que deseja testar em particular.

| `$ make test-local` |
| :--- |


Para adicionar todas as fórmulas do repositório na pasta temporária .rit

Após ter adicionado a fórmula no **.rit** através do _**Makefile**_ \(principal\), será possível executar o comando associado a essa fórmula pelo terminal \(o auto-completion não funcionará nesse caso\).

![Teste local da nova f&#xF3;rmula](https://lh3.googleusercontent.com/mdCy9EEHMClzyFaEQpmPukVSAm1ZjdkSywrafOMhNfbrZy1kEpOinkZBvnhfv9tfn0y-e4BLysKh6ZMLClnDI2CbfPfD5qMIlPQ5_KNvEfKm3hqgdXTKiAPXDqVXCgXR4s0tmWjy)

![Pasta .rit ap&#xF3;s uso do comando make test-local](https://lh6.googleusercontent.com/UlEmXyQVdvXksKE-llsWh5mv2Oe2VYwdTe4psQBp8-5_NfAd3loorzlYpRE8NsoEE-UBYcy68WdZSZEoedtuJ01zkBdEBxvdL7s6irgffMAZZV2k8N2Tu5xt30giG7-mzIVoh6pn)

| **✅ Parabéns, você criou sua primeira fórmula usando o Ritchie !** |
| :--- |


**Sua fórmula pode ser útil para outras pessoas?**  
_****_  
****→ Compartilhe ela com a comunidade, abrindo uma pull request no repositório [ritchie-formulas](https://github.com/ZupIT/ritchie-formulas).

