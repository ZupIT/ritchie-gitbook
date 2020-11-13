# Comandos de fórmulas

Com fórmulas, as Input flags tem como base os **nomes dos parâmetros de entrada** que são informados no arquivo **config.json** no momento de implementar uma fórmula. 

### **Exemplo**

1. Comando de fórmula: **`rit demo formula`**

   \*\*\*\*

2. Nomes dos parâmetros de entrada que são perguntados pelo arquivo config.json:

   * **`name`**
   * **`surname`**
   * **`dateOfBirth`**

3. Execução da fórmula com Input flags:

```text
rit demo formula --name='dennis' --surname='ritchie' --dateOfBirth='09/09/1941'
```

{% hint style="danger" %}
O comando de fórmula, através do input flags, precisa dos parâmetros de entrada que são colocados no config.json para funcionar corretamente.  
{% endhint %}

