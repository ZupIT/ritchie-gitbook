---
description: 'Nesta seção, você encontrará tudo sobre a flag STDIN.'
---

# Como usar a flag STDIN

Informar parâmetros de entrada através de **argumentos** ou **flags** permite que você automatize workflows. 

 É particularmente útil quando você estiver manipulando outras ferramentas dentro do script, assim você automatiza operações sem precisar interagir com o terminal. 

{% hint style="danger" %}
A flag **`--stdin`** no Ritchie foi desenvolvida para também dar suporte nesse cenário. Nesse caso, os parâmetros de entrada devem ser informados em um **formato JSON**:

**`echo`**`'{"key":"value"}'`**`|`**`RIT (GROUP) VERB NOUN` **`--stdin`**
{% endhint %}

![](../../.gitbook/assets/screen-shot-2020-08-27-at-15.22.10.png)

## **Próximos passos**

Você viu nessa seção como funciona a flag --stdin. Se você quiser ler mais sobre comandos no Ritchie:

👉 Confira a seção [**comandos de fórmulas** ](comandos-de-formulas.md)para ver mais possibilidades de automações.

👉 Confira a seção [**comandos core**](comandos-core.md) ****para ver mais comandos que podem ser usados por meio de stdin. 

