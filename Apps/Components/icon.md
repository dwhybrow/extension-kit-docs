The **Icon** component allows users to use visual symbols to represent ideas, objects, or actions.

## Example

You can use the **Icon** component to add extra visual information for your components. For example, in this app:

-   Users can add the date their holiday starts.

![Icon component](https://docs-external.u4pp.com/extensions-kit/app-studio/images/ripple/iconripplecomponent.png)

> Note: The **Icon** component follows [the WCAG 2.0 AA accessibility guidelines](https://www.w3.org/).

## Properties

The following **Icon** component properties are available:

### Main properties

The following table describes the main properties of the component.

|**Property**|**Description**|**Required**|
|---|---|---|
|_Component ID_|Enter a unique name for the component. See [Templating in components](https://docs-external.u4pp.com/extensions-kit/app-studio/components/components-overview-ripple/#templating-in-components) for more details.|Yes|
|_Icon_|Select the icon from the drop-down menu. You can also type to search.|Yes|

### Styles properties

The following table describes the styles properties of the component.

|**Property**|**Description**|**Required**|
|---|---|---|
|_Color_|Select a colour from the drop-down menu.|No|
|_Style_|Select a style from the drop-down menu.|No|
|_Size_|Select a size from the drop-down menu.|No|

### Interactions properties

The following table describes the interactions properties of the component.

|**Property**|**Description**|**Required**|
|---|---|---|
|_Hidden_|Select the checkbox to hide the component in the end-user app. To hide it in the canvas, use the eye icon in the _Layers_ panel.|No|
|_Add rule_|You can set rules to hide the component using Liquid JS. If no rules are set, the component will be hidden in all instances.|No|

> Note: See [Add rules to trigger properties](https://docs-external.u4pp.com/extensions-kit/app-studio/templating-and-liquid/liquid-support/#add-rules-to-trigger-properties) for more information on setting rules for these properties.

### Accessibility properties

The following table describes the accessibility properties of the component.

|**Property**|**Description**|**Required**|
|---|---|---|
|_Aria label_|Enter a text that allows assistive technology to attach a label to the component.|No|
|_Title_|Enter a text that is displayed as a tooltip when hovering the mouse over the component in the end-user app.|No|
