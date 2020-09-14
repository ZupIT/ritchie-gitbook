---
description: >-
  Nesta seção, você encontrará mais detalhes sobre comandos que rodam com
  fórmulas no Ritchie.
---

# Comandos de fórmulas

Com fórmulas, o id do **JSON** com a flag  STDIN tem como base os **nomes dos parâmetros de entrada** que são informados no arquivo **config.json** no momento de implementar uma fórmula. 

### **Exemplo**

1. Comando de fórmula: **`rit demo formula`**

   \*\*\*\*

2. Nomes de inputs que são perguntadas pelo arquivo config.json:

   * **`name`**
   * **`surname`**
   * **`dateOfBirth`**

3. Execução da fórmula com STDIN:

```text
echo '{"name":"Dennis", "surname":"Ritchie", "dateOfBirth":"09/09/1941"}' | rit demo formula --stdin
```



{% hint style="danger" %}
O comando de fórmula, através do stdin, precisa dos parâmetros de entrada que são colocados no config.json para funcionar corretamente.  

Se, durante a implementação da fórmula, for demandada uma informação via **prompt**, não será possível usar exclusivamente o stdin para fórmula ser executada com sucesso. 
{% endhint %}

