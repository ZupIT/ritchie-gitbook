# Formulas commands

With formulas, the STDIN flag **JSON** id based on the **inputs parameters names** informed on the **config.json file** used to implement the formula.

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
Because it's based on the **config.json** file, for the formula's commands to work through **stdin**, it is necessary that this formula works informing **exclusively** the input parameters through the config.json file.

If the formula's implementation asks for data via **prompt**, it will not be possible to use exclusively stdin for the formula to run successfully. 
{% endhint %}

