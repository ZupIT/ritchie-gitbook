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
  
The variable **name** will be convert **uppercase** as the **local variable name**. 
{% endhint %}

> A good practice is to add a _**`RIT_`**_ suffix to each **`input name`** to avoid having conflicts with local variables.  
>   
> Example_: `rit_file_name` --&gt; `RIT_FILE_NAME`_

* `type`: 

  * **text** \(string\), 
  * **list** \(string, associated with a list of **items**\),
  * **bool** \(boolean, associated with a list of **items\*\***\), 
  * **password** \(hidden string on the CLI\), 
  * **multiselect** \(string, associated with a list of **items**\),
  * **credentials** _\(specific type, learn more informations_ [_**here**_](https://docs.ritchiecli.io/tutorials/credentials#how-to-use-credentials-as-formula-inputs)_\),_
  * **dynamic** _\(associated with the optional `request_info` field below\),_
  * _**path** \(autocomplete string with `tab` key\)_

  \_\_

* `label` : text appearing on the CLI, asking for the input. 

_\*\* the **item list** for boolean values can be `false`, `true`, `"yes"` \(string\) or `"no"` \(string\), where `"yes"` will be convert to `true`, and `"no"` to `false`._

#### Input example with mandatory fields:

```text
{
      "label": "Type your name:",
      "name": "rit_name",
      "type": "text",
}
```

#### Input example with the boolean type:

```text
{
      "label": "I'm of legal age:",
      "name": "rit_legal_age",
      "type": "bool",
      "items": [
           true,
           false
      ]
}
```

#### Input example with the multiselect type:

```text
{
      "label": "Choose one or more days: ",
      "name": "rit_days",
      "type": "multiselect",
      "required": true,
      "items": [
           "Monday",
           "Tuesday",
           "Wednesday",
           "Thursday",
           "Friday",
           "Saturday",
           "Friday"
      ]
}
```

#### Some observations regarding the **`multiselect` type**

* To select one of the options with the `multiselect` type, you must press the `space` key \(the`enter` key will move to the next input, if any\)
* The options selected in the `multiselect` type field will return a string with the options separated by pipe \(`|`\) and without space example: `Monday | Wednesday | Friday`
* It is suggested to use the `required` field as`true`, otherwise, if no option is selected, the local variable will be saved as `undefined` 

#### Parameter example using the autocomplete type: 

```text
{
      "label": "Type the path to the folder with your file:",
      "name": "rit_path",
      "type": "path"
}
```

### Optional fields

* `default`: default input value \(**if** **null**\). 

```text
{
      "label": "Type your name:",
      "name": "rit_name",
      "type": "text",
      "default": "Dennis"
}
```

{% hint style="info" %}
You also can make this default configuration with the default flag, which allows you to attribute default values configured on the formula.

In case of fields without a default value, the flag will keep asking for this inputs that must be configured on your config.json file.
{% endhint %}

* `required`: boolean that indicates if the input value is required or optional.

```text
{
      "label": "Type your name:",
      "name": "rit_name",
      "type": "text",
      "required": true
}
```

* `tutorial`: input helper message _\[? for help\]_ 

```text
{
      "label": "Type your name:",
      "name": "rit_name",
      "type": "text",
      "tutorial": "We are expecting you to write your name (ex: John)"
}
```

* `items`: list of input variable options. 

```text
{
      "label": "Type your name:",
      "name": "rit_name",
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
      "name": "rit_name",
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
      "name": "rit_name",
      "type": "text",
      "default": "Dennis"
},
{
      "condition": {
            "variable": "rit_name",
            "operator": "!=",
            "value": "Dennis"
      },
      "label": "What is your date of birth?",
      "name": "rit_date_of_birth",
      "type": "text"
}
```

* `pattern`: configure an input value validation. 
  * `regex`: The regex pattern to validate the input.
  * `mismatchText`: error message when input doesn't match the regex pattern

```text
{
      "label": "What is your age",
      "name": "rit_age",
      "type": "text",
      "pattern": {
            "regex": "[0-9]",
            "mismatchText": "Only a numerical value is allowed here (ex: 20)"
      }
}
```

* `requestInfo`: configuration to get dynamic input type.
  * `url`: URL to consume a GET service that will return a list of objects.
  * `jsonPath`: Path to the variable to extract from the returned list, for each object. \(Check out ****[**how works the json path**](https://goessner.net/articles/JsonPath/)\).

```text
{
      "label": "Type your name:",
      "name": "rit_name",
      "type": "dynamic",
      "requestInfo": {
            "url": "https://my-url.com",
            "jsonPath": $..users
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
      "name": "rit_system",
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
        "variable":"rit_system",
        "operator":"==",
        "value":"LINUX"
      },
      "label": "Select a LINUX OS:",
      "name": "rit_linux_os",
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

