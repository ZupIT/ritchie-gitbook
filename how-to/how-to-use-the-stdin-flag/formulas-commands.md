---
description: >-
  In this section, you will find more details about commands that run with
  Ritchie's formulas.
---

# Formulas commands

With formulas, the STDIN flag **JSON** is based on the **inputs parameters names** informed on the **config.json file** used to implement the formula.

### **Example**

1. Formula command: **`rit demo formula`**

   \*\*\*\*

2. Inputs names asked in the config.json file:

   * **`name`**
   * **`surname`**
   * **`dateOfBirth`**

3. Formula execution with STDIN:

```text
echo '{"name":"Dennis", "surname":"Ritchie", "dateOfBirth":"09/09/1941"}' | rit demo formula --stdin
```



{% hint style="danger" %}
The formula's command through stdin, needs the input parameters that are based on the config.json, in order to work properly. 

If the formula's implementation asks for data via **prompt**, it will not be possible to exclusively use  stdin for the formula to run successfully.
{% endhint %}

