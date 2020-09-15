---
description: >-
  Nesta seção, você verá como executar detalhes de como executar fórmulas no
  Ritchie.
---

# Como executar fórmulas

## Como executar?

Você tem **duas maneiras** de executar fórmulas usando o Ritchie:

1. Localmente
2. Usando o Docker

O **método de execução de fórmulas padrão** foi escolhido durante a etapa de inicialização com o comando **`rit init`**. Ele pode ser alterado executando o comando abaixo:

```text
rit set formula-runner
```

![Comando rit set formula-runner](../../.gitbook/assets/large-gif-1374x404-.gif)

### 1. Execução local

Para executar uma fórmula localmente, é necessário ter a linguagem de programação que foi usada para desenvolver a fórmula instalada no computador.

**Exemplo**: uma fórmula desenvolvida em **Java** precisará ter **Java instalado** na máquina para ser executada localmente.  


### 2. Execução via Docker

Todas as fórmulas podem ser executadas sem depender da linguagem usada a condição que  o **`DOCKER`** esteja instalado e iniciado.

{% hint style="info" %}
Vamos no exemplo a seguir da [**seção fórmula hello world** ](formula-hello-world.md)para ver como isso funciona na prática.
{% endhint %}



### 3. Local & Docker Flags

É possível forçar o Ritchie CLI a executar uma fórmula seguindo um método de execução específico, usando flags.

* A flag **`--local`** executará a fórmula localmente \(se o método de execução padrão é o Docker\). 
* A flag **`--docker`** executará a fórmula com Docker \(se o método de execução padrão é o local\). 

### 4. Containers com Ritchie

{% hint style="warning" %}
Todos os templates de formulas contém um arquivo **DockerFile** que cria um container com **Ritchie CLI** instalado.
{% endhint %}

## Próximos passos 

Nesta seção, você viu como rodar uma fórmula no Ritchie. Para continuar aprendendo mais:

👉 Vá para página [**Fórmula Hello World**](formula-hello-world.md) ****te descubra as diferentes maneiras de executar uma fórmula no Ritchie.

👉 Vá para página [**como criar fórmulas**](../como-criar-formulas.md) para entender o passo a passo para criar sua primeira automação usando o Ritchie.

