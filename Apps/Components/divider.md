## Horizonal and vertical divider

The **Horizontal divider** and **Vertical divider** components allow you to organize and structure the layout of your app.

-   Use the **Horizontal divider** component to create a visual separation between sections stacked vertically on the window.
-   Use the **Vertical divider** component to break up the window visually into columns, which is useful when you want to display content side-by-side.

## Example

You can use the **Horizontal** and **Vertical divider** components to clearly delineate and create visual separation between sections, making the layout cleaner.

![Divider component](https://docs-external.u4pp.com/extensions-kit/app-studio/images/ripple/divider-ripple2.png)

> Note: The **Horizontal** and **Vertical divider** components follow [the WCAG 2.0 AA accessibility guidelines](https://www.w3.org/).

## Horizontal divider properties

The following **Horizontal divider** component properties are available:

### Main properties

The following table describes the main properties of the component.

|**Property**|**Description**|**Required**|
|---|---|---|
|_Inset_|Turn on to change the divider from full width to inset. Inset dividers have rounded edges and are indented from the sides.|No|
|_Text_|Enter a text for the divider. Only available when _Inset_ is active.|No|

### Styles properties

The following table describes the styles properties of the component.

|**Property**|**Description**|**Required**|
|---|---|---|
|_Size_|Choose the amount of vertical space (margin) added above and below the divider line from the drop-down menu.|No|

### Interactions properties

The following table describes the interactions properties of the component.

|**Property**|**Description**|**Required**|
|---|---|---|
|_Hidden_|Select the checkbox to hide the component in the end-user app. To hide it in the canvas, use the eye icon in the _Layers_ panel.|No|
|_Add rule_|You can set rules to hide the component using Liquid JS. If no rules are set, the component will be hidden in all instances.|No|

> Note: See [Add rules to trigger properties](https://docs-external.u4pp.com/extensions-kit/app-studio/templating-and-liquid/liquid-support/#add-rules-to-trigger-properties) for more information on setting rules for these properties.

## Vertical divider properties

The **Vertical divider** component can be only dropped inside **Containers** between columns. The following component properties are available:

### Main properties

The following table describes the main properties of the component.

|**Property**|**Description**|**Required**|
|---|---|---|
|_Inset_|Turn on to change the divider from full width to inset. Inset dividers have rounded edges and are indented from the sides.|No|
|_Text_|Enter a text for the divider. Only available when _Inset_ is active.|No|

### Interactions properties

The following table describes the interactions properties of the component.

|**Property**|**Description**|**Required**|
|---|---|---|
|_Hidden_|Select the checkbox to hide the component in the end-user app. To hide it in the canvas, use the eye icon in the _Layers_ panel.|No|
|_Add rule_|You can set rules to hide the component using Liquid JS. If no rules are set, the component will be hidden in all instances.|No|

> Note: See [Add rules to trigger properties](https://docs-external.u4pp.com/extensions-kit/app-studio/templating-and-liquid/liquid-support/#add-rules-to-trigger-properties) for more information on setting rules for these properties.
