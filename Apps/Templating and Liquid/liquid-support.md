## Liquid JS template language support

## Overview

Liquid JS is an open-source template language that is used in many web applications to place dynamic content and modify data. All the Liquid JS API and syntax are fully supported in App Studio.

To learn more about Liquid JS, see the [official Liquid JS documentation](https://liquidjs.com/).

## Categories

In Liquid JS, there are three types of code: objects, tags, and filters.

### Objects

Objects are surrounded by matched pairs of curly braces `{{}}`. They can be used in App Studio to show content. The objects resolve to the initial type of the field.

Here are a couple of object example outputs:

1.  `{{user.name}}` This example results in a string.
    
2.  `{{item.active}}` This example results in a Boolean and it is not converted to a string.
    

### Tags

Tags which do not resolve to text are surrounded by a matched pair of curly braces and percent signs `{%` and `%}`. They are used for logic operations and control flow for templates.

`{% if res10.supplierId != blank %}Updated by {% endif %}`

> Note: The text surrounded by the curly brace percentage delimiters has no visible output when the template is rendered.

### Filters

Filters change the output of a Liquid JS object or variable. They are used within double curly braces `{{}}` and variable assignment, and are separated by a pipe character `|`, for example:

`{{ user.name | upcase }}`

## App Studio quick tips

___

App Studio allows templating in Liquid JS. Templating term refers to using Liquid JS language to render dynamic content in the end-user app.

> ⚠️ Warning: Incorrect use of Liquid JS language might produce blank fields and cells in the end-user app. Be sure to check your Liquid JS syntax if this happens.

In this section you can find quick tips for:

-   [Adding rules to trigger component properties](https://docs-external.u4pp.com/extensions-kit/app-studio/templating-and-liquid/liquid-support/#add-rules-to-trigger-properties), like _Hidden_ or _Read only_.
-   [**Data grid** component.](https://docs-external.u4pp.com/extensions-kit/app-studio/templating-and-liquid/liquid-support/#data-grid-component)
-   [Adding a filter to a component.](https://docs-external.u4pp.com/extensions-kit/app-studio/templating-and-liquid/liquid-support/#add-a-filter-to-a-component)
-   [Avoiding unwanted line breaks.](https://docs-external.u4pp.com/extensions-kit/app-studio/templating-and-liquid/liquid-support/#avoid-unwanted-line-breaks)
-   [Using tags to display a message.](https://docs-external.u4pp.com/extensions-kit/app-studio/templating-and-liquid/liquid-support/#use-tags-to-display-a-message)

### Add rules to trigger properties

___

The **Properties** section of a component allows you to set rules to trigger some of the properties, such as _Hidden_, _Disabled_ or _Read only_ **Interactions** or the _Required field_ **Validation**.

Here is a quick tip to set any of them using _Read only_ as an example:

1.  Go to the **Interactions** section in your component. This example uses the **Select** component.
2.  Select the _Read only_ checkbox.
3.  Enter the Liquid JS code `{{checkbox1.value == true}}` in the _Rule_ field, where `checkbox1` is the _Component ID_ of the component that will trigger the property, in this case the **Checkbox** component.

In this example the component will be _Read only_ only when the rule is fulfilled. Now, when the **Checkbox** component value matches the rule (in this case, when the checkbox is selected), the rule returns as valid (true). This triggers the rule, setting the component to _Read only_, in this example a **Select** component.

![Read only rule example](https://docs-external.u4pp.com/extensions-kit/app-studio/images/qtrules2.png)

### **Data grid** component

___

You can use Liquid JS to use data from your resources or to use data from your components.

**Get specific data from the** Data grid **component**

Here is a quick tip if the data you need is a specific cell value of the **Data grid** component:

1.  Enter `{{dataGridId.rows[3].columnID}}` in the component field.
    
    -   `dataGridId` specifies the table that you want to retrieve data from and is the _Component ID_ of the **Data grid** component.
        
    -   `rows[3]` specifies the row within the table, where the number corresponds to the array position. Note that in Liquid JS arrays, counting starts from 0.
        
    -   `columnID` specifies the column of the **Data grid** component and is the _Column ID_ of the column.
        

**Get all data from the** Data grid **component**

Here is a quick tip if you want to get all the data from your **Data grid** component in JSON format:

1.  Enter `{{dataGridId.rows | json}}` in the component field.
    
    -   `dataGridId` specifies the table that you want to retrieve data from and is the _Component ID_ of the **Data grid** component.
        
    -   `rows` all the rows from the **Data grid** component.
        
    -   `json` specifies the format in which you want to retrieve the data.
        

**POST the** Data grid **component data using the** HTTP **resource**

Here is a quick tip to serialise the data of your **Data grid** component to send them in JSON format:

1.  Go to your **HTTP** resource.
    
2.  Enter `{{dataGridId.rows | json}}` in the _Content definition_ (following JSON format).
    
    -   `dataGridId` specifies the table that you want to retrieve data from and is the _Component ID_ of the **Data grid** component.
        
    -   `rows` all the rows from the **Data grid** component. You can select other options like `deletedrows`.
        
    -   `json` specifies the format in which you want to retrieve the data.
        

See the [send complex request bodies with Liquid JS templating](https://docs-external.u4pp.com/extensions-kit/app-studio/tutorials/tutorial-send-complex-request-body-with-liquid/) tutorial for a more complex use case.

**Do operations between the properties of the resource in non-editable tables in the** Data Grid **component**

Here is a quick tip if you want to have a column that shows the result of an operation between two properties of the **Data grid** component's resource:

1.  Open the **Column** menu of the column you want to show the result.
    
2.  To multiply the value of two properties, enter `{{propertyName | times:propertyName}}` in the _Column data_ field.
    
    -   `propertyName` specifies which properties of the resource array we want to use for the operation. Typically, the value entered in the _Column data_ field of each row that we want to operate with. For example, `{{Price | times:Qty}}`. You can use the **Templating** drop-down to search for the properties.

To see what operations you can perform, see [Liquid JS filters](https://liquidjs.com/filters/overview.html).

**Do operations with columns in the Data grid component**

Here is a quick tip if you want to have a column that shows the result of operations between two columns or resources in the **Data grid** component:

1.  Open the **Column** menu of the column you want to show the result.
    
2.  Select the **Dynamic calculation** checkbox.
    
3.  Enter the Liquid JS formula in the _Formula_ field. For example, to multiply two values, enter `{{colData.col1 | times: resData.quantity}}`.
    
    -   `colData.col1` specifies the column with the value for the operation. You can use the **Templating** drop-down to search for the columns under the **Column data** entry.
    -   `resData.quantity` specifies the property of the resource we want to use for the operation. You can use the **Templating** drop-down to search for the properties of the resource under the **Resource data** entry.

You can do operations between two column data or two properties of the resource as well. To see what operations you can perform, see [Liquid JS filters](https://liquidjs.com/filters/overview.html).

### Add a filter to a component

___

Here is a quick tip if you want to filter data from an array in your resources. This example has two components, where the second component filters data according to the value of the first.

1.  Enter `{{res1 | where: 'propertyName', my1Component.value}}` in the field of your second component.
    
    -   `res1` specifies the resource array that you want to filter data from and is the default name given to the resource.
        
    -   `propertyName` specifies in which property from the resource array we want to filter.
        
    -   `my1Component.value` is the value we want to filter, where `my1Component` is the _Component ID_ of the first component.
        

### Avoid unwanted line breaks

___

Here is a quick tip to avoid unwanted line breaks caused by indentation in your Liquid JS formula.

There are three ways to avoid them:

1.  Write the formula in one line.
2.  Use hyphens in your tag syntax to eliminate left and right whitespaces. For example: `{% assign currentYear= "now" | date: "%Y" -%}` This will eliminate the right whitespace. See [Liquid JS documentation](https://liquidjs.com/tutorials/whitespace-control.html#sidebar) for more details.
3.  Use the filter `| strip_newlines`. See [Liquid JS documentation](https://liquidjs.com/filters/strip_newlines.html) for more details.

### Use tags to display a message

___

Here is a quick tip if you want to use a Liquid JS tag to display a message.

-   If Supplier is **not selected** (blank) no information is displayed.
-   If a Supplier **is selected** (not blank) the message appears (updated by). Also, for this example a filter to format the date is used.

`{% if res10.supplierId != blank %}Updated by {% endif %}`

`{% if res10.supplierId != blank %}{res10.lastUpdated.updatedBy}{% endif %}`

`{% if res10.supplierId != blank %}, {res10.lastUpdated.updatedAt | date: "%m/%d/%Y %H:%M" } (User time zone) {% endif %}`

![Example app with Liquid JS Tag and Filter](https://docs-external.u4pp.com/extensions-kit/app-studio/images/Liquid-Example1.png)

and here is a preview of the end-user app:

![App Preview with Liquid JS Tag and Filter](https://docs-external.u4pp.com/extensions-kit/app-studio/images/Liquid-Example2.gif)
