---
description: Passo a passo explicando como criar uma nova fórmula no Ritchie
---

# Criando fórmulas

## Introdução 

O processo de criação de fórmulas é feito por meio da execução do comando _**`rit create formula`,**_ que cria a estrutura necessária para você começar a desenvolver uma nova fórmula na sua máquina.  
****  
É importante ter em mente que, antes de criar uma fórmula, você tem de ter configurado o Ritchie corretamente na sua máquina, bem como realizado testes para se certificar de que está rodando comandos corretamente. 

## Passo 1: Executar a fórmula 

Quando executamos o comando no terminal, um input é pedido para o usuário, no caso, o **comando** que executará a nova fórmula. 

{% hint style="info" %}
Lembre-se que o ideal é que a nova fórmula siga o padrão **rit + group + verb + noun**.
{% endhint %}

![Exemplo do comando create new formula](https://lh5.googleusercontent.com/O9s2UpIovVyG4h2p1kuX8kLvASX_YS0mAKRSQWXxwoe2Tmr-R1r8xWSKH-nq2uCAfQSG4EcZC1tYPnICeh34coLM5ZsfIU38zTHDRwf6q3cqY_e1KWABAjX-hA_zfqOntFuA-WWX)

## Passo 2: Teste seu template 

## Passo 3: Direcionar para um repositório

Quando é executado o comando para criação de fórmula, você tem a opção de informar o caminho para um repositório de fórmulas já existente na máquina.

Caso você não tenha um repositório de fórmulas disponível, será criado um repositório de fórmulas automaticamente chamado **ritchie-formulas-local** na **HOME** da sua máquina.

{% hint style="info" %}
Se acontecer do Ritchie não informar nada e existir esse repositório local na sua máquina, a nova fórmula será adicionada lá e a sua estrutura será automaticamente atualizada. 
{% endhint %}

Segue um exemplo da estrutura do repositório local com uma fórmula \(dentro da pasta _group_\).

![Estrutura do reposit&#xF3;rio local](https://lh3.googleusercontent.com/Tz7C28jLzbXdqABAVo1BUWXr_uMkBcIxwsEXvze8OYVOU3Gs6mLoMhIF5EFYp6bq7bQjE8wvyuFxLWR5Qx2xBLSCnLorRc9kc6DWZVHQu09P_WV4BL4TkQ4SsWrCez0nEmqCSiD4)

## Passo 4: Organizar a pasta da fórmula 

{% hint style="info" %}
Vale reforçar que o comando `rit create formula` , por si só, já cria automaticamente uma pasta referente à fórmula no repositório, de acordo com o _input_ informado. 
{% endhint %}

A pasta de uma fórmula, por padrão, possui a seguinte estrutura:

![](https://lh4.googleusercontent.com/lu-BipM4Ym4qc3EeGXLNoEyvDknCZ1ZUtAvUxWra0v4uyyKi71gZiUAJzwi2n4UlwqPwdhKROps945TJ6g6i_kfi_TmlqC-nC-JOVl7T3Oy6Ks5Fnoy8Ok1lwVViRn36JAV-JAg0)



O conteúdo da pasta **SRC** é padronizado de acordo com a linguagem escolhida e é sempre composto dos seguintes elementos:

### O arquivo main

É o arquivo executável da fórmula, responsável por iniciar o código que será chamado pelo terminal. O **main** será criado de acordo com a linguagem utilizada para criar a fórmula, informando como _input_ no comando. Além disso, ele conterá um exemplo padrão de implementação.

### O arquivo Makefile \(da fórmula\)

O arquivo _**Makefile \(fórmula\)**_ é diferente do arquivo _**Makefile**_ do repositório. O _**Makefile**_ _**\(fórmula\)**_ permite gerar os executáveis da fórmula, enquanto o _**Makefile**_ do repositório permite tanto gerar os executáveis de todas as formulas, quanto testar as formulas localmente adicionando esses executáveis na [pasta .rit]().

### O arquivo config.json

Arquivo que contém 3 _**inputs**_ padrões como exemplo, que são extraídos e manipulados no arquivo **main** da fórmula.

### A pasta pkg

Pasta composta pelos demais arquivos do código que, junto com o arquivo **main,** permitirão a execução da fórmula. É gerada de acordo com a linguagem escolhida para criar a fórmula.

Se você criou uma fórmula pela primeira vez criando o repositório local, este repo e a pasta da fórmula seguirão a estrutura abaixo:

![](https://lh5.googleusercontent.com/6oPMzmvLxb9PGmC9a6U7KfLt4oCpEnFhOHXXOoGkgMgmaQi4kKHDo5epvU27HbWbBvM1mC1K2aruXfGPQrtWJMibeXmXmN19NbI7S81Djz11Axc0fCG2GtTNCAYivuI2iMMxMLZK)

## Passo 5: Implemente a fórmula 

Uma vez criada e organizada a fórmula no seu respectivo repositório e pasta, está na hora de implementá-la. 

Para isso, é necessário alterar 3 lugares para implementar a operação desejada:

* O _**config.json**_ da fórmula para configurar os inputs.
* O arquivo _**main**_
* Os arquivos da **pasta** **pkg**.

Caso tenha usado outra linguagem para criar sua fórmula, você talvez precise alterar mais arquivos.

{% hint style="warning" %}
Algumas orientações importantes: 

❗Não altere o nome das pastas raízes da fórmula \(group/verb/noun\) sem atualizar o **tree.json** e o **Makefile \(principal\)** com os paths adequados.

❗Lembre que o **tree.json** e o **Makefile \(principal\)** já são criados/alterados com a execução do comando `rit create formula`. Consequentemente, não precisará alterar-los para conseguir testar a nova fórmula, mesmo após ter alterados os arquivos comentados acima.

É possível que você tenha de realizar alguns ajustes nesses arquivos, se tiver necessidade. Por exemplo, se precisar alterar a mensagem _descriptíva_ ou o _helper_ do comando associado a sua fórmula, será necessário realizar essas modificações no **tree.json**.
{% endhint %}

