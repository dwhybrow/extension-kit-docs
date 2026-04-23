## Introduction

A **Mapping table** is table of correspondence for mapping a specific set of input values to a set of output values over different time periods.

> More details about [Mapping table structure here](https://docs-external.u4pp.com/extensions-kit/guides/portal/mapping-tables/#example-of-a-mapping-table-json-file)

Mapping tables can be used inside Extension Kit Flows through templating expressions and are available from the templating fields menu "[+]".

> See [Templating](https://docs-external.u4pp.com/extensions-kit/guides/portal/templating/) for more details.

## Basic example

In this example, we will use a simple mapping table that we call `Country mappings` to **map** a `Country code` (in this case `ES`) to a `Country name` (`Spain`) and we will use it in an _Email action_ based on a parameter.

```
{
    "Name": "Country mappings",
    "Definition": {
        "properties": {
            "CountryCode": {
                "type": "string",
                "description": "Country code.",
                "minLength": 2,
                "isKey": true
            },
            "CountryName": {
                "type": "string",
                "description": "Country name.",
                "minLength": 1
            }
        }
    },
    "Data": [
        {
            "CountryCode": "ES",
            "CountryName": "Spain"
        },
        {
            "CountryCode": "PL",
            "CountryName": "Poland"
        },
        {
            "CountryCode": "FR",
            "CountryName": "France"
        },
        {
            "CountryCode": "PT",
            "CountryName": "Portugal"
        },
        {
            "CountryCode": "IT",
            "CountryName": "Italy"
        }
    ]
}
```

In the _Email action_, let's say we want to set the email subject like so. We put the _Country name_ that matches the _Country code_ stored in a specific parameter:

### Step 1: select the mapping table value we want to display:

![Image 1: Mapping Table Country Code Open Templating Menu](https://docs-external.u4pp.com/extensions-kit/images/portal/mapping-table-country-code-open-templating-menu.png)

Result of selecting _CountryName_ from Templating menu above:

![Image 2: Mapping Table Country Code Result Of Templating Menu](https://docs-external.u4pp.com/extensions-kit/images/portal/mapping-table-country-code-result-of-templating-menu.png)

### Step 2: provide the key values:

You can notice that the key values have to be given by either a correct value or another templating expression.

In the example above, the string `"***CountryCode key value here***"` can be replaced either by an actual value (like `"ES"`) or by another templating expression like `parameters.CurrentCountryCode` as below:

![Image 3: Mapping Table Country Code Result Of Templating Menu2](https://docs-external.u4pp.com/extensions-kit/images/portal/mapping-table-country-code-result-of-templating-menu2.png)

When using this action, if the parameter `CurrentCountryCode` contains the country code `ES`, then this templating expression above will be resolved by giving the following string as a result in the email subject:

`For Country: Spain`

> **NOTE**: If no matching value is found, based on the given key values, it will be resolved with an empty string

## Complex example with all the possible cases

The following example illustrates a mapping table value that is an array.

Here is the summary of the mapping table `Cost centre mappings` used here:

```
{
    "Name": "Cost centre mappings",
    "KeyColumns": [
        "productCode",
        "isLocal",
        "year"
    ],
    "ValueColumns": [
        "costCentre",
        "costCountries",
        "costMonths"
    ]
}
```

It has: * 3 key columns: 1 string `productCode`, 1 boolean `isLocal` and 1 integer `year` * 3 value columns: 1 string `costCentre` and 1 array of strings `costCountries` and 1 array of integers `costMonths`

And it also has this _keys-values_ combination among its data:

```
{
    "productCode": "PRODUCT2",
    "isLocal": true,
    "year": 2022,
    "costCentre": "COSTCENTER2",
    "costCountries": [ "Belgium", "Germany" ],
    "costMonths": [ 5, 11 ]
}
```

The following templating example can be used to **loop** on the `costCountries` array:

```
The countries are: 
{% assign arrayOfCountries = MappingTableEval "Cost centre mappings" "costCountries" "PRODUCT2" "true" 2022 %}
{% for costCountryItem in arrayOfCountries %} 
  - {{ costCountryItem }} 
{% endfor %}
```

*   Line 2 is where the array variable `arrayOfCountries` is assigned with the result of mapping table evaluation of the value column `costCountries` for the given 3 keys `"PRODUCT2"`, `"true"` and `2022`
*   Line 3 is a _for-loop_ on this array where the current item goes to the variable `costCountryItem`
*   Line 4 is where the current item `costCountryItem` is used
*   Line 5 is the end of the _for-loop_

> **NOTE**: a boolean key value must be surrounded by double-quotes like strings (like `"true"`)

## Rules to be strictly followed

### Some technical explanations

The templating expression that is provided has the following format:

`{{MappingTableEval "Cost centre mappings" "costCentre" "***productCode key value here***" "***isLocal key value here***" "***year key value here***"}}`

where `MappingTableEval` is a keyword function name whose meaning is: from mapping table `Cost centre mappings`, we want the `costCentre` value that is matching the 3 given key columns `productCode`, `isLocal` and `year`.

By all means, the user has to give proper values or valid templating expression to the 3 key columns that are surrounded by `***`.

> **NOTE**: Make sure to provide the right `type` for key values: `string` and `boolean` values must be surrounding by double-quotes (e.g. `"ES"` or `"false"`), whereas `integer` and `number` values must not (e.g. `2022` or `123.45`)

### Respect order of the key values

The key value parameters must be provided **in the same order** as they appear in the **Mapping Table definition**. So, after having selected a mapping table value from the templating menu, the user just has to provide key values without changing the order they are passed to the templating function `MappingTableEval`. Otherwise it might lead to an error or an expected result.

### What if not matching value is found

If no values match the given key values, the templating expression just returns **an empty string**.

## Troubleshoot

Here is a list of the possible errors you might encounter when using mapping table in a flow:

1.   When using a wrong mapping table name that does not exist

![Image 4: Mapping Table Country Code Error Wrong Mt Name](https://docs-external.u4pp.com/extensions-kit/images/portal/mapping-table-country-code-error-wrong-mt-name.png)

> **NOTE**: The user is not supposed to modify the mapping table name after having selected it from the templating menu

* * *

1.   When using a wrong value column name

![Image 5: Mapping Table Country Code Error Wrong Value Name](https://docs-external.u4pp.com/extensions-kit/images/portal/mapping-table-country-code-error-wrong-value-name.png)

> **NOTE**: The user is not supposed to modify the value column name after having selected it from the templating menu

* * *

1.   When a key value is populated with the wrong type

![Image 6: Mapping Table Country Code Error Wrong Key Type1](https://docs-external.u4pp.com/extensions-kit/images/portal/mapping-table-country-code-error-wrong-key-type1.png)

Unexpected errors whose meaning does not to mention clearly an issue related the mapping table template, like the one above, might be due to **a wrong type in key values**. For example, when a string or a boolean is passed without double-quotes or a number/integer is passed with double-quotes.

* * *

1.   When the number of key values is not the one expected

![Image 7: Mapping Table Country Code Error Wrong Number Of Key Values](https://docs-external.u4pp.com/extensions-kit/images/portal/mapping-table-country-code-error-wrong-number-of-key-values.png)

> **NOTE**: The user is not supposed to add or remove key values, but just provide a correct value for each of them

* * *

## Example of a mapping table JSON file

### Mapping table structure

A mapping table consists of 4 properties: - `MappingTableId`: the unique identifier of a mapping table. MappingTableId is not required when importing a mapping table. - `Name`: the name of the mapping table that will be used in the Portal. Name is required when importing a mapping table. - `Definition` object that is a JSON Schema that describes the mapping table structure (more detail here https://json-schema.org/). Definition is required when importing a mapping table. - `Data` array that contains the possible combinations of key / value columns. Data is optional as it's possible to create a mapping table without data.

The `Definition` object is a **JSON schema** that must have: - `properties` object: that contains the columns that make up the mapping table. There are 2 types of columns : **key** and **values**. The **key** columns must have the boolean property `isKey` set to `true`. The other columns that do not have this `"isKey": true` will be considered as **value** columns.

### Mapping table example

In the following JSON example, the mapping table Definition has **3 key columns** and **7 value columns**, and it also has 2 Data items. It covers all possible use cases in term of **field types** as follows: - `"myBooleanKey"`: a **boolean** - `"myDropdownKey"`: a **restricted string** whose value must be taken from an **enum** of possible values - `"myIntegerKey"`: an **integer** within a min/max range - `"myNumberValue"`: a **decimal number** within a min/max range - `"myDropdownIsListValue"`: a **list of restricted string** values, taken from an enum of possible values - `"myEmailValue"`: a string that must match the **email** format - `"myUrlValue"`: a string that must match the **url** format - `"myStringIsListValue"`: a **list of free string** values - `"myStringValue"`: a basic **free string** - `"myStringWithPatternValue"`: a **restricted string** that must match the given **pattern**

```
{
  "Name": "My mapping table",
  "Definition": {
    "properties": {

      "myBooleanKey": {
        "type": "boolean",
        "description": "True or False.",
        "isKey": true
      },

      "myDropdownKey": {
        "type": "string",
        "enum": [
          "First option",
          "Second option",
          "Third option",
          "Fourth option",
          "Fifth option",
          "Long description option Long description option"
        ],
        "default": "Second option",
        "description": "Dropdown column.",
        "isKey": true
      },

      "myIntegerKey": {
        "type": "integer",
        "description": "Integer Min= 1000 Max = 9999.",
        "minimum": 1000,
        "maximum": 9999,
        "isKey": true
      },

      "myNumberValue": {
        "type": "number",
        "description": "Number Min= -10.5 Max = 20.9",
        "minimum": -10.5,
        "maximum": 20.9
      },

      "myDropdownIsListValue": {
        "type": "array",
        "items": {
            "type": "string",
            "enum": [
              "First option",
              "Second option",
              "Third option"
            ]
        },
        "default": "Second option",
        "description": "Dropdown column checkbox"
      },

      "myEmailValue": {
        "type": "string",
        "format": "email",
        "description": "E-mail."
      },

      "myUrlValue": {
        "type": "string",
        "format": "uri",
        "description": "URL."
      },

      "myStringIsListValue": {
        "type": "array",
        "description": "List of strings.",
        "items": {
            "type": "string" 
        }
      },

      "myStringValue": {
        "type": "string",
        "description": "String with length between 5 and 25.",
        "minLength": 5,
        "maxLength": 25
      },

      "myStringWithPatternValue": {
        "type": "string",
        "description": "String with pattern [A-Z][a-z]*.",
        "pattern": "^[A-Z][a-z]*$"
      }
    }
  },
  "Data": [
    {
      "myBooleanKey": true,
      "myDropdownKey": "Second option",
      "myIntegerKey": 2022,

      "myNumberValue": 20.9,
      "myDropdownIsListValue": [ "Third option", "First option" ],
      "myEmailValue": "john@doe.com",
      "myUrlValue": "http://john-doe.com",
      "myStringIsListValue": [ "value1", "value2" ],
      "myStringValue": "any string value",
      "myStringWithPatternValue": "Test"
    },
    {
      "myBooleanKey": false,
      "myDropdownKey": "First option",
      "myIntegerKey": 2023,

      "myNumberValue": -0.8,
      "myDropdownIsListValue": [ "First option", "Second option" ],
      "myEmailValue": "james@doe.com",
      "myUrlValue": "http://john-doe.com/james",
      "myStringIsListValue": [ "value1", "value2", "value3" ],
      "myStringValue": "another string value",
      "myStringWithPatternValue": "Anothertest"
    }
  ]
}
```
