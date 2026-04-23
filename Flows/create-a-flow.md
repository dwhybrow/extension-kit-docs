# Create a flow

To create a flow, select the **New flow** button in the **Bottom** toolbar of the **Flow overview** section to open the **Flow editor**.

The **Flow editor** has two sections:

![Image 7: Flow editor](https://docs-external.u4pp.com/extensions-kit/images/portal/newflow3.png)

1.   The **Flow roadmap**: The section on the left defines the roadmap of the flow and has the following subsections:

| **Section** | **Description** |
| --- | --- |
| **Flow name** | Select the **Pencil** icon to enter the name of your flow. You must follow the [flow naming convention](https://docs-external.u4pp.com/extensions-kit/guides/portal/create-a-flow/#flow-naming-convention). This field is mandatory. |
| **Flow description** | Provide a meaningful description of the flow's purpose and functionality. This field is optional. |
| **Trigger** | To select and configure the trigger of the flow. |
| **Add filter** | Dynamic section, which you can optionally define, that allows you to stop a flow depending on the output of the previous step of the action associated to it. This way the flow will react to more specific events. |
| **Add condition** | Dynamic section, which you can optionally define, that allows you to conditionally skip the action it is associated with. |
| **Action** | To define what actions will follow a triggered event. The flow must contain at least one action. |
| **Overview** | Summary of the state of the flow. See the [**Overview** section](https://docs-external.u4pp.com/extensions-kit/guides/portal/create-a-flow/#overview-section) for more details. |

1.   The **Dynamic** section: The section on the right side dynamically changes depending on what you choose on the left, allowing you to enter values relevant only to the currently chosen element.

## Name your flow

To save your flow you must first name it. To name your flow:

1.   Go to the top of the **Flow roadmap** section.
2.   Select the **Pencil** icon.
3.   Enter the name of your flow following the flow naming convention.

> Note: You can only save a flow if the name, trigger and all actions are properly defined.

### Flow naming convention

You must follow the naming convention for the flows created in the **Preview** and **Production** environments as shown in the example below:

**[Owner]-[ShortName]-[Group]-[FlowName]-[FlowType]-[Version]**

| **Component** | **Description** | **Example** |
| --- | --- | --- |
| **Owner** | Identifier of the owner. | U4, if the flow was created by Unit4. |
| **ShortName** | Short name of the tenant ID given in the Portal. | ACME |
| **Group** | Logical grouping or module reference for related flows up to 6 characters. | HR, FIN, CRM, PRJ, SALES |
| **FlowName** | Short name of the **Trigger** or source. | **SE** - Scheduler Event, **MH** - Message Hub Event, **WH** - Webhook |
| **FlowType** | The domain object or function the flow relates to. | _employee_, if the flow uses the **Employee** object in the ERP public API. |
| **Version** | Current version of the flow. | v1, v2, etc. |

**Example**

U4-ACME-HRCRDN-SE-employee-v1

This represents a flow created by Unit4 (U4), for the ACME tenant, under the HRCRDN (HR – Business process, CRDN – Ceridian platform) grouping, triggered by a Scheduler Event (SE), related to the Employee object, version 1.

> Note: Only letters, numbers, spaces, dashes, underscores, periods, brackets, square brackets and ampersands are allowed.

## Trigger configuration

![Image 8: Add trigger](https://docs-external.u4pp.com/extensions-kit/images/portal/add-trigger-2.png)

The trigger defines what will start your flow. To create a new flow:

1.   Select the **Trigger** node in the **Flow roadmap** and the **Dynamic** section will show you all the triggers that you can add.

2.   Select the type of **Trigger** and then configure it by entering the relevant properties. These are dynamic and will differ according to the type of trigger you configure. Go to **Extensions**>**Triggers** to see all the available triggers and their configuration.

3.   When all the required information is provided the **Trigger** node is marked with a green check mark in the **Flow roadmap**.

## Action configuration

![Image 9: Add flow, action overview](https://docs-external.u4pp.com/extensions-kit/images/portal/add-action.png)

To add actions to your flow, you must:

1.   Open the list of available actions in the **Dynamic** section of the editor. To open it, you must:

    *   Select the action placeholder from the **Flow roadmap** for the first action. 
    *   Select the **Add new action** button from the **Flow roadmap** for further actions.

2.   Select an action.

3.   Fill in all the required fields of the **Action configuration** section to set up the action. Go to **Extensions**>**Actions** to see all the available actions and their configurations.

> Note: All flows must have at least one action.

### Templating in actions

To use other actions outputs as inputs, you can:

*   Use the **Plus (+)** button to display the **Suggestions** drop-down and select the desired data.
*   Enter the data manually: `{{Step0.SomeData}}`. 

> Note: When the focus is lost from the input, these input data fields are rendered as chips.

## Overview section

This section allows you to see:

*   A summary of everything you have configured during the flow creation process.
*   Configure an enable or disable some features.

![Image 10: Overview  summary](https://docs-external.u4pp.com/extensions-kit/images/portal/overviewnew.png)

The **Overview** section shows:

| **Field** | **Description** |
| --- | --- |
| _Flow name_ | The name of the flow. |
| **Enable/disable flow** switch | Turn on and off to enable or disable the flow. A blue switch indicates that the flow is enabled and a grey switch that the flow is disabled. |
| _Tenant ID_ | The tenant hosting the flow. |
| _Flow ID_ | Unique ID number generated by Extension Kit when a flow is saved to identify the flow. |
| _Flow description_ | A meaningful description of the flow's purpose and functionality. Only visible if defined while creating the flow. |
| _Summary_ | A summary of your flow that lists all the actions included in the flow. |
| _Extra data_ | This section appears after you have created a flow with a **Webhook** trigger. See [**Webhook (v2)**](https://docs-external.u4pp.com/extensions-kit/built-in-triggers/http-webhook-v2/#extra-data) for more details. It has the following data: • _Address_: URL to trigger the flow. • _Meta data address_: Provides an endpoint that returns the metadata in Swagger / OpenAPI format. For example, this metadata address can be used when using the Logic app's _Http plus Swagger_ connector. • _Trigger ID_: Unique ID number generated by Extension Kit to identify the trigger. |
| _Created by_ | The developer who created the flow. |
| _Latest changes_ | Date and developer to implement the last changes to the flow. |
| _Tags_ | Enter up to five tags to label your flow. Only owner and contributor roles can update tags: • Enter your text and press tab to create the different tags. • Each tag must contain only lowercase letters, numbers, dashes or underscores. White spaces are not accepted. • Maximum 15 characters. • Tags will be displayed in the flow card. • Select the **Cross icon** button to remove a tag. |
| Configuration settings | • [**Sensitive**](https://docs-external.u4pp.com/extensions-kit/guides/portal/sensitive-flows/): Turn on to disable input and output data storage in the flow history. • [**Static IP**](https://docs-external.u4pp.com/extensions-kit/guides/portal/static-ip/): Turn on to enable the use of static IP in the actions that allow it. Available only when activated as a feature by Unit4. • [**Automatic steps renumbering**](https://docs-external.u4pp.com/extensions-kit/guides/portal/edit/#rearrange-actions): Turn on to automatically renumber steps when these are added moved or removed from the flow. |
| Preview features | Features that are not yet in production: • **Optimize flow memory**: Turn on to apply optimizations to Liquid templating to improve memory consumption. Caution it might cause breaking changes. See [optimize flow memory](https://docs-external.u4pp.com/extensions-kit/guides/portal/create-a-flow/optimizeflowmemory.md) for more details. |

## Exit flow creation

If you decide to leave the creation process, select the **Cancel** button and a confirmation window appears prompting you to leave the process.

![Image 11: Add flow, cancel process confirmation](https://docs-external.u4pp.com/extensions-kit/images/portal/add-flow-cancel-2.png)
