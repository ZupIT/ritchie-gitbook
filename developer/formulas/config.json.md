# Config.json

{% hint style="info" %}
The formula input parameters are configured within the **config.json** file contained in the formula folder.
{% endhint %}

This file contains the following information: 

* a description 
* the formula input parameters 

These input parameters are made up of the following fields: 

* name 
* type
* label 
* default \(optional\) 
* items \(optional\) 
* cache \(optional\)

```text
{
  "description": "Sample inputs in Ritchie.",
  "inputs" : [
    {
      "name" : "sample_text",
      "type" : "text",
      "label" : "Type : ",
      "cache" : {
        "active": true,
        "qtd" : 6,
        "newLabel" : "Type new value. "
      }
    },
    {
      "name" : "sample_list",
      "type" : "text",
      "default" : "in1",
      "items" : ["in_list1", "in_list2", "in_list3", "in_listN"],
      "label" : "Pick your : "
    },
    {
      "name" : "sample_bool",
      "type" : "bool",
      "default" : "false",
      "items" : ["false", "true"],
      "label" : "Pick: "
    }
  ]
}
```

The **name** field refers to the name of the variable that will be extracted when implementing the formula. 

The **type** field represents the type of the variable \(currently there is only TEXT and BOOL\) 

The **label** field is the text that will appear to the user via PROMPT to inform this variable. 

The **default** field is the value of the variable that will come by default if the choice is a list of options. 

The **items** field is the list of possible options for the variable. 

The **cache** field allows to configure whether it is necessary to store the user's choices for this variable. It consists of 3 fields: 

* active 
* qtd 
* newLabel. 

The **active** field indicates whether the cache is enabled or not. 

The **qtd** field refers to the number of choices that can be stored in the cache.

The **newLabel** field is for the user to enter another value for the variable if those saved in the cache do not meet their needs.

