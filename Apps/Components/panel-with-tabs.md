The **Panel with tabs** component allows you to present content to your users in a clear and structured way using different tabs to organize your content and a stable layout.

The user can use the tabs to navigate to the different content, tabs are always available, but only the content of the selected one will be in display.

## Example

You can use the **Panel with tabs** component to create an **Absence request** window with information organized thematically in different tabs, making it is easier for the user to fill in.

![Panel with tabs component](https://docs-external.u4pp.com/extensions-kit/app-studio/images/ripple/tabsripplecomponent.png)

> Note: The **Panel with tabs** component follows the [WCAG 2.0 AA accessibility guidelines](https://www.w3.org/).

## Properties

The following **Panel with Tabs** component properties are available:

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
|_Tab variant_|Select the appearance from the drop-down menu.|No|
|_Content size_|Select the size from the drop-down menu.|No|
|_Hide footer_|Turn on to hide the footer.|No|
|_Hide border_|Turn on to hide the border.|No|

### Tabs properties

You can:

-   Add tabs using the **Plus (+)** button next to menu header.
-   Rearrange tabs using the arrows in each Tab header.
-   Delete the tabs using the **Delete tab** button in the bottom corner of each Tabs menu.

![Tabs menu](https://docs-external.u4pp.com/extensions-kit/app-studio/images/Hidden-Disabled-Tabs.png)

The following table describes the tabs properties of the component.

|**Property**|**Description**|**Required**|
|---|---|---|
|_Tab title_|Enter the text for the tab to display.|Yes|
|_Tab icon_|Select an icon or type to search. This displays to the left of the _Tab title_. Only available if _Tabs icon_ property is turned on in the **Main** menu.|No|
|_Tab hidden_|Select the checkbox to hide the tab in the end-user app.|No|
|_Add rule_|You can set rules to hide the tab using Liquid JS. If no rules are set, the tab will be hidden in all instances.|No|
|_Tab disabled_|Select the checkbox to disable the tab in the end-user app.|No|
|_Add rule_|You can set rules to disable the tab using Liquid JS. If no rules are set, the tab will be disabled in all instances.|No|

### Interactions properties

The following table describes the interactions properties of the component.

|**Property**|**Description**|**Required**|
|---|---|---|
|_Hidden_|Select the checkbox to hide the component in the end-user app. To hide it in the canvas, use the eye icon in the _Layers_ panel.|No|
|_Add rule_|You can set rules to hide the component using Liquid JS. If no rules are set, the component will be hidden in all instances.|No|

> Note: See [Add rules to trigger properties](https://docs-external.u4pp.com/extensions-kit/app-studio/templating-and-liquid/liquid-support/#add-rules-to-trigger-properties) for more information on setting rules for these properties.
