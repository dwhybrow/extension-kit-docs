The **Button** component is an interactive element that allows you to:

-   Trigger actions or events when selected. See [Logic drawer](https://docs-external.u4pp.com/extensions-kit/app-studio/logic/logic-drawer.md#actions) and the [**Events**](https://docs-external.u4pp.com/extensions-kit/app-studio/components/button-ripple/#events) section for more details.
-   Take the user to another URL.

Buttons are an important feature for the user experience:

-   Use buttons to communicate to the user the available actions.
-   Use buttons to allow users to interact with the page.
-   Use the variants and colours to communicate to the user the importance and category of each of the actions.

## Example

You can use the **Button** component to trigger a flow that allows you to get the user ID with the email. See [How to trigger a flow from App Studio](https://docs-external.u4pp.com/extensions-kit/app-studio/tutorials/tutorial-U4C-trigger-a-flow-from-AS/) for more details.

![Button component](https://docs-external.u4pp.com/extensions-kit/app-studio/images/buttontriggerflow3.png)

> Note: The **Button** component follows [the WCAG 2.0 AA accessibility guidelines](https://www.w3.org/).

## Properties

The following **Button** component properties are available:

### Main properties

The following table describes the main properties of the component.

|**Property**|**Description**|**Required**|
|---|---|---|
|_Component ID_|Enter a unique name for the component. See [Templating in components](https://docs-external.u4pp.com/extensions-kit/app-studio/components/components-overview-ripple/#templating-in-components) for more details.|Yes|
|_Text_|Enter the name you want to be displayed inside the button.|Yes|

> Note: See [Templating drop-down](https://docs-external.u4pp.com/extensions-kit/app-studio/templating-and-liquid/templating-dropdown/) for more details on rendering dynamic content using Liquid JS.

### Styles properties

The following table describes the styles properties of the component.

|**Property**|**Description**|**Required**|
|---|---|---|
|_Size_|Select the size.|Yes|
|_Variant_|Select the appearance.|Yes|
|_Color_|Select the colour for the chosen variant.|Yes|
|_Icon before_|Select an icon from the drop-down. It displays to the left of the text.|No|
|_Icon after_|Select an icon from the drop-down. It displays to the right of the text.|No|
|_Hyperlink_|Add a URL. It opens in a new tab.|No|

> Note: The _Align_ property in **Columns** is set to _Stretch_ by default, so the component will take all the available width. To change that, set the _Align_ property to _Left_, _Center_ or _Right_.

### Interactions properties

The following table describes the interactions properties of the component.

|**Property**|**Description**|**Required**|
|---|---|---|
|_Hidden_|Select the checkbox to hide the component in the end-user app. To hide it in the canvas, use the eye icon in the _Layers_ panel.|No|
|_Add rule_|You can set rules to hide the component using Liquid JS. If no rules are set, the component will be hidden in all instances.|No|
|_Disabled_|Select the checkbox to disable the component in the end-user app.|No|
|_Add rule_|You can set rules to disable the component using Liquid JS. If no rules are set, the component will be disabled in all instances.|No|

> Note: See [Add rules to trigger properties](https://docs-external.u4pp.com/extensions-kit/app-studio/templating-and-liquid/liquid-support/#add-rules-to-trigger-properties) for more information on setting rules for these properties.

### Accessibility properties

The following table describes the accessibility properties of the component.

|**Property**|**Description**|**Required**|
|---|---|---|
|_Aria label_|Enter a text that allows assistive technology to attach a label to the component.|No|
|_Title_|Enter a text that is displayed as a tooltip when hovering the mouse over the component in the end-user app.|No|

## Events

The **Button** component supports the **On click** event. See [Logic drawer](https://docs-external.u4pp.com/extensions-kit/app-studio/logic/logic-drawer/#actions) for more details.
