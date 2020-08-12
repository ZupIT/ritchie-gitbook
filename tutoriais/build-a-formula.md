---
description: >-
  Você encontrará nessa seção o passo a passo para fazer o build de fórmulas no
  Ritchie.
---

# Como "buildar" fórmulas

## Como "buildar"?

Depois de [**criar uma fórmula**](como-criar-formulas.md),  se desejar, você pode editar o código da fórmula, será necessário fazer o build dessas alterações para testar o comando com a nova implementação. 

Para isso, basta executar o comando:  ****

```text
$ rit build formula
```

  
****Você deverá informar: 

* O **path  do diretório** onde a fórmula está salva.
* O **caminho para a fórmula** a ser buildada \(o comando da fórmula\). 

Caso queira atualizar o código da fórmula em tempo de execução, é possível utilizar a **flag “--watch”** junto da fórmula. Veja no exemplo abaixo:   
****

```text
$ rit build formula --watch
```

## Próximos passos

Nessa seção, você viu como fazer o build de uma fórmula no Ritchie. Para continuar configurando sua fórmula: 

👉 Vá ao [**publicar uma fórmula**](como-publicar-formula.md) para ver como transferir seu trabalho para um repositório público. 

👉 Vá a [**executar uma fórmula** ]()para ver como proceder com a execução das fórmulas no Ritchie.

