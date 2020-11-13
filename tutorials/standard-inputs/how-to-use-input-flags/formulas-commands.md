# Formulas commands

With formulas, the Input flags are based on the **inputs parameters names** informed on the **config.json file** used to implement the formula.

### **Example**

1. Formula command: **`rit demo formula`**

   \*\*\*\*

2. Inputs names asked in the config.json file:

   * **`name`**
   * **`surname`**
   * **`dateOfBirth`**

3. Formula execution with input flags:

```text
rit demo formula --name='dennis' --surname='ritchie' --dateOfBirth='09/09/1941'
```



{% hint style="danger" %}
The formula's command through Input flags, needs the input parameters that are based on the config.json, in order to work properly. 
{% endhint %}

