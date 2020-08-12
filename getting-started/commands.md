---
description: Você encontrará nessa seção como executar o comando Hello World
---

# Executando a fórmula "hello-world"

## Como executar fórmulas?

Fórmulas são executadas **`LOCALMENTE` por padrão**, o que significa que você precisará ter instalado as dependências associadas as linguagens de programação que usará para desenvolver um fórmula. 

{% hint style="danger" %}
Para **executar localmente** uma fórmula desenvolvida em **Java**, você precisará ter **Java instalado** na sua máquina.
{% endhint %}

Contudo, todas as fórmulas podem ser executadas independentemente da linguagem usada a condição que você tiver o **`DOCKER`** instalado.

Vamos seguir o exemplo abaixo e observar todas as maneiras de executar comandos no Ritchie.

## Hello World

Depois de finalizar os passos anteriores -  [**instalação**](installation/) e [**inicialização**](initialization.md) -,  você poderá executar a [**fórmula hello world**](https://github.com/ZupIT/ritchie-formulas/tree/master/demo/hello-world) para testar o Ritchie.

{% hint style="warning" %}
Esse comando foi disponibilizado na [**release 2.0.1**](https://github.com/ZupIT/ritchie-formulas/releases) do repositório[ **ritchie-formulas**](https://github.com/ZupIT/ritchie-formulas).   
  
É possível verificar qual versão do repositório da comunidade está sendo usado executando o comando **`rit list repo`**.
{% endhint %}

Execute os comandos abaixo:

### Usando Prompt

```text
rit demo hello-world
```

Selecione uma opção para cada parâmetro de entrada e veja a mágica acontecer:

![rit demo hello-world](../.gitbook/assets/large-gif-1054x366-%20%281%29.gif)

Essa é a execução padrão de linhas de comando no Ritchie, executando fórmulas localmente através de **prompt** \(interagindo com o CLI no terminal\) para informar os parâmetros de entrada.

### Usando Docker

É possível executar o mesmo comando usando a flag **--docker** para executar a fórmula remotamente \(em um container\), continuando informando os parâmetros de entrada usando **prompt**:

```text
rit demo hello-world --docker
```

{% hint style="warning" %}
**Docker** precisa estar instalado e iniciado para conseguir executar comandos usando essa flag.
{% endhint %}

### Usando Stdin

É também possível executar comando usando a flag **--stdin** \(Standard Input\). Dessa maneira, os parâmetros de entrada podem ser informados diretamente na linha de comando inicial:

```
echo '{"input_text":"Dennis", "input_bool":"false", "input_list":"false", "input_password":"Ritchie"}' | rit demo hello-world --stdin
```

{% hint style="warning" %}
Ritchie usa o formato **JSON** para executar comandos STDIN.
{% endhint %}

### Usando Stdin & Docker

Quando são usadas as 2 flags **--stdin** e **--docker**, é possível executar o comando remotamente informando os parâmetros de entrada na linha de comando inicial, sem necessidade de ação humana:

```text
echo '{"input_text":"Dennis", "input_bool":"false", "input_list":"false", "input_password":"Ritchie"}' | rit demo hello-world --stdin --docker
```

{% hint style="success" %}
Dê uma olhada nas fórmulas da comunidade \(ex: [**ritchie-formulas**](https://github.com/ZupIT/ritchie-formulas)\). 

A maioria das fórmulas tem um arquivo [**README**](https://github.com/ZupIT/ritchie-formulas/tree/master/demo/hello-world) explicando como executar a fórmula e para que ela serve.
{% endhint %}

