---
description: >-
  Nesta seção, você encontrará o passo a passo para fazer o build de fórmulas no
  Ritchie.
---

# Como "buildar" fórmulas

## Como "buildar"?

Depois de [**criar uma fórmula**](como-criar-formulas.md),  se você quiser editar o código dela, será necessário fazer o build dessas alterações para testar o comando com a nova implementação. 

Para isso, basta executar o comando:  ****

```text
rit build formula
```

  
****Você deverá informar: 

* O **caminho  do diretório** onde a fórmula está localizada.
* O **caminho da fórmula** a ser buildada \(ele segue o comando da fórmula\). 

Caso queira atualizar o código da fórmula em tempo de execução, é possível utilizar a **flag “--watch”** junto da fórmula. Veja no exemplo abaixo:   
****

```text
rit build formula --watch
```

## Próximos passos

Nessa seção, você viu como fazer o build de uma fórmula no Ritchie. Para continuar configurando sua fórmula: 

👉 Vá para página de como [**publicar uma fórmula**](como-publicar-formula.md) para ver como transferir seu trabalho para um repositório público. 

