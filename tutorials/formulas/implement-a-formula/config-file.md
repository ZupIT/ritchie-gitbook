---
description: 'In this section, you will find information about a formula config.json file'
---

# Config File

## What is the config.json file?

The **config.json** file contains the formula's input parameters. It allows the CLI to know what datas to ask the user when he runs the command in the terminal in order to process the formula correctly.

These input parameters are made up of the following fields:

* a **`docker image builder`** \(according to the programming language chose at the formula creation\) 
* the formula **`inputs parameters list`**.

```text
{
  "dockerImageBuilder": "dockerImage",
  "inputs": []
}
```

## Input parameter configuration

Each input parameter is composed of the following fields:

### Mandatory fields

* `name`: variable name to extract.

{% hint style="warning" %}
Once an input value is informed on Ritchie CLI, it is saved as a **local variable** during the formula execution.  
  
The variable **name** will be convert **UPPERCASE** as the **local variable name**. 
{% endhint %}

> A good practice is to add a _**`RIT_`**_ suffix to each **`input name`** to avoid having conflicts with local variables.  
>   
> _**ex**: `rit_file_name` --&gt; `RIT_FILE_NAME`_

* `type`: 
  * _**text**_ \(string\), 
  * _**bool**_ \(boolean\), 
  * _**password**_ \(hidden string on CLI\), 
  * _**credentials** \(specific type, learn more informations_ [_**here**_](https://docs.ritchiecli.io/tutorials/credentials#how-to-use-credentials-as-formula-inputs)_\)_
  * _**dynamic** \(associated with the optional `request_info` field below\)_ 
* `label` : text appearing on the CLI, asking for the input. 

#### Input example with mandatory fields:

```text
{
      "label": "Type your name:",
      "name": "name",
      "type": "text",
}
```

### Optional fields

* `default`: default input value \(**if** **null**\). 

```text
{
      "label": "Type your name:",
      "name": "name",
      "type": "text",
      "default": "Dennis"
}
```

* `required`: boolean that indicates if the input value is required or optional.

```text
{
      "label": "Type your name:",
      "name": "name",
      "type": "text",
      "required": true
}
```

* `tutorial`: input helper message _\[? for help\]_ 

```text
{
      "label": "Type your name:",
      "name": "name",
      "type": "text",
      "tutorial": "We are expecting you to write your name (ex: John)"
}
```

* `items`: list of input variable options. 

```text
{
      "label": "Type your name:",
      "name": "name",
      "type": "text",
      "items": [
            "Dennis",
            "John",
            "Bill"
      ]
}
```

* `cache`:  saves former input values.
  * `active`: if cache is enabled or not.
  * `qty`: amount of values to store.
  * `newLabel`: text appearing on the CLI asking for a new input. 

```text
{
      "label": "Type your name:",
      "name": "name",
      "type": "text",
      "cache": {
            "active": true,
            "qty": 5,
            "newLabel": "Type another name:"
      }
}

```

* `condition`: shows this input if the given condition succeeds
  * `variable`: The variable name used on a previous input for comparison.
  * `operator`: A logical operator to compare. Supports **`==`**, **`!=`**, **`<`**, **`>`**, **`<=`**, and **`>=`.**
  * `value`: The desired value to compare to.

```text
{
      "label": "Type your name:",
      "name": "name",
      "type": "text",
      "default": "Dennis"
},
{
      "condition": {
            variable: "name",
            "operator": "!=",
            "value": "Dennis"
      }
      "label": "What is your date of birth?",
      "name": "date_of_birth",
      "type": "text",
}
```

* `pattern`: configure an input value validation. 
  * `regex`: The regex pattern to validate the input.
  * `mismatchText`: error message when input doesn't match the regex pattern

```text
{
      "label": "What is your age",
      "name": "age",
      "type": "text",
      "pattern": {
            "regex": [0-9],
            "mismatchText": "Only a integer value is allowed here (ex: 20)"
      }
}
```

* `requestInfo`: configuration to get dynamic input type.
  * `url`: URL to consume a GET service that will return a list of objects.
  * `jsonPath`: Path to the variable to extract from the returned list, for each object. \(Check out ****[**how works the json path**](https://goessner.net/articles/JsonPath/)\).

```text
{
      "label": "Type your name:",
      "name": "name",
      "type": "text",
      "requestInfo": {
            "url": "https://my-url.com",
            "jsonPath": $['user']['name']
      }
}
```

{% hint style="info" %}
Each formula can contain as many inputs as necessary, as well as any association of the above fields.
{% endhint %}

**Conditional input example with Regex pattern:**

```text
"inputs": [
    {
      "label": "Select a system:",
      "name": "system",
      "type": "text",
      "items": [
        "LINUX",
        "MACOS",
        "WINDOWS"
      ],
      "required": true,
      "tutorial": "Select a System from the list."   
    },
    {
      "condition": {
        "variable":"system",
        "operator":"==",
        "value":"LINUX"
      },
      "label": "Select a LINUX OS:",
      "name": "linux-os",
      "type": "text",
      "items": [
        "UBUNTU",
        "FEDORA",
        "CENTOS"
      ],
      "pattern": {
        "regex": "UBUNTU|FEDORA|CENTOS",
        "mismatchText": "Invalid option"
      },
      "required": false,
      "tutorial": "Select an Linux Operating System from the list."   
    }
  ]
```

{% hint style="warning" %}
Once an input is informed on Ritchie CLI, it is saved as a **local variable** during the formula execution.
{% endhint %}

