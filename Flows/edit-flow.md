# Edit a flow

## Flow editor

You can edit an existing flow by selecting the flow from the list of flows shown in the **Flow overview**.

![Image 8: Flow overview section](https://docs-external.u4pp.com/extensions-kit/images/portal/home-edit-1.png)

This opens the **Flow editor** where you can see:

*   The **Flow roadmap** to the left, where you can see the trigger and all the actions of your flows as well as the **Overview** and the **History** buttons.
*   The **Dynamic** section to the right, where you can see the properties of the trigger or the action selected or the overview and history information.
*   The **Bottom** toolbar with the following elements:
    *   The **Save flow** button: Save changes made on the flow.
    *   The **Delete** button: Delete the flow from the system.
    *   The **Cancel** button: Cancel the editing.
    *   The **More** button:

        *   **Clone**: Create a new flow based on the one you are currently editing. 

> Note: For security reasons, all sensitive data used in the trigger and action configurations, such as _Passwords_ and _Passphrases_, are removed from the cloned flow. In some cases, this data is optional. It is recommended to verify each individual configuration and reintroduce any required data.

        *   **Export as JSON file**: Export your flow as a JSON file that includes the definition of the flow along with the parameters found on it. See [Export Flow as JSON](https://docs-external.u4pp.com/extensions-kit/guides/portal/import-export-v2/) for more details.
        *   **Export as an App**: Exports the flow as an app to allow it to be reused by system administrators to be installed as a **Marketplace** flow. See [Export Flow as an App](https://docs-external.u4pp.com/extensions-kit/guides/portal/import-export-v2/#export-flow-as-an-app) for more details.

> Note: You can also perform these actions in the **Three dots menu** in the **Flow card** of each flow.

![Image 9: Flow editor](https://docs-external.u4pp.com/extensions-kit/images/portal/edit-flow.png)

## Edit triggers

To edit a trigger, select the **Trigger** node in the **Flow roadmap** to be able to view and edit all the properties in the **Dynamic** section to the right.

### Trigger toolbar

The **Trigger** configuration section has a toolbar with the following components:

![Image 10: Trigger configuration toolbar](https://docs-external.u4pp.com/extensions-kit/images/portal/trigger-toolbar.png)

1.   **Trigger** name: Name of the selected trigger.
2.   **Help** button: Select to open documentation in another tab.
3.   **Change** button: Select to change the trigger type.

## Edit actions

To edit an action, select the **Action** node in the **Flow roadmap** to be able to view and edit all properties in the **Dynamic** section to the right.

![Image 11: Edit action](https://docs-external.u4pp.com/extensions-kit/images/portal/edit-action.png)

### Action toolbar

The **Action** configuration section has a toolbar with the following components:

![Image 12: Action configuration toolbar](https://docs-external.u4pp.com/extensions-kit/images/portal/action-configuration-toolbar.png)

1.   **Action** name: Name of the selected action.
2.   **Help** button: Select to open documentation in another tab.
3.   **Clone** button: Select to create a copy of your action that will be added at the end of the flow. The action configuration will be copied.

> Note: If you use the **Clone** button on the **For Each** or **Until** actions, all sub-actions will also be cloned.

4.   **Change** button: Select to choose another action from the action list. The new action won't have any of the previous action configuration.

5.   **Delete** button: Select to directly delete the action. Not available for the first action of the flow and the loop.
6.   **Gear icon** button: Select to open the actions settings. Select the **Continue on error** checkbox if you want the flow to continue its execution even if this action fails. You can enter an optional custom error message. The [**Flow history**](https://docs-external.u4pp.com/extensions-kit/guides/portal/flow-history/) shows any actions that failed and the flow continued to run.
> Note: The **Continue on error** checkbox is not available for the **For each**, **Pause**, **Stop Execution** and **Until** actions.

### Rename an action

When you add a new action, a default name is set. To change it:

*   Select the name.
*   Enter the custom name.
*   Select **Save flow** to save the changes.

The custom labels are then displayed in the **Overview** section.

### Rearrange actions

You can rearrange the order of the flow by rearranging actions:

*   Select the **Action** node on the flow roadmap.
*   Drag it to its new position in the roadmap. 

To automatically renumber the flow steps when rearranging them, you must turn on the **Automatic steps renumbering** toggle in the [**Overview** section](https://docs-external.u4pp.com/extensions-kit/guides/portal/create-a-flow/#overview-section).

Once on, step numbers will be automatically updated when you rearrange actions in the **Flow roadmap**. If you are using templating, that is, if you are using any step outputs as other step inputs, they will automatically update as long as the execution order is not affected.

> ⚠️ Warning: If the execution order is affected and you need to manually update the steps, a warning will appear.

![Image 13: Action warning](https://docs-external.u4pp.com/extensions-kit/images/portal/action-warning2.png)
