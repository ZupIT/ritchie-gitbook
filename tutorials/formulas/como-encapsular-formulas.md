---
description: 'Nesta seção, você entenderá o que é e como encapsular fórmulas em Ritchie.'
---

# Como encapsular fórmulas

## O que é encapsulamento?

No Ritchie, é possível **executar fórmulas dentro de fórmulas**. Esse processo é o que chamamos de **Encapsulamento de Fórmula**. 

Essa função permite que você, por exemplo, realize operações em que é necessário rodar fórmulas consecutivas. 

A seguir, veja como você pode fazer esse processo de encapsulamento: 

## Como encapsular?

### 1. Premissa 

Para realizar um encapsulamento de fórmula, é necessário usar **Standard Inputs**. Na página a seguir, temos uma explicação mais detalhada de como ela funciona:

{% page-ref page="../standard-inputs/" %}

### 2. Execução

Ao [**implementar uma fórmula**](como-implementar-formulas/), você precisa pegar o arquivo onde a operação está codificada e executar a linha de comando associada à fórmula encapsulada.

A linha de comando da fórmula encapsulada deve ser executada utilizando **Standard Inputs** e informando os seus parâmetros de entradas diretamente no código.

### 3. Exemplo

A fórmula **`rit publish repo`** foi implementada usando o encapsulamento de fórmula. Inclusive, você pode encontrar no Github a [**implementação dessa fórmula**](https://github.com/ZupIT/ritchie-formulas/tree/master/publish/repo)**.** 

No exemplo abaixo, você verá como esse encapsulamento funciona na parte do código usando **`Input flags`**. 

{% hint style="warning" %}
Vale reforçar que essa fórmula foi implementada usando **Shell**, mas o raciocínio seria o mesmo para qualquer outra linguagem de programação.
{% endhint %}

```text
runFormula() {
  if [ "Github" == $PROVIDER ]
  then
    echo "🐙 Github provider selected"
    rit github publish repo --privacy=$PRIVACY --project_name=$PROJECT_NAME --workspace_path=$WORKSPACE_PATH --version=$VERSION
  elif [ "Gitlab" == $PROVIDER ]
  then
    echo "🦊 Gitlab provider selected"
    rit gitlab publish repo --privacy=$PRIVACY --project_name=$PROJECT_NAME --workspace_path=$WORKSPACE_PATH --version=$VERSION
  else
    echo "🤖 Unexpected Provider informed. Check it please and try again."
  fi
}
```

Aqui, de acordo com a entrada informada pelo usuário, duas fórmulas diferentes podem ser executadas: 

1. **`rit github publish repo`**
2. **`rit gitlab publish repo`**

Para tanto, os parâmetros de entrada das fórmulas encapsuladas são informados dinamicamente de acordo com os parâmetros de entrada da fórmula principal \(**`rit publish repo`**\).

Dependendo da operação, os **`inputs flags`** do comando podem ser gerados de acordo com outras operações realizadas durante a execução da fórmula principal, antes de executar a linha de comando da fórmula encapsulada.

## Próximos passos 

Nessa seção, você viu como funciona o encapsulamento de fórmulas no Ritchie.  Para continuar lendo sobre os comandos do Ritchie:

👉 Cheque os[ **desafios**](../../challenges/o-que-sao-esses-desafios.md) que criamos para você praticar as diversas funcionalidades do Ritchie.

👉 Cheque a [**lista de comandos**](../../reference/lista-de-comandos-e-flags.md) para ver as automações disponíveis no repo da nossa comunidade. 
