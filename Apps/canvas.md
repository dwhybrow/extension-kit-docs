## Overview

The **Canvas** is where you design and edit your apps. It contains the following elements:

1.  Main toolbar
2.  Canvas toolbar
3.  Canvas viewport
4.  Layers
5.  Layout
6.  Components
7.  Properties
8.  Logic map

![App Studio overview](https://docs-external.u4pp.com/extensions-kit/app-studio/images/canvasoverview3.png)

## 1\. Main toolbar

![Main toolbar](https://docs-external.u4pp.com/extensions-kit/app-studio/images/maintoolbar2.png)

The main toolbar allows you to:

1.  Return to the App Studio dashboard.
2.  Edit the app's name.
3.  Switch between the **Canvas**, [**Resources**](https://docs-external.u4pp.com/extensions-kit/app-studio/resources/) and [**Logic flow**](https://docs-external.u4pp.com/extensions-kit/app-studio/logic/logic-flow/) tabs when creating your app.
4.  See warnings and error messages in the **Notification** panel. ![Notification panel](https://docs-external.u4pp.com/extensions-kit/app-studio/images/notificationpanel2.png)
5.  Add or delete query parameters in the **Query parameters** panel. Query parameters are used to pass data to the app when it is opened. See [Query parameters](https://docs-external.u4pp.com/extensions-kit/app-studio/templating-and-liquid/templating-dropdown/) and [using query parameters in App Studio tutorial](https://docs-external.u4pp.com/extensions-kit/app-studio/tutorials/tutorial-query-parameters/) for more details. ![Query parameters panel](https://docs-external.u4pp.com/extensions-kit/app-studio/images/queryparameters-panel.png)
6.  Import an app in JSON format and export the current app as a JSON file.
    
    > Note: You cannot import U4 components apps to a Ripple **Canvas**. To import U4 components apps, you must use the **Import app** button in the **Dashboard**
    
7.  Save your app as a draft.
8.  Preview your app. Previewed apps last for 30 minutes.
    
    > Note: If the preview does not open in a new tab after a few seconds, you might have the block pop-ups feature turned on in your browser. Allow pop-ups to fix the issue.
    
9.  Publish the current app.
    
10.  Manage credentials.

## 2\. Canvas toolbar

![Toolbar functions](https://docs-external.u4pp.com/extensions-kit/app-studio/images/canvastoolbar4.png)

You can use the **Canvas** toolbar to:

1.  See how your app renders when running on different device sizes (desktop, laptop, tablet and mobile).
2.  Resize the **Canvas viewport** and reset the size back to 100%.
3.  Turn on/off the grid using the **Layout view** switch.
4.  Undo and redo your edits.

## 3\. Canvas viewport

You create and edit content on a canvas using the **Canvas viewport**. All associated panels and toolbars are placed around the editable area, which is in the centre of the page. You can drag components from the **Layout** and **Components** panels onto the viewport and arrange them as required.

## 4\. Layers

The **Layers** panel shows the components used in your app and how they are structured. You can:

-   Select a component in the **Layers** panel. The component gets highlighted on the **Canvas viewport** and its properties become available in the **Properties** panel.
-   Rearrange components using drag-and-drop to move them along the **Layers** panel. The **Canvas viewport** updates to show the new structure.
-   Hide the component in the **Canvas viewport** by selecting the _Eye_ icon.
-   Expand/collapse each layer group by selecting the _Chevron_ icon.
-   Delete components from **Layers** by pressing the **Backspace** key. The component is also deleted in the **Canvas viewport**.

![Example on how to use Layers](https://docs-external.u4pp.com/extensions-kit/app-studio/images/canvaslayers3.png)

## 5\. Layout

The **Layout** panel contains components specifically designed to help you structure and align content in your app. Drag these components to create your app. There are two categories of **Layout** components:

-   Basic **Layout** components used to align content in a grid: **Container**.
-   Advanced **Layout** components used to help with more advanced configurations and functionality: **Panel**, **Panel with tabs** and **Panel with stepper**.

> Note: See Ripple components and [how to edit an app](https://docs-external.u4pp.com/extensions-kit/app-studio/get-started/how-to-edit-app-ripple/) for more details.

## 6\. Components

The **Components** panel contains components with different functionalities. Drag these components to previously added **Layout** components in the **Canvas viewport** and define their properties and styles.

![Drag and drop component example](https://docs-external.u4pp.com/extensions-kit/app-studio/images/canvascomponents3.png)

> Note: See Ripple components and [how to edit an app](https://docs-external.u4pp.com/extensions-kit/app-studio/get-started/how-to-edit-app-ripple/) for more details.

## 7\. Properties

The **Properties** panel allows you to define how your components look and behave, how they show data and other information, and how they are connected to the app data. The **Properties** appear in the right panel when you select a component.

Component properties have the following categories:

-   [Main](https://docs-external.u4pp.com/extensions-kit/app-studio/canvas/#main)
-   [Styles](https://docs-external.u4pp.com/extensions-kit/app-studio/canvas/#styles)
-   [Validation](https://docs-external.u4pp.com/extensions-kit/app-studio/canvas/#validation)
-   [Interactions](https://docs-external.u4pp.com/extensions-kit/app-studio/canvas/#interactions)
-   [Accessibility](https://docs-external.u4pp.com/extensions-kit/app-studio/canvas/#accessibility)

> Note: Not all components share the same properties. Read each component's documentation for more details on their properties.

### Main properties

The **Main** properties define the _Component ID_ which can be used for templating (see [Templating dropdown](https://docs-external.u4pp.com/extensions-kit/app-studio/templating-and-liquid/templating-dropdown/)) and other properties that allow you to define which input data is required or is used to populate it. Read each component documentation for more details.

The fields can be expanded for editing.

![Main panel](https://docs-external.u4pp.com/extensions-kit/app-studio/images/fieldexpand.png)

### Styles properties

The **Styles** properties are used to define certain field attributes such as the height or width, if a switch is checked by default or which icon to display. Read each component documentation for more details.

![Styles panel](https://docs-external.u4pp.com/extensions-kit/app-studio/images/stylespanel.png)

### Validation properties

The **Validation** properties allow you to:

-   Set the component as required and add a rule to specify when the component is required.
-   Define validation rules for input fields based on common patterns.
-   Set additional validations rules for error, warning and informative conditions.
-   Enter messages for required fields and error, warning and informative conditions.

![Validation panel](https://docs-external.u4pp.com/extensions-kit/app-studio/images/validation-ripple.png)

> Note: See [Validation](https://docs-external.u4pp.com/extensions-kit/app-studio/logic/validation/) for more details on validation properties and see [add rules to trigger properties](https://docs-external.u4pp.com/extensions-kit/app-studio/templating-and-liquid/liquid-support/#add-rules-to-trigger-properties) for more details on setting rules to these properties.

### Interactions properties

The **Interactions** properties allow you to set to read only, hide or disable a component. You can also add rules to specify when a component is hidden, disabled, or read only. See [add rules to trigger properties](https://docs-external.u4pp.com/extensions-kit/app-studio/templating-and-liquid/liquid-support/#add-rules-to-trigger-properties) for more details.

The **Component toolbar** displays an _Eye_ icon when a component is set to disabled or read only and an _Eye slash_ icon for hidden.

![Interaction panel](https://docs-external.u4pp.com/extensions-kit/app-studio/images/interactiontoolbar.png)

> Note: If overlapping interactions occur, then the hierarchy is: _Hidden_ > _Disabled_ > _Read only_. For example, if a component is set as _Disabled_ and _Read only_ at the same time, then the component would only appear as _Disabled_.

### Accessibility properties

The **Accessibility** properties allow you to add certain HTML tags that are passed and attached directly to the source code of the app, to make your components more accessible. Read each component documentation for more details.

![Accessibility panel](https://docs-external.u4pp.com/extensions-kit/app-studio/images/accessibilitypanel.png)

## 8\. Logic map

The **Logic map** section is available in every component that supports events. See [logic drawer](https://docs-external.u4pp.com/extensions-kit/app-studio/logic/logic-drawer/) for more details.

The viewport has the controls Zoom in, Zoom out, Fit to content and Maximize.

![Logic map event and actions](https://docs-external.u4pp.com/extensions-kit/app-studio/images/logicmapcanvas.png)
