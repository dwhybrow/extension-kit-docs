The **Panel with stepper** component guides you through a series of steps in a structured and sequential manner. Each step represents a stage in a process.

You can add components to a panel in each step. Use the **Previous** and **Next** buttons to navigate through them.

## Example

You can use the **Panel with stepper** component to create an app where the user must follow certain steps to request a new expense. In this example:

-   Users select the type of expense.
-   Users add additional information and/or attach documents.
-   Users upload the information.

![Panel with Stepper component](https://docs-external.u4pp.com/extensions-kit/app-studio/images/ripple/stepper-ripple.png)

> Note: The **Panel with stepper** component follows [the WCAG 2.0 AA accessibility guidelines](https://www.w3.org/).

## Properties

The following **Panel with stepper** component properties are available:

### Main properties

The following table describes the main properties of the component.

|**Property**|**Description**|**Required**|
|---|---|---|
|_Title_|Enter the text you want as the heading.|Yes|
|_Subtitle_|Enter the text you want to display below the _Title_.|No|
|_Icon before_|Select an icon or type to search. This displays to the left of the _Title_.|No|
|_Icon after_|Select an icon or type to search. This displays to the right of the _Title_.|No|

### Styles properties

The following table describes the styles properties of the component.

|**Property**|**Description**|**Required**|
|---|---|---|
|_Background color_|Select a background color for the container from the drop-down.|No|
|_Variant_|Select the appearance.|No|
|_Content size_|Select the size from the drop-down menu.|No|
|_Hide border_|Turn on to hide the border.|No|

### Navigation buttons properties

The following table describes the navigation buttons properties of the component.

|**Property**|**Description**|**Required**|
|---|---|---|
|_Previous button text_|Enter the text to display in the button.|Yes|
|_Next button text_|Enter the text to display in the button.|Yes|
|_Finish button text_|Enter the text to display in the button.|Yes|

### Steps properties

You can:

-   Add steps using the **Plus (+)** button next to menu header.
-   Rearrange the steps using the arrows in each Step header.
-   Delete the steps using the **Delete step** button in the bottom corner of each **Steps** menu.

![Steps](https://docs-external.u4pp.com/extensions-kit/app-studio/images/ripple/steps-ripple3.png)

The following table describes the steps properties of the component.

|**Property**|**Description**|**Required**|
|---|---|---|
|_Step title_|Enter the text you want as the text heading.|Yes|
|_Step description_|Enter the text you want to display below the _Title_.|No|
|_Substep_|Turn on to make the step a substep of the previous step. Not available for the first step.|No|
|_Step hidden_|Select the checkbox to hide the step in the end-user app.|No|
|_Add rule_|You can set rules to hide the step using Liquid JS. If no rules are set, the step will be hidden in all instances.|No|
|_Step disabled_|Select the checkbox to disable the step in the end-user app.|No|
|_Add rule_|You can set rules to disable the step using Liquid JS. If no rules are set, the step will be disabled in all instances.|No|

### Interactions properties

The following table describes the interactions properties of the component.

|**Property**|**Description**|**Required**|
|---|---|---|
|_Hidden_|Select the checkbox to hide the component in the end-user app. To hide it in the canvas, use the eye icon in the _Layers_ panel.|No|
|_Add rule_|You can set rules to hide the component using Liquid JS. If no rules are set, the component will be hidden in all instances.|No|

> Note: See [Add rules to trigger properties](https://docs-external.u4pp.com/extensions-kit/app-studio/templating-and-liquid/liquid-support/#add-rules-to-trigger-properties) for more information on setting rules for these properties.

## Events

The **Panel with stepper** component supports the **On finish** event. See [Logic drawer](https://docs-external.u4pp.com/extensions-kit/app-studio/logic/logic-drawer/#actions) for more details.

![Panel with stepper logic map](https://docs-external.u4pp.com/extensions-kit/app-studio/images/ripple/stepper-logicmap-ripple.png)

> Note: You must have the component selected on the canvas to see the **Logic map** tab.
