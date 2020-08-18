---
description: Você encontrará nessa seção como executar o comando Hello World
---

# Executando a fórmula "hello-world"

## Como executar fórmulas?

Tem duas maneiras de executar fórmulas com Ritchie:

* Localmente
* com Docker

### Localmente

{% hint style="danger" %}
Para executar uma fórmula localmente, é necessário ter a linguagem de programação que foi usada para desenvolver a fórmula instalada no computador.

**Exemplo**: _uma fórmula desenvolvida em **Java** precisará ter **Java instalado** na máquina para ser executada localmente._
{% endhint %}

### Docker

{% hint style="danger" %}
Todas as fórmulas podem ser executadas independentemente da linguagem usada a condição que  o **`DOCKER`** esteja instalado e iniciado.
{% endhint %}

Vamos seguir o exemplo abaixo e observar todas as maneiras de executar comandos no Ritchie.

## Hello World

Depois de finalizar os passos anteriores -  [**instalação**](installation/) e [**inicialização**](initialization.md) -,  você poderá executar a [**fórmula hello world**](https://github.com/ZupIT/ritchie-formulas/tree/master/demo/hello-world) para testar o Ritchie.

{% hint style="warning" %}
Esse comando foi disponibilizado na [**release 2.0.1**](https://github.com/ZupIT/ritchie-formulas/releases) do repositório[ **ritchie-formulas**](https://github.com/ZupIT/ritchie-formulas).   
  
É possível verificar qual versão do repositório está sendo usada executando o comando **`rit list repo`**.
{% endhint %}

Execute os comandos abaixo:

### Usando Prompt

{% hint style="warning" %}
Como **essa fórmula  foi desenvolvido usando Golang**, é preciso ter **Golang** instalado para conseguir executar ele **localmente**.
{% endhint %}

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
Nesse caso, não é necessário ter **Golang** instalado.
{% endhint %}

### Usando Stdin

É também possível executar comando usando a flag **--stdin** \(Standard Input\). Dessa maneira, os parâmetros de entrada podem ser informados diretamente na linha de comando inicial:

```
echo '{"input_text":"Dennis", "input_bool":"false", "input_list":"everything", "input_password":"Ritchie"}' | rit demo hello-world --stdin
```

{% hint style="warning" %}
Ritchie usa o formato **JSON** para executar comandos STDIN.
{% endhint %}

### Usando Stdin & Docker

Quando são usadas as 2 flags **--stdin** e **--docker**, é possível executar o comando remotamente informando os parâmetros de entrada na linha de comando inicial, sem necessidade de ação humana:

```text
echo '{"input_text":"Dennis", "input_bool":"false", "input_list":"everything", "input_password":"Ritchie"}' | rit demo hello-world --stdin --docker
```



{% hint style="success" %}
Dê uma olhada nas fórmulas da comunidade \(ex: [**ritchie-formulas**](https://github.com/ZupIT/ritchie-formulas)\). 

A maioria das fórmulas tem um arquivo [**README**](https://github.com/ZupIT/ritchie-formulas/tree/master/demo/hello-world) explicando como executar a fórmula e para que ela serve.
{% endhint %}

## Próximos passos

Nessa seção, você viu como executar uma fórmula no Ritchie. 

👉Confira agora as fórmulas que você tem acesso usando o comando:

```text
rit --help
```

👉E entenda como [criar suas fórmulas](../tutoriais/como-criar-formulas.md).

