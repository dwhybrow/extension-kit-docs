This tutorial shows how to use Liquid JS templating to send more customised JSON request bodies that combine user input with data from a **Data grid** component.

This example shows how to configure an app where the user can:

-   Enter a batch ID and an interface name using **Text inputs** components
-   Import data from an Excel using a **Data grid** component with the import functionality.
-   Send the combined data as a structured JSON array using Liquid JS templating.

![Batch processing app](https://docs-external.u4pp.com/extensions-kit/app-studio/images/tutorialsimg/tutorial-complex-body-final2.png)

The app uses advanced Liquid JS templating techniques to generate dynamic JSON structures that combine **Text inputs** with **Data grid** data.

To start:

1.  Select **My Apps** from the Extension Kit portal main menu.
2.  Select the **Create new app** button and name your app.
3.  Select the **Create** button.

![Create an app](https://docs-external.u4pp.com/extensions-kit/app-studio/images/tutorialsimg/createapp2.png)

## Configure the app layout

> ❗ IMPORTANT: The components and resources have dependencies between them. To configure this app, you must go from the **Canvas** tab to the **Resources** tab and the **Logic flow** tab frequently.

![Resources](https://docs-external.u4pp.com/extensions-kit/app-studio/images/tutorialsimg/tut3-tabs.png)

Go to the **Canvas** tab:

-   Drag and drop the **Layout** components to the canvas. In this example we added the following components in this order:
    -   Four containers:
        -   First container: Single column layout (for the **Text** component)
        -   Second container: Two columns layout with 50%/50% split (for the **Text inputs** components)
        -   Third container: Single column layout (for the **Data grid** component)
        -   Fourth container: Single column layout (for the **Button** component)

![App layout](https://docs-external.u4pp.com/extensions-kit/app-studio/images/tutorialsimg/tutorial-complex-body-layout.png)

-   Drag and drop the following components inside the **Layout** components, as shown in the image:
    -   One **Text** component (for the title)
    -   Two **Text input** components (for the batch ID and interface)
    -   One **Data grid** component (for the transaction data)
    -   One **Button** component (for sending the data)

![App components](https://docs-external.u4pp.com/extensions-kit/app-studio/images/tutorialsimg/tutorial-complex-body-components.png)

## Configure the Text component

In this example we configure the component as follows:

-   Select the **Text** component in the canvas and go to the **Properties** panel.
    -   Open the **Main** menu and configure:
        -   _Text_: Enter the text: Batch Transaction Processing.
    -   Open the **Styles** menu and configure:
        -   _Variant_: Select _Heading XL_ from the drop-down.

## Configure the Text input components

### Configure the Batch ID text input

-   Select the first **Text input** component in the canvas and go to the **Properties** panel.
    -   Open the **Main** menu and configure:
        -   _Component ID_: Select the **Edit (pencil)** button and enter 'batchId' and select the **Save (floppy disc)** button.
        -   _Label_: Enter the text: Batch ID
        -   _Placeholder_: Enter the text: BATCH-001

### Configure the Interface text input

-   Select the second **Text input** component in the canvas and go to the **Properties** panel.
    -   Open the **Main** menu and configure:
        -   _Component ID_: Select the **Edit (pencil)** button and enter 'interface' and select the **Save (floppy disc)** button.
        -   _Label_: Enter the text: Interface
        -   _Placeholder_: Enter the text: INVOICE

## Configure the Data grid component

In this example we configure the component as follows:

-   Select the **Data grid** component in the canvas and go to the **Properties** panel.
    
    -   Open the **Main** menu and configure:
        -   Enable the **Enable data import** checkbox. This feature will enable the **Import** button in the **Three dots** menu of the rendered component, allowing the end user to import data from an Excel file.
    -   Open the **Columns** menu and configure the following columns:
        
        **Column 1:**
        
        -   _Column ID_: Enter the text: invoiceNumber
        -   _Title_: Enter the text: Invoice number
        -   _Width_: Select _Stretch_ fom the drop-down.
        -   _Datatype_: Select _Text_ from the drop-down.
        
        **Column 2:**
        
        -   _Column ID_: Enter the text: amount
        -   _Title_: Enter the text: Amount
        -   _Width_: Select _Stretch_ fom the drop-down.
        -   _Datatype_: Select _Number_ from the drop-down.
        
        **Column 3:**
        
        -   _Column ID_: Enter the text: currency
        -   _Title_: Enter the text: Currency
        -   _Width_: Select _Stretch_ fom the drop-down.
        -   _Datatype_: Select _Text_ from the drop-down.

Go to the **Resources** tab:

## Create the _Send batch data_ resource

To configure the resource, follow these steps:

1.  Select the **Plus (+)** button on top of the left panel to create a new resource.
2.  Select the new resource on the left panel.
3.  Select the **Pencil** icon to change the name to 'Send batch data'
4.  Select **HTTP** from the **Type** menu on the right and configure:
    
    1.  **Configuration** section:
        
        -   _URL_: Enter `https://postman-echo.com/post`
        -   _Method_: Select _POST_ from the dropdown.
    2.  **Content definition** section:
        
        -   _Body Data Type_: Select _JSON_ from drop-down.
        -   _Content_: Delete the curly braces and copy and paste the following Liquid JS template JSON:
        
        `json copy [ {% for item in dataGrid1.rows %} { "header": { "batchId": "{batchId.value}", "interface": "{interface.value}" }, "transaction": { "id": { forloop.index0 }, "invoiceNumber": "{item.invoiceNumber}", "amount": {item.amount}, "currency": "{item.currency}" } } {% if forloop.last == false %},{% endif %} {% endfor %} ]`
        

> Note: This Liquid JS template iterates through each row in the **Data grid** component: dataGrid1, and creates a JSON object for each transaction. The `forloop.index0` provides a zero-based index, and the conditional comma ensures proper JSON formatting. See the [understanding liquid JS template](https://docs-external.u4pp.com/extensions-kit/app-studio/tutorials/tutorial-send-complex-request-body-with-liquid/#understanding-liquid-template) section for more details.

Go to the **Canvas** tab:

## Configure the Button component

In this example we configure the component as follows:

-   Select the **Button** component in the canvas and go to the **Properties** panel.
    -   Open the **Main** menu and configure:
        -   _Text_: Enter the text: Send data.
    -   Open the **Styles** menu and configure:
        -   _Icon before_: Select the _Send_ icon from the drop-down.
    -   Open the **Logic map** tab in the bottom-right corner and configure:
        -   Drag the **On click** event to the viewport.
        -   Drag the **HTTP Request** action to the viewport and connect it to the **On click** event.
        -   Select **HTTP Request** action in the viewport to see the **Properties** panel to the right.
        -   Open the **HTTP** drop-down.
        -   Select the resource _Send Batch Data (res1)_.

![Logic map](https://docs-external.u4pp.com/extensions-kit/app-studio/images/tutorialsimg/tutorial-complex-body-logic.png)

Finally, after configuring the components and the resource, select the **Save draft** button and preview your app.

> Note: See the Components documentation, [resources](https://docs-external.u4pp.com/extensions-kit/app-studio/resources/) and [logic drawer](https://docs-external.u4pp.com/extensions-kit/app-studio/logic/logic-drawer/#actions) for more details.

## Example of usage

The following example shows how the end-user of the app should use the app:

1.  **Text input Configuration**: The user enters in the corresponding components:
    
    -   Batch ID: BATCH-001
    -   Interface: INVOICE
2.  **Data Import**: The user imports an Excel file with the following content:
    
    -   Row 1:
        -   Column A: INV-100
        -   Column B: 500
        -   Column C: USD
    -   Row 2:
        -   Column A: INV-101
        -   Column B: 750
        -   Column C: EUR
3.  **Generated Request Body**: After the user selects the **Send data** button, the following JSON will be sent: `json [ { "header": { "batchId": "BATCH-001", "interface": "INVOICE" }, "transaction": { "id": 0, "invoiceNumber": "INV-100", "amount": 500, "currency": "USD" } }, { "header": { "batchId": "BATCH-001", "interface": "INVOICE" }, "transaction": { "id": 1, "invoiceNumber": "INV-101", "amount": 750, "currency": "EUR" } } ]`
    

## Understanding Liquid template

The Liquid JS template used in this tutorial demonstrates several key concepts:

-   **Loop iteration**: `{% for item in dataGrid1.rows %}` iterates through each row in the **Data grid** component with the ID `dataGrid1`.
-   **Component values**: `{{batchId.value}}` and `{{interface.value}}` access the current values of **Text input** components.
-   **Row data access**: `{{item.invoiceNumber}}` accesses column data from the current row.
-   **Loop indexing**: `{{forloop.index0}}` provides a zero-based counter for each iteration.
-   **Conditional logic**: `{% if forloop.last == false %},{% endif %}` adds commas between JSON objects but not after the last one.

This approach allows for dynamic generation of complex request bodies that scale with the amount of imported data.
