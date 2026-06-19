## Working with components

The drag-and-drop elements of App Studio are arranged in two panels:

1.  **Layout** panel: This panel groups all the elements that help you design the layout of your app. It is recommended to use these elements to contain all the functional components. Drag a **Layout** component to the **Canvas viewport**, then drag components inside it. This practice will allow you to align all your app elements effectively. The available **Layout** components are:
    
    -   **Container**: The basic layout building block used to align content in a grid.
    -   **Panel**, **Panel with tabs** and **Panel with stepper**: Advanced layout components for more complex configurations and functionality.
2.  **Components** panel: This panel groups all the elements with functionality. The **Magnifying-glass icon** button allows you to search components by name. Read each component's documentation for configuration details and tips.
    

> Note: The **Layers** panel allows you to see and rearrange the component's hierarchy.

## Component toolbar

![Component toolbar](https://docs-external.u4pp.com/extensions-kit/app-studio/images/componenttoolbar.png)

When you select a component in the **Canvas viewport**, a component toolbar is available with the following options:

-   **Drag**: Select and move an element while holding it.
-   **Select parent component**: Select the component that contains this component.
-   **Delete**: Delete the selected component.
-   **Clone**: Copy the selected component and its configuration.

> Note: The **Component toolbar** displays an _Eye_ icon when an **Interaction** property is set to _Disabled_ or _Read only_ and an _Eye slash_ icon for _Hidden_.

## Templating in components

The templating term refers to using Liquid JS template language to render dynamic content in the end-user app.

The _Component ID_ allows you to use the data from that component using Liquid JS. You can enter Liquid JS formulas in the fields or use the **Plus (+)** button to display the **Templating** drop-down. See [Templating drop-down](https://docs-external.u4pp.com/extensions-kit/app-studio/templating-and-liquid/templating-dropdown/) for more details.

The _Component ID_ is automatically generated every time you add a component following the pattern:

`[componentName][counter]`

The counter is incremented for each new component added, for example, `[textInput4]`, `[dropdown2]`.

> Note: _Component ID_ is not case sensitive.

A component's input is accessible using `.value`, for example using the Liquid JS formula `{{textInput12.value}}` or selecting it from the **Templating** drop-down.

If the _Component ID_ is changed in the _Component ID_ field in the **Main** properties section, all references are automatically updated in all places where templating is allowed.

The following fields used in the components below do not get automatically updated since they depend on the resource selected in the _Options_ field and not on the _Component ID_:

-   **Dropdown** component: _Display field_, _Value field_.
-   **Combobox** component: _Display field_, _Value field_.
-   **Radio** component: _Display field_, _Value field_.

It is recommended to enter a meaningful name in the _Component ID_ and you cannot use an already existing name.

> Note: The **Container**, **Panel**, **Panel with tabs**, **Panel with stepper**, **Image**, **Icon**, **Link**, **Text** and **Divider** components do not have a _Component ID_.

## Ripple components

New apps use the **Ripple** design system. The following components are available:

### Layout components

|**Component**|**Description**|
|---|---|
|[Container](https://docs-external.u4pp.com/extensions-kit/app-studio/components/container-ripple/)|The basic layout building block. Arrange content using columns inside it.|
|[Panel](https://docs-external.u4pp.com/extensions-kit/app-studio/components/panel-ripple/)|An advanced layout component for grouping content in a collapsible section.|
|[Panel with tabs](https://docs-external.u4pp.com/extensions-kit/app-studio/components/panel-with-tabs-ripple/)|An advanced layout component for organising content in tabs.|
|[Panel with stepper](https://docs-external.u4pp.com/extensions-kit/app-studio/components/stepper-ripple/)|An advanced layout component for organising content in sequential steps.|
|[Stacked list](https://docs-external.u4pp.com/extensions-kit/app-studio/components/components-overview-ripple/stacked-list-ripple.md)|A layout component to render multiple instances of child components based on a data array. Only available for **System** apps.|
|[App container](https://docs-external.u4pp.com/extensions-kit/app-studio/components/components-overview-ripple/app-container-ripple.md)|A layout component to embed another app. Only available for **System** apps.|

### Components

|**Component**|**Description**|
|---|---|
|[Button](https://docs-external.u4pp.com/extensions-kit/app-studio/components/button-ripple/)|Triggers an action when selected.|
|[Charts](https://docs-external.u4pp.com/extensions-kit/app-studio/components/charts-ripple/)|Displays data as a chart.|
|[Checkbox](https://docs-external.u4pp.com/extensions-kit/app-studio/components/checkbox-ripple/)|Allows users to select one or more options.|
|[Combobox](https://docs-external.u4pp.com/extensions-kit/app-studio/components/combobox-ripple/)|Allows users to select an option from a searchable list.|
|[Data grid](https://docs-external.u4pp.com/extensions-kit/app-studio/components/data-grid-ripple/)|Displays and allows editing of tabular data.|
|[Divider](https://docs-external.u4pp.com/extensions-kit/app-studio/components/divider-ripple/)|A horizontal or vertical line to separate content.|
|[Drawing area](https://docs-external.u4pp.com/extensions-kit/app-studio/components/drawing-area-ripple/)|Allows users to draw and attach sketches.|
|[Dropdown](https://docs-external.u4pp.com/extensions-kit/app-studio/components/dropdown-ripple/)|Allows users to select an option from a list.|
|[File uploader](https://docs-external.u4pp.com/extensions-kit/app-studio/components/file-uploader-ripple/)|Allows users to upload files.|
|[File viewer](https://docs-external.u4pp.com/extensions-kit/app-studio/components/file-viewer-ripple/)|Displays a file inline in the app.|
|[Icon](https://docs-external.u4pp.com/extensions-kit/app-studio/components/icon-ripple/)|Displays an icon.|
|[Image](https://docs-external.u4pp.com/extensions-kit/app-studio/components/image-ripple/)|Displays an image.|
|[Link](https://docs-external.u4pp.com/extensions-kit/app-studio/components/link-ripple/)|Displays a selectable hyperlink.|
|[Radio](https://docs-external.u4pp.com/extensions-kit/app-studio/components/radio-ripple/)|Allows users to select a single option from a group.|
|[Range](https://docs-external.u4pp.com/extensions-kit/app-studio/components/range-ripple/)|Allows users to select a value within a range.|
|[Root](https://docs-external.u4pp.com/extensions-kit/app-studio/components/root-ripple/)|The root layout element of the app window.|
|[Switch](https://docs-external.u4pp.com/extensions-kit/app-studio/components/switch-ripple/)|Allows users to toggle a boolean value.|
|[Text](https://docs-external.u4pp.com/extensions-kit/app-studio/components/text-ripple/)|Displays static or dynamic text.|
|[Text area](https://docs-external.u4pp.com/extensions-kit/app-studio/components/text-area-ripple/)|Allows users to enter multi-line text.|
|[Text input](https://docs-external.u4pp.com/extensions-kit/app-studio/components/text-input-ripple/)|Allows users to enter single-line text.|

> Note: See [how to edit an app](https://docs-external.u4pp.com/extensions-kit/app-studio/get-started/how-to-edit-app-ripple/) for more details on working with Ripple components.
