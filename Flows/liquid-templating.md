#Templating

Templating allows you to render dynamic content in actions or triggers. For example, render actions and trigger outputs into another action field:

`{{ step0:Body.supplierId }}`

## Liquid templating language in Extension Kit

The implemented templating language in Extension Kit aims to comply with the Liquid templating language, but it contains some custom functions to provide additional functionality and certain Liquid functions are adapted to better suit Extension Kit requirements. See the [official Liquid documentation](https://shopify.github.io/liquid/) for more details.

## Liquid filters supported in Extension Kit

Filters change the output of a Liquid object and are used within an output separated by a `|`. For example:

*   `{{ "TEST STRING" | downcase }}  => "test string"`
*   `{{ "Name Surname" | split: " " | first }} => Name`

List of the supported filters:

✅ Supported filters

❌ Not supported filters

⚠️ Differ from standard Liquid

| Name | Supported | Comments |
| --- | --- | --- |
| abs | ✅ |  |
| append | ✅ |  |
| at_least | ✅ |  |
| at_most | ✅ |  |
| capitalize | ✅ |  |
| ceil | ✅ |  |
| date | ✅/⚠️ | In Extension Kit, you must use the `date.to_string <datetime> <pattern> <culture>` filter. See [Date](https://docs-external.u4pp.com/extensions-kit/guides/portal/templating/#date) for more details. |
| default | ✅ |  |
| divided_by | ✅ |  |
| downcase | ✅ |  |
| escape | ✅ |  |
| escape_once | ✅ | If the string already contains escaped characters, they are not modified further, for example: `{{ "1 &lt; 2 &amp; 3" | escape_once }} -> 1 &lt; 2 &amp; 3` |
| first | ✅ |  |
| floor | ✅ |  |
| join | ✅ |  |
| last | ✅ |  |
| lstrip | ✅ |  |
| map | ✅ |  |
| minus | ✅ |  |
| modulo | ✅ |  |
| newline_to_br | ✅ |  |
| plus | ✅ |  |
| prepend | ✅ |  |
| remove | ✅ |  |
| remove_first | ✅ |  |
| replace | ✅ |  |
| replace_first | ✅ |  |
| reverse | ✅ |  |
| round | ✅ |  |
| rstrip | ✅ |  |
| size | ✅ |  |
| slice | ✅ |  |
| sort | ✅ |  |
| sort_natural | ✅ |  |
| split | ✅ |  |
| strip | ✅ |  |
| strip_html | ✅ |  |
| strip_newlines | ✅ |  |
| times | ✅ |  |
| truncate | ✅ |  |
| truncatewords | ✅ |  |
| uniq | ✅ |  |
| upcase | ✅ |  |
| url_decode | ✅ |  |
| url_encode | ✅/⚠️ | The function `url_encode` requires the word html to work. It converts any URL-unsafe character in a string into percent-encoded characters, for example: `{{ "Tetsuro Takara" | html.url_encode }} => "Tetsuro%20Takara"` |
| where | ✅ |  |

## Default flow variables

A flow has the following variables set up as default:

*   `{{ defaultVariables.tenantId }}` - unique identifier of the current tenant TenantId. 
*   `{{ defaultVariables.flowId }}` - unique identifier of the flow currently running FlowId. 
*   `{{ defaultVariables.runId }}` - unique identifier of the current run of the flow RunId. 
*   `{{ defaultVariables.operationId }}` - unique identifier of the current [distributed trace](https://w3c.github.io/trace-context/#trace-id). It is created from the incoming `traceparent` when the flow is triggered. If it is not triggered with a `traceparent`, a new one is generated. It is propagated to external systems on HTTP calls and messages. 
*   A `parameters` object that contains the tenant parameters.

![Image 1: Templating default variables](https://docs-external.u4pp.com/extensions-kit/images/portal/templatingv2-default-variables.png)

This can be extended with additional values provided by the team.

## Additional functions

By default we include additional [builtin functions](https://github.com/lunet-io/scriban/blob/master/doc/builtins.md) attached to the different data types. To use them you must include the data type they belong to, for example:

*   `{{ string.capitalizewords "example text" }}`
*   `{{ [1, 2, 3] | array.add 4 }}`
*   `{{ product | object.has_key "title" }}`

Existing data types:

*   array
*   date
*   html
*   math
*   object
*   regex
*   string
*   timespan

## Date

The date filter in Extension kit is different from the [Liquid `date` filter](https://shopify.github.io/liquid/filters/date/).

*   In Liquid, you can use `date` in the following way:

`{{ step1.Body.publishedDate | date: "%a, %b %d, %y" }}`

*   Instead, in Extension Kit, you must use the `date.to_string <datetime> <pattern> <culture>` filter.

Example: `{{ step1.Body.publishedDate | date.to_string '%d %b %Y' }}` or `{{ date.now | date.to_string '%d %b %Y' }}`

You can parse dates that come in a string format, for example: `{{ date.parse '2016/01/05' }}`. E

Example of a parse plus a format: `{{ date.parse step0.Body.date | date.to_string '%a, %b %d, %y' }}` where `step0.Body.date` equals `'2020/10/10'`. The result is `Sat, Oct 10, 20`.

You can also use a `date` type templating variable, for example current date, like this:

`{%- assign myDateVariable = date.now -%}`

To use this same variable in other actions, you must parse the date variable like this:

`{{ date.parse myDateVariable }}`

> Note: The system cannot parse `date` automatically because it may modify the actual value coming from third-party system, like ERPx, and Extension Kit must not modify the incoming data. That is why the action must parse the date variable accordingly when using it.

There are a lot of additional functions you can use with the `date` object:

*   date.now
*   date.add_days
*   date.add_months
*   date.add_years
*   date.add_hours
*   date.add_minutes
*   date.add_seconds
*   date.add_milliseconds
*   date.parse
*   date.to_string

Also, it is possible to set dates _from the past_ for all `date.add` functions, for example:

```
{% assign myDate = date.now | date.add_days (-1) %}
```

For more information, see the [scriban builtin date functions documentation](https://github.com/lunet-io/scriban/blob/master/doc/builtins.md#date-functions).

## Custom Liquid functions and enhanced operations

The following custom Liquid functions and enhanced operations are available:

### 1. array.each

The `array.each` function iterates over each string in the array to perform a specified action. For example, to remove any leading and trailing whitespace directly in the original array:

`array.each @string.strip`

### 2. array_strip

The `array_strip` function removes all leading and trailing whitespaces from the given array and returns a new array.

```
{% ["     ", "   too many spaces           "] | array_strip %}  => ["", "too many spaces"]
```

### 3. array.add/array.add_range

To populate a templating array, you can use

*   `array.add` to add a single item to an array. 
*   `array.add_range` to add an array to an existing array.

When adding a single item to an array:

*   If you use `array.add_range`, the item must be within square-brackets (an array), like this:

```
{%- for record in records -%}
    {{- invoices_retrieved = invoices_retrieved | array.add_range [ record ] -}}
{%- endfor -%}
```

*   If you use `array.add`, add the item like this:

```
{%- for record in records -%}
    {{- invoices_retrieved = invoices_retrieved | array.add record -}}
{%- endfor -%}
```

### 4. size_in_bytes

The `size_in_bytes` function returns the size in bytes of the file or string that where it is passed.

Examples of how the `size_in_bytes` function is used within a Liquid template are shown below:

`{{step0.Body | size_in_bytes}}`

`{{size_in_bytes "Lorem ipsum dolor sit amet, consectetur adipiscing elit. Sed rhoncus odio dui, eu feugiat enim lobortis vel." }}`

### 5. zip / unzip

You can include `zip` and `unzip` functions within a Liquid templating script to zip and unzip large files before sending and receiving.

When a file is unzipped and it is a binary file, it is converted to Base64, otherwise it is not encoded and the plain text, XML or JSON is passed on.

> Note: The `zip` and `unzip` functions use gzip compression and gunzip decompression.

Examples of how the `zip` and `unzip` functions are used within a Liquid template:

`{{zip step1.FileContent}}`

`{{unzip step2.Output}}`

You can set a limit on the size of the file to be zipped as shown in the example below, where only files larger than 5 Mbytes are zipped.

![Image 2: Zip file if size condition met](https://docs-external.u4pp.com/extensions-kit/images/portal/zip-unzip-size.png)

## Further relevant technical information

### Negative numbers

In Liquid operations, when a number is considered negative you must wrap it in parentheses.

Example:

```
{{ 4.9901 | at_most: (-4.9901) }}
```

### Splitting strings into individual characters

Using the default `string.split` or `split` filter does not allow to split strings to individual characters. Instead, use the [`regex.split`](https://github.com/scriban/scriban/blob/master/doc/builtins.md#regexsplit) filter.

Example:

```
{% assign result = '12345' | regex.split "" }} => ['1', '2', '3', '4', '5']
```

### Using variables that contain special characters

Liquid documentation states the following about variables containing special characters:

**Variables**: The most basic kind of expression is just the name of a variable. Liquid variables are named like Ruby variables. They must:

*   Consist of alphanumeric characters and underscores.
*   Always start with a letter.
*   Not have any kind of leading sigil, that is, they look like `var_name`, not `$var_name`.

In case that you need to access a variable that is not a valid Liquid variable name, you can use the following syntax:

`step1.Response["1variable-with-unsupported$chars"]`

Example:

❌ Incorrect

```
{{ step1.Response.value-with-hypens }}
```

✅ Correct

```
{{ step1.Response["value-with-hypens"] }}
```
